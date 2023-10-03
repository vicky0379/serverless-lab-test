[LevelUp! Lab for Serverless] (https://github.com/vicky0379/serverless-lab-test/)

[Lab Overview And High Level Design] (https://github.com/vicky0379/serverless-lab-test/)

Let's start with the High Level Design.
![image](https://github.com/vicky0379/serverless-lab-test/assets/40485508/022ffd66-2a63-49d1-a0cd-7b02a55926d6)
An Amazon API Gateway is a collection of resources and methods. For this tutorial, you create one resource (DynamoDBManager) and define one method (POST) on it. The method is backed by a Lambda function (LambdaFunctionOverHttps). That is, when you call the API through an HTTPS endpoint, Amazon API Gateway invokes the Lambda function.

The POST method on the DynamoDBManager resource supports the following DynamoDB operations:

Create, update, and delete an item.
Read an item.
Scan an item.
Other operations (echo, ping), not related to DynamoDB, that you can use for testing.
The request payload you send in the POST request identifies the DynamoDB operation and provides necessary data. For example:

The following is a sample request payload for a DynamoDB create item operation:
{
    "operation": "create",
    "tableName": "lambda-apigateway",
    "payload": {
        "Item": {
            "id": "1",
            "name": "Bob"
        }
    }
}

The following is a sample request payload for a DynamoDB read item operation:

{
    "operation": "read",
    "tableName": "lambda-apigateway",
    "payload": {
        "Key": {
            "id": "1"
        }
    }
}

