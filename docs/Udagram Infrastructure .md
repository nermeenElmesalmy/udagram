# AWS
## RDS Postgres
The application server uses AWS RDS Postgres as database for storing and retrieving information.

Database URL:
database-1.c35snyvfanhr.us-east-1.rds.amazonaws.com
## Elastic Beanstalk
The application server is deployed on AWS Elastic Beanstalk service. The application is build, archived and uploaded to and S3 bucket from where Elastic Beanstalk extracts and runs the application on an endpoint.

EB URL:http://udagram-api-dev.eba-ys7fm4p9.us-east-1.elasticbeanstalk.com
## S3 Bucket
The frontend application is deployed using AWS S3 Bucket. The bundled assets are uploaded to an S3 bucket and that bucket is made publicly readable.

Bucket URL: http://full-stack-ner.s3-website-us-east-1.amazonaws.com

End users can access the application from the Bucket URL.