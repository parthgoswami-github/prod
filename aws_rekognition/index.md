# How to configure AWS Rekognition and AWS Transcoder


![](/images/aws_rekognition/intro.png " ")

## Consider a scenerio:

We have setup a VPC for the instances which are in the same range. The Public instance is having an internet connection and Private instance does not having an internet connection. 

Inside Public instance we have S3 bucket endpoint to which users will have the access to upload/download images and videos. The EC2 instances have an ELB (Elastic Load Balancer) attached with an Alarm set to it. 

The EC2 instances will have IAM roles attached to it having roles set like *AWSS3FullAccess*, *AWSRekognitionFullAccess* and *AWSElasticTranscoderFullAccess.*
 
## Steps:

1. Private instance will have NAT connectivity with Public instance which will open a browser with the endpoint given to the user to access S3 bucket uploads an image an request for image recognition.

<br/>

2. Inside EC2 run this command to get the output:

	
	```
	aws rekognition detect-labels --image "{\"S3Object\":{\"Bucket\":\"bucketname\",\"Name\":\"image.png\"}}" --region us-east-1
	

<br/>

3. The output of the image recognition will be stored in Amazon RDS.

<br/>

4. If the user wants a video to be converted to the version which can be accessible via phone or pc can upload the video in S3 Bucket and by setting up a pipeline in AWS Transcoder the user will be notified about the process completion and the user can further request for image/video recognition.

<br/>

5. The user having internet connection will access S3 Bucket with the endpoint provided and can further request for the AWS Rekognition. Procedure is same as above.

## Configuration:

1. **First step is to configure VPC:** <br/>

	1.1 Create VPC with the name **MyVPC**: <br/>
![](/images/aws_rekognition/step-1.1.png " ")
	1.2 Create 3 Subnets with the name **Public**, **Public1**, **Private**:<br/>
![](/images/aws_rekognition/step-1.2.png " ")
	1.3 Create a separate Route table with names **PublicRT** and **PrivateRT** and place the subnets with the respective route table:<br/>
![](/images/aws_rekognition/step-1.3.1.png " ")
![](/images/aws_rekognition/step-1.3.2.png " ")
	1.4 Create a Gateway with the name **MyGateway**:<br/>
![](/images/aws_rekognition/step-1.4.png " ")
2. **Create three EC2 instances and attach them with *MyVPC* as given below :**<br/>
![](/images/aws_rekognition/step-2.1.png " ")
![](/images/aws_rekognition/step-2.2.png " ")
![](/images/aws_rekognition/step-2.3.png " ")
![](/images/aws_rekognition/step-2.4.png " ")
3. **Create IAM roles the instances:** <br/>

	3.1 Create IAM roles for Public Instance with respective policy as shown below:<br/>
![](/images/aws_rekognition/step-3.1.png " ")
	3.2 Create IAM role for Private instance which holds RDS policy (optional) :<br/>
![](/images/aws_rekognition/step-3.2.png " ")
4. **Create S3 bucket as follows:** <br/>

	4.1 Create 2 buckets with the name **inputbucket12** and **outputbucket12**:<br/>
![](/images/aws_rekognition/step-4.1.png " ")
	4.2 In **inputbucket12** will be used to upload images and videos:<br/>
![](/images/aws_rekognition/step-4.2.png " ")
5. **Setup for AWS Image Rekognition in *Public* instance using cli mode:**<br/>
![](/images/aws_rekognition/step-5.png " ")
6. **Setting up AWS Transcoder for video converter:** <br/>

	6.1 Create Pipeline as given below:<br/>
![](/images/aws_rekognition/step-6.1.png " ")
	6.2 Create job for the Pipeline:<br/>
![](/images/aws_rekognition/step-6.2.1.png " ")
![](/images/aws_rekognition/step-6.2.2.png " ")
![](/images/aws_rekognition/step-6.2.3.png " ")
![](/images/aws_rekognition/step-6.2.4.png " ")
	6.3 Output of the video will be shown in **outputbucket12**:<br/>
![](/images/aws_rekognition/step-6.3.1.png " ")
![](/images/aws_rekognition/step-6.3.2.png " ")
![](/images/aws_rekognition/step-6.3.3.png " ")



-------
<br/>


*Shreya Dhange is a Technical Training Developer at [Red Hat](https://www.redhat.com/en), who likes to explore and learn new technologies and share her knowledge by writing articles. She has completed her Masters in Computer Science and has gained award for her exemplary academic performance. She has been engaged in creating and delivering content in the cloud and linux space. She can be reached out [LinkedIn](https://www.linkedin.com/in/shreyadhange/) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=shreyadhange@gmail.com)*.

