# Firebase Cloud Messaging (FCM) Implementation

The Flutter application in the given code snippet implements Firebase Cloud Messaging (FCM), which enables the app to receive messages and notifications from a server or the Firebase Console.
 
## Import Statements
The following packages are imported:
1. `package:flutter/material.dart` - provides the core Flutter framework.
2. `package:firebase_core/firebase_core.dart` - Flutter plug-in for Firebase.
3. `package:firebase_messaging/firebase_messaging.dart` - Flutter plug-in for Firebase Cloud Messaging.
4. `package:flutter_local_notifications/flutter_local_notifications.dart` - Flutter plug-in for local notifications on Android and iOS.

## Variables
- `channel` - an instance of the `AndroidNotificationChannel` to configure the channel for notifications on Android.
- `flutterLocalNotificationsPlugin` - an instance of the `FlutterLocalNotificationsPlugin` to implement local notifications within the app.
- `_counter` - an integer to keep track of the number of times the button is pressed.

## Methods
- `_firebaseMessagingBackgroundHandler()` - a method that is called whenever a new message/notification is received by the app while it is in the background. It initializes Firebase and then prints a message to the console indicating the message ID.
- `main()` - the primary entry point for the Flutter app. It initializes Firebase, sets up a Firebase Messaging Handler, and initializes the local notification channel before running the `MyApp` widget.
- `MyHomePageState.initState()` - an initialization method to set up Firebase Messaging listeners to receive messages and notifications and trigger the display of a local notification when a new notification is received.
- `MyHomePageState.showNotification()` - a method to show a new local notification each time it is called. It updates the counter and triggers the `FlutterLocalNotificationsPlugin.show()` method to display the new notification.
- `MyHomePageState.build()` - the method that builds the user interface for the application.

## Widget tree
- `MyApp` - the outermost widget that builds the MaterialApp widget.
- `MyHomePage` - a stateful widget that builds the main page of the app.
  - `Scaffold` - a widget to create the app's scaffold, which provides a basic visual structure of the application.
    - `AppBar` - a widget that displays the app's title in the app bar along with a notification Icon button.
    - `Center` - centers the `Column` widget in the middle of the scaffold
      - `Column` - a widget that arranges its children in a vertical manner. 
        - Two `Text` widgets - one static and one that updates with the value of `_counter`.
  - `floatingActionButton` - a widget that displays a circular button used to trigger the `showNotification()` method.
