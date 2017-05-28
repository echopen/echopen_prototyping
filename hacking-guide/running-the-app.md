After, you can launch the Gradle wrapper from the project directory, example:

`Mac/Linux`

```
./gradlew assembleDebug

```

`Windows`

```
gradlew.bat assembleDebug

```

**Note**: some users experienced some issues with running the code on Windows machine, check this `issue` on GitHub 

To install on a device:

* Switch the Android device to dev mode \(generally, tap 7 times on "Version number" in parameters\)
* Enable USB debugging
* Connect the device to your computer \(with screen unlocked to see the prompt\)
* Accept the prompt on your device, to authorize your computer
* Launch gradlew with
  `installDebug`

**Note**: We currently use `android-sdk 25`, with `minSdkVersion 19,` and `targetSdkVersion 25`

# How to contribute {#how-to-contribute}

Report a bug, ask for features, for all of this, we use[Github issues](https://github.com/echopen/android-app/issues)

You can fork the projet, add something or fix a bug and make a pull request. We'll review the code as quick as possible.

