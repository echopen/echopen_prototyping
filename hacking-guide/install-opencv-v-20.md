# Install OpenCV

Master branch main algorothims of the Android App relies heavily on `OpenCV 3.1`. Indeed, a critical step is getting the data received in polar coordinates and we have to transform it in cartesian ones. `OpenCV` offers natively a routine to do that. Let's note that this piece of API knocks the `JNI`. That's the reason why in the preceding section, we invite the user to inform the `ndk.dir` in `local.propeties` file.

## OpenCV 3.1 installation \(by [Greg Sadetsky](https://github.com/gregsadetsky)\)

Note: OpenCV versions 3 and later should be used as OpenCV 2.4.11 for Android lacks the polar interpolation functions.

The integration of OpenCV into the Android project \(being developed in Android Studio\) is a bit error-prone, and differs from one version of OpenCV and from one version of Android Studio to another. Here are the steps that worked for OpenCV 3.1 & Android Studio 1.5.1, based on [these instructions](http://stackoverflow.com/a/17368359/426790) \(which seem to work for both OpenCV 2 & 3\):

* Download the `OpenCV 3.1` for Android from [opencv.org](http://opencv.org)
* Import the folder in Android Studio as an existing project
* Build everything in the project. Close the project.
* In the android-app project, choose Import Module, then select the `<opencv directory>/sdk/java/sdk.iml` file.
* Right-click the "app" in the project pane, choose "Open Module Settings"; under "Dependencies", click the "+" button, then choose "Module dependency", and then choose OpenCV
* from the OpenCV folder, copy the sdk/native/libs directory into your project's app/src/main, then rename it `jniLibs`



