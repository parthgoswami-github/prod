# Deploying Jenkins slave using docker containers



While exploring Jenkins, I came across a usecase wherein I wanted to make use of Jenkins slave to build some of my jobs. So after exploring I found out a way wherein we can deploy Jenkins slave as containers. Once the job is complete, the containers will be destroyed, thus releasing the resources. This removes the dependency to have extra VM's or need for more storage to accomodate the jobs.

This article is based on configurations tried and tested on MAC. For other environments, you need to make appropriate changes on Step B.

<br/>

<b>Assumptions :</b>
1. You have Jenkins Master already installed on docker as a container. If not you can use the following command to launch the jenkins container.

```
docker run --name jenkins -p 8080:8080 -p 50000:50000 jenkins/jenkins
```

<b>Note</b> : Complete the installation with all the plugins.

<br/>

Follow below <b>Steps</b> to setup jenkins build agents :

A. You need to expose the docker api, so that the jenkins can launch the jenkins build agent to complete it's jobs. You can use the following command to expose the docker API to be used,


```
docker run -d --restart=always -p 127.0.0.1:2376:2375 -v /var/run/docker.sock:/var/run/docker.sock alpine/socat tcp-listen:2375,fork,reuseaddr unix-connect:/var/run/docker.sock
```

<br/>

B. Once the above command is ran, you can check if the docker api is actually exposed to be used. Login to jenkins container and run the below command,


```
docker exec <container-name> curl http://docker.for.mac.localhost:2376/v1.41/info
```

<br/>

C. Once you get an output, you need to install a plugin on Jenkins called Docker.

<br/>

![ ](/images/nihalshah/jenkins/image1.png " ")
<br/>

D. Next you need to configure the jenkins build agent ( slave ) templates. Navigate to Manage Jenkins --> Manage Nodes and Clouds --> Configure Clouds
You will see following screen, 
![ ](/images/nihalshah/jenkins/image2.png " ")

**Note** : You will only see Add a new cloud option. 

<br/>

E. Once you navigated to above location, click on Add a new cloud --> Select Docker --> Then click on Docker Cloud details and configure the following settings,
Docker Host URI : tcp://docker.for.mac.host.internal:2376
Enabled : Select the option

<br/>

F. Now you can see the Test Connection option, please click on it and you should see the version of docker installed,

<br/>

![ ](/images/nihalshah/jenkins/image3.png " ")

If you got the ouput on step B, then you shouldn't face any issues.

<br/>

G. Next we need to configure the Docker Agent templates, this template will be used by Jenkins to launch the Jenkins build agent container.
1. <b>Label</b> : If you need to schedule a particular job to run on particular jenkins slave node.
2. <b>Enabled</b> : Select the option, so that jenkins can auto launch the containers when it needs to run the job
3. <b>Name</b> : Can be anything as per your preference
4. <b>Docker Image</b> : jenkins/agent --> Preferred image for launching the container. There is another image called jenkins/slave but it has some issues, so it's best to go with jenkins/agent
5. <b>Registry Authentication</b> : Use the creds you use to login to registry. The creds you use to login to hub.docker.com
6. <b>Remote File System Root</b> : Basically the path where you job would run
7. <b>Connect method</b> : Attach docker container
Done this would setup the agent template. 

Once above settings are done, you are good to run the job using jenkin build agent on docker container.
I hope you liked the article. Cheers!

-------
<br/>


*Nihal Shah is a Devops engineer who loves to explore new tools and automate different processes for ease of use. He can be reached out on [LinkedIn](https://www.linkedin.com/in/nihal-shah-619469153), [Twitter](https://twitter.com/nihalshah9?t=a6xKhOgsQs_b1-I6tjxO_Q&s=08) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=nihals175@gmail.com)*.

