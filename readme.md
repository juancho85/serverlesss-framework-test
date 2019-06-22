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
## It can be removed with the following command
`serverless remove`

# Behind the scenes
Behind the scenes a cloud formation template is created and deployed to an S3 bucket (added to source control)