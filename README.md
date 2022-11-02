# udagram-project
## Hosting a Full-Stack Application

### Udagram

##Site

http://udagram-api-dev.eba-cpdffcj3.us-east-1.elasticbeanstalk.com/

Installation
Provision the necessary AWS services needed for running the application:

In AWS, provision a publicly available RDS database running Postgres.
In AWS, provision a s3 bucket for hosting the uploaded files.
Export the ENV variables needed or use a package like dotnev/.
From the root of the repo, navigate udagram-api folder cd starter/udagram-api to install the node_modules npm install. After installation is done start the api in dev mode with npm run dev.
Without closing the terminal in step 1, navigate to the udagram-frontend cd starter/udagram-frontend to intall the node_modules npm install. After installation is done start the api in dev mode with npm run start.


### Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1- cd starter/udagram-frontend
2- npm run test
3- npm run e2e

There are no Unit test on the back-end

Unit Tests:
Unit tests are using the Jasmine Framework.

End to End Tests:
The e2e tests are using Protractor and Jasmine.
