# NativeScript

[![Version](https://img.shields.io/npm/v/nativescript.svg?label=npm)](https://www.npmjs.com/package/nativescript)
<a href="https://play.google.com/store/apps/details?id=org.nativescript.preview.android"><img height="20.5px" src="https://raw.githubusercontent.com/tomayac/SVGcode/main/public/badges/play-store.svg"></a>

NativeScript provides platform APIs directly to the JavaScript runtime (with strong types) for a rich TypeScript development experience.

### Adding custom native code to a project
NativeScript allows you to access any native API anytime in your app.

### Adding Java/Kotlin Code to an application

### Adding native code to an application
There are different ways to add native code to an Android application. 

You can add **`.jar`** and **`.aar`** 
files, or Java/Kotlin source files in 
**`App_Resources/Android/libs`** and 
**`App_Resources/Android/src`** respectively.

#### Example

```bash
App_Resources/ 
├─ Android/ 
│  ├─ app.gradle 
│  ├─ libs/ 
│  │  ├─ HelloAndroidLib.aar # Android Archive 
│  │  └─ HelloJavaLib.jar # Java Archive 
│  └─ src/ 
│     └─ main/ 
│       ├─ java/ 
│       │  ├─ com/example/HelloKotlin.kt # Kotlin source code 
│       │  └─ com/example/HelloJava.java # Java source code 
│       └─ res/ 
└─ ... more
```

### Adding Java code 

Define the java file in
`App_Resources/Android/src/main/java`.

```bash
// HelloJava.java package com.example; 

public class HelloJava { 
  public String getString() { 
    return "Hello from Java!"; 
  } 
}
```
Given the example above, your JavaScript or TypeScript code can reference the Java code by using the full class name:

```bash
const helloJava = new com.example.HelloJava() 
console.log('Java says: ' + helloJava.getString()) 
// prints: Java says: Hello from Java!
```
```bash
Note

When using TypeScript, you 
may need to "generate typings",
or alternatively declare the top 
level package name as any.

// typescriptdeclare const com: any
```
### Adding Kotlin code 

#### Configuring Kotlin 
**Enable Kotlin**

When using Kotlin, it must be enabled first.

Set `useKotlin=true` in `App_Resources/Android/gradle.properties` (create the file if it doesn't exist).

```bash
useKotlin=true
```
**Configure Kotlin version**

Configure the version of Kotlin to use in the application in 
`App_Resources/Android
before-plugins.gradle` (create the file if it doesn't exist).

```bash
project.ext { kotlinVersion = "1.9.10" }
```
**Using Kotlin**

Define the kotlin file in 
`App_Resources/Android/src/main/java`.

```bash
// HelloKotlin.kt package com.example class HelloKotlin { val hello = "Hello from Kotlin!" }
```
Given the example above, your JavaScript or TypeScript code can reference the Kotlin code by using the full class name:

```bash
const helloKotlin = new com.example.HelloKotlin() console.log('Kotlin says: ' + helloKotlin.hello) // prints: Kotlin says: Hello from Kotlin!
```
```bash
Note

When using TypeScript, you 
may need to "generate typings",
or alternatively declare the top 
level package name as any.

// typescriptdeclare const com: any
```
### Other Reference

## NativeScript Preview 

- Install [NativeScript Preview](https://preview.nativescript.org)
and start developing mobile app with only
one additional dependency. A browser. 

- Installing the [NativeScript CLI](https://www.npmjs.com/package/nativescript) 
**`npm install -g nativescript`.**
