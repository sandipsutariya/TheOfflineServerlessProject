# TheOfflineServerlessProject

This project was to check how one can run serverless project offline.

## Prerequisit 
To run serverless project in offline node, one need the project ```serverless-offline``` as dependency.

## How to run this for development 

```

yarn dev

```

## How one access the offline resources
when you run it using ```yarn dev``` command, it shows below console log 

```

offline: Starting Offline: dev/us-east-1.
offline: Offline [http for lambda] listening on http://localhost:3002
offline: Function names exposed for local invocation by aws-sdk:
           * hello: theofflineproject-dev-hello

   ┌─────────────────────────────────────────────────────────────────────────┐
   │                                                                         │
   │   GET | http://localhost:3000/dev/hello                                 │
   │   POST | http://localhost:3000/2015-03-31/functions/hello/invocations   │
   │                                                                         │
   └─────────────────────────────────────────────────────────────────────────┘

offline: [HTTP] server ready: http://localhost:3000 🚀

```
Now here, you can access the local endpoint (http://localhost:3000/dev/hello) for API directly. This internally calls lambda and give you output. You can also invoke lambda directly using ``` aws cli ``` using below command. Here is the endpoint url and function name is discovered from logs. 

```

aws lambda invoke output.txt --endpoint-url http://localhost:3002 --function-name theofflineproject-dev-hello

```
