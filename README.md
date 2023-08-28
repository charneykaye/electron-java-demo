# How to use node-java to include custom Java JAR in Electron app?

I want to build an Electron app that bundles a custom JAR (made in a Gradle project in a sub-folder of the project). The Electron app would use [`node-java`](https://github.com/joeferner/node-java) to call our custom API from TypeScript.

In an ideal implementation:

* TypeScript can parse custom types exposed by the Java code.
* TypeScript can call functions exposed by the Java code, passing in parameter values of said custom types and receiving deals of custom types.
* TypeScript can pass in callback functions as parameter values and receive callbacks from the Java code.

Our existing Java application uses floating-point computation and audio I/O, including local playback, writing files, streaming to YouTube, and VST. It also bundles a platform-specific ffmpeg via javacpp (javacv). Quite a handful to even consider rebuilding in Node.js and not necessarily appealing; Java has been good to us.

The biggest downside is debugging the complex low-level code, which is a great strength of Java. However, exposing a rich yet simple external API from our Java code can be a win-win for both the TypeScript UI developer consuming and Java audio developer producing and unit testing.

https://stackoverflow.com/questions/76989630/how-to-use-node-java-to-include-custom-java-jar-in-electron-app
