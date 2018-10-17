* **resolving react-native run-android compilation issue when created from ejected create-react-native-app**:
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
