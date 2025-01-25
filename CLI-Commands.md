# To Add Files To a Repository:
```
git add serverless.yml
git commit -m "Added serverless.yml"
git push origin main
```
```
git add CLI-Commands.md
git commit -m "Added CLI-Commands.md"
git push origin main
```

Merge / Rebase
```
git pull --no-rebase
git pull --rebase
git pull --ff-only
aws s3 cp index.html s3://thamidaffan-bucket/index.html

git push -u origin main
git fetch origin

```
```
# Test the API Using Curl:
https://26pp853315.execute-api.us-east-1.amazonaws.com/prod/chat

curl -X POST https://your-api-id.execute-api.region.amazonaws.com/prod/chat -H "Content-Type: application/json" -d '{"username": "testuser", "message": "Hello, world!"}'

# Custom Command based on my account:
curl -X GET https://26pp853315.execute-api.us-east-1.amazonaws.com/prod/chat \
-H "x-api-key: wJYJ0PVkfl24Rq6keKtTQVNUdJ71tbq3QxqH9vM7"

aws lambda update-function-code --function-name your-function-name --zip-file fileb://function.zip --region us-east-1

# Trust Policy for IAM - Lambda Permission
```
```   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "Service": "lambda.amazonaws.com"
         },
         "Action": "sts:AssumeRole"
       }
     ]
   }
```
```
aws lambda invoke --function-name your-function-name1 --payload '{"httpMethod": "GET"}' response.json --cli-binary-format raw-in-base64-out --region us-east-1

aws lambda add-permission --function-name <your function name> --statement-id APIGatewayInvokePermission --action lambda:InvokeFunction --principal apigateway.amazonaws.com --source-arn arn:aws:execute-api:us-east-1:<your_account_id>:<api-id>/*/POST/chat

aws lambda add-permission --function-name your-function-name1 --statement-id APIGatewayInvokePermission94 --action lambda:InvokeFunction --principal apigateway.amazonaws.com --source-arn arn:aws:execute-api:us-east-1:954976328760:26pp853315/*/POST/chat

aws lambda add-permission --function-name your-function-name1 --statement-id APIGatewayInvokePermission94 --action lambda:InvokeFunction --principal apigateway.amazonaws.com --source-arn arn:aws:execute-api:us-east-1:954976328760:26pp853315/*/GET/chat
```
