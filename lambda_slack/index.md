# Invoke AWS Lambda from Slack


<br/>


**AWS Lambda** is a compute service that lets you run code without provisioning or managing servers. Lambda runs your code only when needed and scales automatically, from a few requests per day to thousands per second. AWS Lambda in our task is invoked using the API Gateway.

**Slack** is a channel-based messaging platform. With Slack, people can work together more effectively, connect all their software tools and services, and find the information they need to do their best work — all within a secure, enterprise-grade environment.

<br/>

![ ](/images/lambda_slack/intro.png "Invoke lambda function through API Gateway from Slack")

<br/>

This blog covers on how to invoke AWS Lambda function through API Gateway when there is a new message posted to any Slack channel.

<br/>

Here are a few business cases where this can be used:

1. If a Quality Analyst wants to trigger an integration test by sending a message via Slack.
2. If a Developer wants to get logs of a Load Balancer which is managed by the Security Team.

<br/>

Here are the steps to be followed….

<br/>

***Step1: First let’s configure Slack***

Create a workspace in slack.com, then create a slack app at api.slack.com/apps in the newly created workspace and then go to OAuth & Permissions tab, add **channels:history, channels:read, chat:write, im:history & mpim:history** OAuth scope to Bot Token Scopes and User Token Scopes. Now install your app to workspace and allow necessary permissions, then User OAuth Token & Bot User OAuth Token are generated.

<br/>

![ ](/images/lambda_slack/step-1.png "Bot and User Token Scopes")

<br/>

![ ](/images/lambda_slack/step-1.2.png "OAuth & Permissions page")

<br/>

And also keep the copy of verification token which is present in the Basic Information tab of your app.

<br/>

![ ](/images/lambda_slack/step-1.3.png "Access Verification Token from Basic Information page
")

<br/>

***Step 2: Now let’s move on to AWS Lambda configuration part***

Let’s create a Lambda function using Author from scratch lambda function template. Select runtime as Node.js and Create a new role with basic Lambda permissions.

<br/>

![ ](/images/lambda_slack/step-2.1.png "Creating Lambda function in AWS Lambda Console")

<br/>

Now your lambda function is created. In the code tab, change index.js file as follows.

<br/>

```
//Verify Url - https://api.slack.com/events/url_verification
function verify(data, callback) {
    if (data.token === VERIFICATION_TOKEN) callback(null, data.challenge);
    else callback("verification failed");   
}
//Print the slack message on the console
function process(data,context, callback) {
    console.log('context:', JSON.stringify(context));
    console.log('data.event.text',JSON.stringify(data.event.text));
    callback(null,data.event.message);
}
// Lambda handler
exports.handler = (data, context, callback) => {
    console.log(data);
    switch (data.type) {
        case "url_verification": verify(data, callback); break;
        case "event_callback": process(data,context, callback);break;
        default: callback(null,"Hello from Lambda");
    }
};
```

###### *[APP VERIFICATION TOKEN]: Access this token in the basic information tab of the slack app created in Step 1(Refer to Access Verification Token from Basic Information page figure in Step 1).* 
###### *[SLACK ACCESS TOKEN]: Access Bot User OAuth Token from OAuth Tokens for Your Team in OAuth & Permissions page(Refer to OAuth & Permissions page figure in Step 1).*

***Step 3: In this step, API Gateway is configured***

Add a REST API gateway trigger to the lambda function and select Security as Open. In the additional settings, change the deployment stage name to prod(Optional).

<br/>

After the trigger is added, go to API gateway console, add method POST to the resource. After creating POST method, then select Deploy API option from the Actions menu.

<br/>

![ ](/images/lambda_slack/step-3.1.png "Add POST method to the SlackLambda resource")

<br/>
<br/>

![ ](/images/lambda_slack/step-3.2.png "Select Deploy API")

<br/>

Select the Deployment stage which was created in the earlier step, then click deploy

<br/>

![ ](/images/lambda_slack/step-3.3.png "Deploy API to prod stage")

<br/>

***Step 4: Slack Configuration post AWS Lambda/API Gateway configuration***

From Slack App(api.slack.com/apps), select the newly created app. Then go to Event Subscriptions and Enable Events. In the Request URL textbox, paste the API gateway URL which can be accessed from the configuration tab of Lambda function.

<br/>

![ ](/images/lambda_slack/step-4.1.png "Enabling EVents in Event Subscription page")

<br/>

Proceed once the URL is verified. Scroll down and subscribe to message:channels, message.im & message.mpim bot events and events on behalf of users. Then go back to OAuth & Permissions tab and Reinstall app to workspace.

<br/>


![ ](/images/lambda_slack/step-4.2.png " ")

<br/>

## Now let’s test it!

Open slack.com and Launch the workspace where the app is created then post the message to a slack channel or a direct message.

<br/>

![ ](/images/lambda_slack/step-4.3.png "Message posted to slack channel")

<br/>

Now check the message and metadata of the message in the cloud-watch log console.

<br/>

![ ](/images/lambda_slack/step-4.4.png " ")

<br/>

To conclude, When someone posts a message to a slack channel, the API gateway triggers the lambda function and cloud watch logs has a record of all the Lambda invocations.

We have come to an end of this blog. Hope you liked it, please do share it with your friends. ***Happy Reading!***
<br/>
<br/>

*Siya Amonkar is a DevOps Engineer who likes to explore new tools and technologies. She can be reached out on [LinkedIn](https://www.linkedin.com/in/siya-amonkar-b818b41b4) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=siya.amonkar9811@gmail.com)*

<br/>

*Varsha is a software engineer with overall experience of 2 years,  who loves to play with devops tools and is a cloud computing enthusiast. She can be reached out on [LinkedIn](https://www.linkedin.com/in/varsha-reddy-kumbham-05714317b) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=varshareddykumbham@gmail.com)*

