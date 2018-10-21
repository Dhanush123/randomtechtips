# Table of Contents
1. [build and run android shortcut command](#build-and-run-android-shortcut-command)
2. [remote js debugging](#remote-js-debugging)
3. [advanced debugging](#advanced-debugging)
4. [additional debug resources](#additional-debug-resources)
5. [linking libraries](#linking-libraries)

#### build and run android shortcut command
*This worked on OS X Terminal/Bash on 10/17/18. Prereqs: might need to [install Gradle](https://docs.gradle.org/current/userguide/installation.html)*
1. Make sure you're in root directory of React Native project
2. run ```cd android && ./gradlew && cd .. && react-native run-android```

#### remote js debugging
*similar steps to put brakepoints in code in CDTs*
1. enable "Remote JS Debugging" in RN app, i.e. shake physical (Android) device to select option
2. in browser tab that's automatically opened from 1. go to console, ex: open [Developer Tools in Chrome](https://developers.google.com/web/tools/chrome-devtools/#get-started) (right click and "inspect page" or alt-cmd/ctrl-I)
 * go to "Console" for console.log statements
 * go to "Source" for seeing files and putting breakpoints in code

#### advanced debugging
*Assuming have downloaded [React Native Debugger](https://github.com/jhen0409/react-native-debugger) and enabled ["Remote JS Debugging"](#remote-js-debugging)*
* Use RND to inspect and modify elements, see console.log statements, and see files/"Source", looks similar to CDTs
* has Redux inspection capabilities, similar to Redux debugger Chrome Extension
* can't use this at the same time as the "Remote JS Debugging" feature

#### additional debug resources
* [official FB RN docs](https://facebook.github.io/react-native/docs/debugging)

#### linking libraries
*Assuming you've installed [react-native cli](https://github.com/facebook/react-native#readme)*
* some libraries, like [React Native Vector Icon](https://github.com/oblador/react-native-vector-icons), require linking due to their interaction with native code, and so run ```react-native link``` to auto link all libraries that require linking
