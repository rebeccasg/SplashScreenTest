# SplashScreenTest

A sample project illustrating an issue with splash screen behavior when restoring after process death.

The project contains three Activities: MainActivity, SecondActivity and RoutingActivity. RoutingActivity is the launcher and can handle any routing or permission checks with the splash screen before launching the MainActivity. MainActivity consists of a single button that opens SecondActivity. 

To reproduce the issue if do not have the Routing Activity after process death:

1. Build and run the app on an Android 12 device. Splash screen with yellow background and a chat icon will be shown (chat icon is clipped, but that's irrelevant to this issue)
2. Tap the button on MainActivity to open SecondActivity
3. Tap the Home button to background the app
4. Kill the app process with the "Terminate" button in the Android Studio Logcat window
5. Reopen the app. SecondActivity will be restored
6. Tap the back button to return to MainActivity

**EXPECTED**: MainActivity is restored<br/>
**ACTUAL**: The splash screen is shown, then MainActivity is restored

I would not expect the splash screen to be shown at this point, as this is not an "entry point" to the app. App restoration should be completely transparent to the user, and they have already resumed the app from their perspective. I have not been able to reproduce this behavior on a pre-Android 12 device.

Note: this behavior is also easy to reproduce with "Don't keep Activities" enabled in Developer Options.
