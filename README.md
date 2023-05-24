## DevOps-training-web-application
This is 3-tier application deployment on AWS using Terraform and Docker.
In this blog post, we will build a highly available application on top of AWS cloud services. 
To make more sence to the architecture we have imagine the folowing scenario

### Scenario description
We will design an architecture for a DevOps training web application, where students will be able to practice DevOps through pre-recorded videos. This web app is intended to solve the problem of some students not able to attend class at the set time.

#### Requirements:
- High availability is needed as there should be no interruption when the student is watching pre-recorded runboock
- The server should always be up to enable users to access courses anytime
- It must be easy to scale up or down because we do not know the traffic pattern, so we better be prepared.
- The app servers that deal with the database should not be accessible by the rest of the world to ensure security, no one should temper with the data

We will deploy the following architecture.

![Diagram](/images/diagram.png)

1. Create 2 ECR repositories:
```
ECR_APPLICATION_REPO_NAME = app-application-tier
ECR_PRESENTATION_REPO_NAME = app-presentation-tier
```
2. Build and push the images for each tier. 
```
cd ./application-tier/
docker build -t .........
docker tag ........
docker push .......
```
Then, do the same for the presentation tier. 
```
cd ../presentation-tier/
docker build -t .......
docker tag ......
docker push ........
```
Now, we should navigate to the Terraform folder and run `terraform init`.

We should run `terraform apply --auto-approve`
