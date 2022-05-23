## _Hosting a Full-Stack Application_

deploy  developed full stack application to a cloud service provider(aws) so that it is available to customers. This application contains the main components of a 3-tier full stack application (UI, API, and Database).
## Project Environment
Node v16.13.1    # To run the application
npm v8.9.0		 # For dependency management
yarn v1.22.18    # For dependency management
AWS CLI v2		 # to create and deploy elasticbeanstalk
docker-compose   # To run the Postgres database on Docker
##project setup
1. clone the project: - git clone https://github.com/nermeenElmesalmy/udagram.git
2. go into the directory where the project:- cd udagram
3. install the dependencies: - yarn add
4. run the app: yarn start

## Installation
Install the dependencies and devDependencies and start the server.
```
npm i
yarn
 
```
## update environment in ( udagram-api , udagram-fromtend)

update a .env file with all the required environment variables
### in udagram-api
POSTGRES_HOST="localhost"
DB_PORT=5432
PORT=3000
POSTGRES_PASSWORD="123"
POSTGRES_USERNAME="postgres"
RDS_DIALECT="postgres"
POSTGRES_DB="udagram"
AWS_REGION=""
AWS_PROFILE=""
AWS_BUCKET=""
URL="http://localhost"
AWS_ACCESS_KEY_ID=""
AWS_SECRET_ACCESS_KEY=""
JWT_SECRET="HOSTING FULL-STACK"

### in udagram-fromtend
export const environment = {
  production: true,
  appName: "Udagram",
  apiHost: "http://udagram-api-dev.eba-ys7fm4p9.us-east-1.elasticbeanstalk.com/api/v0",
};

## run the project locally
### _in udagram-api_ ###
yarn run dev 
yarn run build
### _in udagram-frontend_ ###
yarn run start
yarn run build
## the project link in github
https://github.com/nermeenElmesalmy/udagram
## hosting the project in aws
-interact with cloud services(deploy the application used aws console)
-deploy a database using AWS RDS
-deploy a web server using AWS Elastic Beanstalk
-deploy a web UI using AWS S3
-create buckets

## connect the github ,circleci and  AWS ##
##setting up a production environment ##

write scripts for web applications
(write scripts )
```
"scripts": {
         "frontend:install": "cd udagram-frontend && yarn install",
        "backend:install": "cd udagram-api && yarn install",
        "frontend:build": "cd udagram-frontend && yarn build",
        "backend:build": "cd udagram-api && yarn build",
        "frontend:test": "cd udagram-frontend && yarn test && yarn e2e",
        "backend:test": "cd udagram-api && yarn test",
        "frontend:deploy": "cd udagram-frontend && yarn deploy",
        "backend:deploy": "cd udagram-api && yarn deploy"

        }
```
configure and document a CI/CD 
-create a CI/CD pipeline in  CircleCI
-create . circleci folder with config.yml file
```
orbs:
  node: circleci/node@5.0.2
  aws-cli: circleci/aws-cli@1.3.1
  eb: circleci/aws-elastic-beanstalk@1.0.2
jobs:
  build:
    docker:
      - image: "cimg/node:18.1.0"
    
    steps:
      - node/install
      - checkout
      - aws-cli/setup
      - eb/setup
      - run: |
          node --version
      - run:
          name: Front-End Install
          command: |
            yarn frontend:install
      - run:
          name: Back-End Install
          command: |
            yarn backend:install
      - run:
          name: Front-End Build
          command: |
            yarn frontend:build
      - run:
          name: Back-End Build
          command: |
            yarn backend:build
      - run:
          name: Deploy App
          command: |
            yarn frontend:deploy
      - run:
          name: Deploy Server
          command: |-
             yarn backend:deploy            
workflows:
  build-and-test:
    jobs:
      - build
      
```
## Testing
This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

cd starter/udagram-frontend
yarn test
yarn e2e
There are no Unit test on the back-end

Unit Tests:
Unit tests are using the Jasmine Framework.

End-to-End Tests:
The e2e tests are using Protractor and Jasmine.

## the frontend link in aws:
http://full-stack-ner.s3-website-us-east-1.amazonaws.com
##  Copyright and licensing information
Nermeen Elsayed Ahmed Mohamed .
FreeSoftware,
## resources 
udacity.com
https://aws.amazon.com/rds/resources/
https://www.postgresql.org/docs/current/
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_express.html
https://video.udacity-data.com/topher/2021/March/604f64fd_build/build.zip

 


