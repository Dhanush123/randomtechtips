#### resolving react-native run-android compilation issue when created from ejected create-react-native-app
1. add google() in buildscript and allproject repositories like this:
```Gradle
  // Top-level build file where you can add configuration options common to all sub-projects/modules.

buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.2.1'

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

allprojects {
    repositories {
        google()
        mavenLocal()
        jcenter()
        maven {
            // All of React Native (JS, Obj-C sources, Android binaries) is installed from npm
            url "$rootDir/../node_modules/react-native/android"
        }
    }
}
```
2. change react-native version in package.json to just a version #, like 0.55.4, instead of the zip file url that's there after ejecting
3. can delete node_modules folder and npm install to be safe, but probably isn't necessary
3. rebuild Android project (in Android Studio or w/ Gradle CLI)
4. NOW do react-native run-android
.
.
.
.
.
.
.
.
..
...
random text here
Build your app from the command line
You can execute all the build tasks available to your Android project using the Gradle wrapper command line tool. It's available as a batch file for Windows (gradlew.bat) and a shell script for Linux and Mac (gradlew.sh), and it's accessible from the root of each project you create with Android Studio.

To run a task with the wrapper, use one of the following commands from a Terminal window (from Android Studio, select View > Tool Windows > Terminal):

On Windows:
gradlew task-name
On Mac or Linux:
./gradlew task-name
To see a list of all available build tasks for your project, execute tasks:

gradlew tasks
The rest of this page describes the basics to build and run your app with the Gradle wrapper. For more information about how to set up your Android build, see Configure your build.

If you'd prefer to use the Android Studio tools instead of the command line tools, see Build and run your app.

About build types
By default, there are two build types available for every Android app: one for debugging your app—the debug build—and one for releasing your app to users—the release build. The resulting output from each build must be signed with a certificate before you can deploy your app to a device. The debug build is automatically signed with a debug key provided by the SDK tools (it's insecure and you cannot publish with it to the Google Play Store), and the release build must be signed with your own private key.

If you want to build your app for release, it's important that you first read Sign your app. That page describes the procedure for generating a private key and then using it to sign your app. If you're just getting started, however, you can quickly run your apps on an emulator or a connected device by building a debug APK.
[link](#resolving-react-native-run-android-compilation-issue-when-created-from-ejected-create-react-native-app)
