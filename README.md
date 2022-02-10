# SplashScreenTest

A sample project with the [Splash Screen API](https://developer.android.com/guide/topics/ui/splash-screen) demonstrating keeping a routing activity when it isn't feasible to move to a singular activity with subcomponents. 
Use ```SplashScreen#setKeepOnScreenCondition``` to keep the routing activity in place but stop it from rendering. Doing so transfers the splash screen to the next activity and allows for a smooth transition ([relevant documentation](https://developer.android.com/guide/topics/ui/splash-screen/migrate#prevent_the_custom_activity_from_displaying)).

The project contains three Activities: MainActivity, SecondActivity and RoutingActivity. RoutingActivity is the launcher and can handle any routing or permission checks with the splash screen before launching the MainActivity if cannot completely remove this type of logic and place it in the Main Activity.

MainActivity consists of a single button that opens SecondActivity. 

Theme.xml changes here are SDK gated for 31+ 
