# Actual best performances

[@Aurelie-Mutschler](https://github.com/Aurelie-Mutschler) [@nowami](https://www.gitbook.com/book/echopen/echopen_prototyping/edit#) obtained a performance of **90-100 fps **with OpenCV implementation

[@gregsadetsky](https://github.com/gregsadetsky) obtained a performance of **31-32 fps** with OpenCV implementation

[@loic-fejoz](https://github.com/loic-fejoz) obtained a performance of **10-12 fps** with hand-made scan conversion algo

## Challenge

The signal coming from the transducer, once preprocessed, can be represented by a double array with polar coordinates. We want to turn this array into cartesian coordinates and take into account that this converted array won't match the double "x-y" array consisting of the pixels of the screen of the phone.

You'll find detailed explanation [here](https://echopen.gitbooks.io/android-app/content/scan_conversion.html).

## Difficulty \(1-5\)

3

## MISSION

The incoming stream of raw data transmitted by the electronics must be converted into an image stream.

Data are coming in polar coordinates and there do not match the resolution of the screen. When we project these images on the screen with repect to the distances, converted data do not fit perfectly on the screen pixels.

Therefore, it is of importance to interpolate the raw signal to produce the data pixelated on the device screen, as shown in the diagram below.

![alt tag](http://wiki.echopen.org/images/2/29/Scan_Révision_.png)

### BEFORE / AFTER

![alt tag](http://wiki.echopen.org/images/4/4a/Before_scan_conversion.jpg)  
![alt tag](http://wiki.echopen.org/images/d/dd/After_scan_conversion.jpg)

### TRADEOFF

techniques already exist and must weigh the optimality of the interpolation with the real-time requirement. The image provided to the radiologist should be in real time.

We will retain the most effective method.

## REWARD

* Residency in our [Head Quarters](https://www.google.fr/maps/place/Point+Zéro+des+Routes+de+France/@48.8533289,2.3467055,17z/data=!4m13!1m7!3m6!1s0x47e671e10bc2d769:0x93bcbce92cd56429!2sParvis+Notre-Dame+-+Pl.+Jean-Paul+II,+75004+Paris!3b1!8m2!3d48.8533289!4d2.3488942!3m4!1s0x0:0x16a14abd23a6dd0d!8m2!3d48.8534033!4d2.3487836) located at the very center of Paris, on le Parvis de Notre Dame \(hosting and breakfast \)
* DevBox USB keys at your name, T-shirts and other Goodies 
* Mention on our Hall of fame of open sources dudes

## RESSOURCES

* You can find stuff, code and ideas [here](https://echopen.gitbooks.io/android-app/content/scan_conversion.html)
* librairies : OpenCV, specific to android lib OpenGL ES, basé sur  OpenGL ou autre
* bunch of other technics of interpolation exist : nearest neighboor, linear or bilinear interpolation, Open GL oriented method ... 
* clonables/forkables sourcesare hosted on [Github](https://github.com/echopen/PRJ-medtec_androidapp)
* Simulated data are available [here](https://github.com/echopen/PRJ-medtec_androidapp/tree/master/phantom)

### REPOS

Pull-requests submissions to [REPO](https://github.com/echopen/PRJ-medtec_androidapp)

## Current implementations

For now, several implementations have been tested

* On the master branch

  * The most effective is obtained through an RenderScript implementation. RenderScript do not allow to control the allocation to the GPU on the CPU processing power. But, on a smartphone \(Android 7.0. run in Galaxy Note 4\), the performance are satisfactory : 90-100fps

* On the [master branch](https://github.com/echopen/android-app/tree/master/app/src/main/java/com/echopen/asso/echopen)

  * The most effective was one upon a time \(v. 2.0. of the mobile app\) obtained through an [OpenCV implementation](https://echopen.gitbooks.io/android-app/content/scan_conversion.html#opencv). Indeed, OpenCV comes with a `linearPolar` method that enables polar to cartesian transform + an interpolation, which is precisely the ScanConversion trick. Let's precise that the type of interpolation can be choosen amongst several core implementation? Here, we use cubic interpolation.  

* On the [redpitaya\_udp\_data](https://github.com/echopen/android-app/tree/redpitaya_udp_data/app/src/main/java/com/echopen/asso/echopen)

  * Here, the scanconversion consists in a simple computation of a weight table that is then applied to the image to be converted. The processing time gain comes from the use of `OpenCL` library which is reached from the java app through the JNI.  

## SUDOERS

[@clecoued](https://github.com/clecoued) clement@echopen.org

[@nowami](https://github.com/benchoufi) nowami@echopen.org

## ECHPERTS

on github aka [@gregsadetsky](https://github.com/gregsadetsky), [@clecoued](https://github.com/clecoued)

