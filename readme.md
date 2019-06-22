# Following example here
## Step 1. Install serverless globally
`$ npm install serverless -g`
## Step 2. Create a serverless function
`$ serverless create --template hello-world`
## Step 3. deploy to cloud provider
`$ serverless deploy`
* We can modify region and stage like this
`$ serverless deploy -r eu-east-1 -s dev`
## Your function is deployed!
 `http://xyz.amazonaws.com/hello-world`
## Update only a function
`serverless deploy -f helloWorld`
## Get logs for a function (or tail logs)
~~~
serverless invoke -f hello -l
serverless logs -f hello -t
~~~
## Security - setting up credentials properly
https://serverless.com/framework/docs/providers/aws/guide/credentials/

## Services
https://serverless.com/framework/docs/providers/aws/guide/services/
## Functions
https://serverless.com/framework/docs/providers/aws/guide/functions/

## Cheat sheet
https://serverless.com/framework/docs/providers/aws/guide/workflow/#cheat-sheet



## It can be removed with the following command
`serverless remove`

# How it works
* When creating a template by default a serverless.yml file and a handler.js file are created
* serverless.yml main responsibilities
    * Declaring a serverless service
    * Defining one or more functions in the service
    * Define events triggering each function
    * Define a set of resources (ex. DynamoDB table)
    * ...
* Behind the scenes a cloud formation template is created and deployed to an S3 bucket (added to source control)
* handler.js
    * Contains the function code (serverless.yml points to this handler.js)
* event.json
    * Add event data so that the function can be invoked with the data via
     `serverless invoke -p event.json`