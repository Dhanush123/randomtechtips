# Table of Contents
1. [build and run android shortcut command](#build-and-run-android-shortcut-command)
2. [using console.log statements](#using-console.log-statements)

#### build and run android shortcut command
*This worked on OS X Terminal/Bash on 10/17/18. Prereqs: might need to [install Gradle](https://docs.gradle.org/current/userguide/installation.html)*
1. Make sure you're in root directory of React Native project
2. run ```cd android && ./gradlew && cd .. && react-native run-android```

#### using console.log statements
1. enable "Remote JS Debugging" in RN app, i.e. shake physical (Android) device to select option
2. in browser tab that's automatically opened from 1. go to console, ex: open [Developer Tools in Chrome](https://developers.google.com/web/tools/chrome-devtools/#get-started) (right click and "inspect page" or alt-cmd/ctrl-I) and go to "Console"
