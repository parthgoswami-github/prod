# Amazon S3 at a glance



Amazon S3 is used to store any amount of data of object type such as static websites, documents, images, videos and backup files as well. This data can be retrieved at any time from anywhere on the web.

Inside S3 you create **Buckets** to store your objects/data. You can create multiple buckets in any region and it stores data upto 5TB.

After you create buckets and upload objects in Amazon S3, you can manage your object storage using below features:

- **Versioning:** You can create multiple copies of your data. If the data center goes down in any region your data will be maintained in other data center of that region. If your data gets deleted versioning helps in retrieving it as it creates version ID of your data. It prevents overwriting or accidential deletion of data. As and when you make any changes in your data the latest copy will be available on the top.

- **Cross region replication:** If you want to copy data from one region bucket to another region bucket you can do it using cross region replication.

- **Transfer acceleration:** Transferring the data from one location to another location with low latency. Transfer acceleration puts data to CloudFront Edge Location and transfers your data. Amazon CloudFront is been explained in another blog.

- **Lifecyle:** You can decide the lifecyle of an object by just settings its lifecycle. For example: Now if your objects are in Standard-IA and after few days you want those objects to be in Glacier in that case you can set lifecycle to your objects.


There are classes of  S3 to store the objects based on the requirements:
- S3 Standard
- S3 Infrequent Access or Standard-IA 
- S3 Glacier

## S3 Standard

Suppose you have hosted a website and its objects are stored in Amazon S3 out of which you only need few data to be fetched frequently. You can use S3 Standard for such objects as its durability is 99.999% and can be fetched in millisec and is highly available. You can store any file that can be as low as KB. You can store the data for an indefinite period of time.

### Key features:

- Low latency and high performance.
- Durability is 99.999999999% of objects across multiple Availability Zones
- Supports SSL for data in transit and encryption of data at rest

## S3 Infrequent Access or Standard-IA:
Suppose you have a image gallery of 2020 images and you do not need it frequently but you only need few images as and when needed so you stored such datas in Standard-IA. Standard-IA fetches data at a durability of 99.9% and can store the data uptill 30 days with a low per GB storage price and per GB retrieval charge. 

### Key features:
- Low latency and high performance.
- Durability is 99.999999999% of objects across multiple Availability Zones
- Supports SSL for data in transit and encryption of data at rest

## S3 Glacier:
S3 Glacier stores archival data that you do not require it on daily bases for example: medical images, news media assets, or genomics data. Its durability of fetching the data is milliseconds to hours to fit your performance needs. You can increase its fetching time by paying certain price per GB pay. It can store 128 KB minimum object size.
 
### Key features:
- Low latency and high performance.
- Data retrieval options from milliseconds to hours as required.
- Durability is 99.999999999% of objects across multiple Availability Zones
- Supports SSL for data in transit and encryption of data at rest
- Data is resilient in the event of the destruction of one entire Availability Zone


-------
<br/>


*Shreya Dhange is a Technical Training Developer at [Red Hat](https://www.redhat.com/en), who likes to explore and learn new technologies and share her knowledge by writing articles. She has completed her Masters in Computer Science and has gained award for her exemplary academic performance. She has been engaged in creating and delivering content in the cloud and linux space. She can be reached out [LinkedIn](https://www.linkedin.com/in/shreyadhange/) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=shreyadhange@gmail.com)*.

