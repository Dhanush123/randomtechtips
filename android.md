# Table of Contents
1. [resolving react-native run-android compilation issue when created from ejected create-react-native-app](#resolving-react-native-run-android-compilation-issue-when-created-from-ejected-create-react-native-app)

#### resolving react-native run-android compilation issue when created from ejected create-react-native-app
*This worked on OS X w/ AS 3.2.1 and Gradle 4.10.2 on 10/16/18*
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
