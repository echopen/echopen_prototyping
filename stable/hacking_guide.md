# Hacking guide

## Installation

The code can be found [here](https://github.com/echopen/PRJ-medtec_androidapp)

The installation supposes the installation of the `NDK` \(see below\) and then running the app.

As an android app, you need to have a java JDK installed.  
We use [Gradle](http://gradle.org/) as builder tools. You need to install it too.  
Before being able to build the app, you need to specify, in a local.properties file, in the root folder, the Android SDK and NDK location, with sdk.dir and ndk.dir, example:

```
sdk.dir=/Path/To/Your/Android/sdk
ndk.dir=/Path/To/Your/android-ndk-r***
```

the current version of the \`NDK\` is `android-ndk-r14b`

## Running the app

After, you can launch the Gradle wrapper from the project directory, example:

`Mac/Linux`

```
./gradlew assembleDebug
```

`Windows`

```
gradlew.bat assembleDebug
```

To install on a device:

* Switch the Android device to dev mode \(generally, tap 7 times on "Version number" in parameters\)
* Enable USB debugging
* Connect the device to your computer \(with screen unlocked to see the prompt\)
* Accept the prompt on your device, to authorize your computer
* Launch gradlew with
  `installDebug`

**Note**: We currently use `android-sdk 25`, with `minSdkVersion 19,` and `targetSdkVersion 25`

## echOpen virtual machine

At this [link](https://drive.google.com/open?id=0B0V8htWBLPWBVEh6ZEJPcFpmTEU), you'll find an Ubuntu Virtual Machine. All the environment is set-up so as you don't have to worry about anything when running echOpen's Android App !

Here are two or three useful things to know to find your way

`username : echtopianpassword : echtopian`

The`echOpen Android app`is under`/home/echtopian`

To run it on Android Studio,

`/home/echtopian/Apps/android-studio/bin/studio.sh`

Android sdk path is`/home/echtopian/Android`

Made with Love ;\)

# List of authors

[Clément Le Couedic](https://www.gitbook.com/book/echopen/echopen_prototyping/edit#)

[@nowami](https://github.com/benchoufi)

