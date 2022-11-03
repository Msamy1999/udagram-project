FrontEnd Deploy Script:

    aws s3 cp --recursive --acl public-read ./www s3://udacity-project-aws/
    aws s3 cp --acl public-read --cache-control="max-age=0, no-cache, no-store, must-revalidate" ./www/index.html s3://udacity-project-aws/

BackEnd Deploy Script:

cd ./www
eb init udagram-api --platform node.js --region us-east-1
eb create --sample udagram-api-dev
eb use udagram-api-dev
yarn build
eb deploy udagram-api-dev
eb open

## Pipeline Jobs:

    ### Steps;

        -Developer update the code localy
        -Push the changes to the github repo
        -Circle Ci will trigger this changes and will start the pipeline
        -Install Node
        -Install AWS Elastic Beanstalk
        -Install AWS CLI
        -Install Front-End Dependencies
        -Lint Front-End
        -Install API Dependencies
        -Build Front-End
        -Build API
        -Wait for the user's approval to deploy the application
        -Update API code in Elastic Beanstalk
        -Update Front-End code in S3 Bucket
