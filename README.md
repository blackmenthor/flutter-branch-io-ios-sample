# flutter_branch_io_ios_sample

A new Flutter application implementing Branch IO on iOS with Swift 4.2.

## Getting Started

This is sample of a single Flutter app implementing Branch IO iOS SDK on iOS side, this implementation of Branch IO SDK comply with Flutter Branch IO Plugin https://pub.dartlang.org/packages/flutter_branch_io_plugin

## Disclaimer

I use this project as a sample because Branch IO's iOS SDK needs us to call Branch's SDK from inside Application's AppDelegate, but i haven't find a way override Flutter's base AppDelegate from inside a package. So the initialization part of Branch's SDK should be done manually in each project.

## Steps

- Open https://docs.branch.io/pages/apps/ios/
- Follow Branch's guideline for iOS project initialization on your Flutter's iOS project, you can do this by opening ios/Runner.xcodeproj/project.pbxproj then click open iOS module on XCode. If you don't have your Podfile file inside your iOS folder, follow this guide (https://stackoverflow.com/questions/51599686/flutter-podfile-and-pods-folders-not-created-in-ios-directory)
- Open your podfile and add this line in the very end of your podfile
```
  pod 'Branch'
```
- Open your AppDelegate.swift, then follow the following file inside this repository (ios/Runner/AppDelegate.swift)
- After you add Branch IO's implementation to Flutter's default AppDelegate.swift, you can catch the messages on Flutter's event channel with channel "flutter_branch_io/event". Or, you can just simply use my dart package at https://pub.dartlang.org/packages/flutter_branch_io_plugin
- Voila, you can intercept Branch IO's received message from the Dart's side of your application.