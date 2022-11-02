FrontEnd Deploy Script:

    aws s3 cp --recursive --acl public-read ./www s3://udacity-project-aws/
    aws s3 cp --acl public-read --cache-control="max-age=0, no-cache, no-store, must-revalidate" ./www/index.html s3://udacity-project-aws/

BackEnd Deploy Script:

cd ./www
eb init udacity-project-aws --region us-east-q --platform node.js
eb use udacity-project-aws-dev
eb setenv POSTGRES_HOST=$POSTGRES_HOST PORT=$PORT POSTGRES_USERNAME=$POSTGRES_USERNAME POSTGRES_PASSWORD=$POSTGRES_PASSWORD POSTGRES_DB=$POSTGRES_DB DB_PORT=$DB_PORT AWS_DEFAULT_REGION=$AWS_DEFAULT_REGION    URL=$URL JWT_SECRET=$JWT_SECRET EB_APP=$EB_APP EB_ENV=$EB_ENV AWS_BUCKET=$AWS_BUCKET
eb deploy

Pipeline Jobs:

    - Install Dependencies for Front & BackEnd Commands:
        - cd udagram-api && npm install
        - cd udagram-frontend && npm install

    - Build BackEnd & FrontEnd Commands:
        - cd udagram-api && npm run build
        - cd udagram-frontend && npm run build

    - Deploy FrontEnd & BackEnd Commands:
        - cd udagram-api && npm run deploy
        - cd udagram-frontend && npm run deploy
