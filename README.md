# notils [![CI status](https://ci.novoda.com/buildStatus/icon?job=notils)](https://ci.novoda.com/job/notils/lastBuild/console) [![Download from Bintray](https://api.bintray.com/packages/novoda/maven/notils-android/images/download.svg)](https://bintray.com/novoda/maven/notils-android/_latestVersion) [![Apache 2.0 Licence](https://img.shields.io/github/license/novoda/notils.svg)](https://github.com/novoda/notils/blob/master/LICENSE.txt)

Never again need a .utils. package yur scurvy sea dogs!

Notils comes in two modules - `notils-java` contains classes that don't depend on anything from the Android SDK, while `notils-android` contains classes that do.

## Description

notils contains a set of common classes that we use in our projects:

  - `AndroidUtils`, for showing the keyboard, checking running services, etc.
  - `ClassCaster` - to help with listeners between Activitys & Fragments
  - No need to cast when finding Fragments
  - No need to double type your types when creating collections
  - Simple Fade animations in & out done for you
  - Simple `Log` to give to give automatic details of where the Log executed
  - `StrictMode` Management - enable strict mode in one line
  - `WebViews`, allowing custom loading of different scenarios (raw assets, external urls)
  - `ToastDisplayers` for saner displaying of Toast notifications
  - `SimpleDateFormatThreadSafe` allowing you to use date formatting from multiple threads
  - `DeveloperError` - custom exceptions for explicit declaration / faster feedback when something goes wrong
  - `SimpleTextWatcher` - simple implementation of `android.text.TextWatcher` with stub implementations of each method
  - `QueryUtils` - easily create placeholders for ContentResolver operations selection
  - [DeviceDetection](https://github.com/novoda/notils/blob/master/android/src/main/java/com/novoda/notils/devicedetection/DeviceDetection.java) - to detect whether the user has `Amazon` or `Intel x86` devices.
  - [AndroidVersion](https://github.com/novoda/notils/blob/master/android/src/main/java/com/novoda/notils/devicedetection/AndroidVersion.java) - to check the Android version in a nicer way.


## Adding to your project

To start using this library, add these lines to the `build.gradle` of your project:

```groovy
repositories {
    jcenter()
}

dependencies {
    compile 'com.novoda:notils-java:3.1.1'
    compile 'com.novoda:notils-android:3.1.1'
}
```


## Simple usage

Here are a few examples.

 * Use the `Views` class to avoid casting your views over and over!
 
 ```java
 UserFragment userFragment = Fragments.findFragmentById(fragmentmanager, R.id.userFragment);
 ```

 * Use `DeveloperError` to let other devs know a problem in the code or prevent potential issues:
 
 ```java
 switch (menuOptionId) {
     case R.id.menu_take_picture:
         // Start the camera...
     break;
     case R.id.menu_from_gallery:
         // Open the gallery...
     break;
     default:
         throw new DeveloperError("Unhandled case in switch statement!");
 }
 ```
 
 * Object-oriented Toasts!
 
 ```java
 Toaster toaster = new Toaster(context);
 toaster.popToast("Good morning!"); // Short toast
 toaster.popBurntToast("Good night!"); // Long toast
 toaster.dropInBath(); // Cancells all active toasts this toaster created
 ```
 
 * Check the javadoc for more! The package structure allows you to easily see what's in each package.


## Links

Here are a list of useful links:

 * We always welcome people to contribute new features or bug fixes, [here is how](https://github.com/novoda/novoda/blob/master/CONTRIBUTING.md)
 * If you have a problem check the [Issues Page](https://github.com/novoda/notils/issues) first to see if we are working on it
 * For further usage or to delve more deeply checkout the [Project Wiki](https://github.com/novoda/notils/wiki)
 * Looking for community help, browse the already asked [Stack Overflow Questions](http://stackoverflow.com/questions/tagged/support-notils) or use the tag: `support-notils` when posting a new question
