# SplashScreenTest

A sample project illustrating an issue with splash screen behavior when restoring after process death.

The project contains three Activities: MainActivity, SecondActivity and RoutingActivity. RoutingActivity is the launcher and can handle any routing or permission checks with the splash screen before launching the MainActivity if cannot completely remove this type of logic and place it in the Main Activity.

MainActivity consists of a single button that opens SecondActivity. 

Theme.xml changes here are SDK gated for 31+ 
