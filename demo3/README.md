# Real-time with Amplify

Please watch the Video Demo 3 in Work Docs. 

Before the demo:
Clone the project https://github.com/aws-samples/aws-mobile-appsync-events-starter-react

Run `yarn` at the base of the folder and `yarn start` before the talk to ensure the app is working.

1. Go the the AWS console
2. Open the AppSync Console
3. Create New Api
4. Choose: Start from a sample project, Event App
5. Accept the default name
6. Wait 2-3 mins for the API to create. During this time explain that the system is creating an API and the dynamodb tables used to persist data. 
8. Show that a GraphQL Schema has been created.
8. Point out that there is a commentOnEvent mutation. 
8. Show that there is a subscribeToEventComments subscription that clients can subscribe to to be informed when users add comments,
7. In the left hand column, Select the API Name this will take you to the Getting Stared page.
8. Go to the JavaScript pane.
8. Show you can download the React event app.
8. Download the config file and save it the src folder of the project.
9. Run yarn start a the base of the project.
9. Navigate to the react application. Localhost:3000
9. Add an event
9. Navigate to that event and add a comment 'One'
9. Open another tab and load the app. Go to the comments of the event. Show that the One has been added to the event.
9. With both windows open add a second comment 'two' and show that both windows have been updated with the new comment. The system was updated in real time.
9. Explain Once the page loads, EventComments sets up a GraphQL subscription using ./GraphQL/SubscriptionEventComments to display any new comments on an event in realtime.
9. Show js that does this if you wish
9. Optionally go the the query tab in App Sync and start the following query

```
subscription startSubscription {
  subscribeToEventComments(eventId: "") {
    eventId
    commentId
  }
}
```

You will need to get the ID first of the event by calleg

```
query ListEvents {
  listEvents {
    items {
      id
      name
    }
  }
}
```
23. You can then add a comment to the app and show that the event fires in the console and retuns data to the subscriber.