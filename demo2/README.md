
1. Show the SAM Template Bookmarked in builders day: https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:729047367331:applications~simple-websockets-chat-app
2. Create a new WebSocket API
1. In the API Gateway console, choose Create API, New API.
2. Under Choose the protocol, choose WebSocket.
3. For API name, enter My Chat API.
4. For Route Selection Expression, enter $request.body.action.
5. Enter a description if you’d like and click Create API.
6. In the API Gateway console, under My Chat API, choose Routes.
7. For New Route Key, enter sendmessage and confirm it.
8. Hook this too the sendmessage lambda
9. Hook up $connect and $disconnect. To the respective lambdas
10. Deploy the api to dev
11. wscat -c wss://{YOUR-API-ID}.execute-api.{YOUR-REGION}.amazonaws.com/{STAGE} (you will need to install wscat)
12. {"action":"sendmessage", "data":"hello world"}
13. Send users to thebeebs.uk/chat. Create you own version of this fiddle. 
14. Replace the API URL. Connect to the socket.
15. Save the CodePen and encourage others to visit the website.




