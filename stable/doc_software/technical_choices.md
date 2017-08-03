# Mobile application technology choice

We consider the pros and the cons of the following mainstream mobile application environment:

* native Android mobile application

  * \(+\) almost fully OpenSource framework
  * \(+\) large and reactive community

* native iOS mobile application

  * \(-\) proprietary environment
  * \(+\) large community

* cross-platform framework for mobile application

  * \(-\) no acces to low level interface, framework is not optimized for required optimizations on backend \(real time image rendering\) and front-end \(precise gestures\)

According to the points listed above we choose to implement first an **Android native mobile application**.

# Rendering pipeline technology choice

We have developed multiple **ScanConversion** filters _\(transformation from polar to cartesian coordinate in an image\)_ relying on differents technologies. This provided us good feedbacks on which technology we should use in order to get great performances to generate images from probe data.

## RenderScript

The best performances as of \(_07.05.17_\) are obtained with RenderScript. We achieved a performance of around 90-100 FPS for a 512x512 image. However, the limit is that the user does not control the allocation to GPU or CPU, and it seems that on most modern architectures, GPU is consistently used, which explains the high frame rate. In a near future, we would like to carry the scan conversion on Vulcan. For the moment \(_07.05.17_\), it is not widely supported or implemented on smartphones.

## OpenCV

To process scan conversion in our implementation, we use OpenCV. The OpenCV implementation scan conversion process is processed from the `opencv_interpolation()` in the `ScanConversion` class, under the `preproc` package.

OpenCV uses essentially the number of lines and the number of samples in order to run its scan conversion method `Imgproc.linearPolar` \(see [here](https://echopen.gitbooks.io/android-app/content/constants.html) for further informations about number of lines and of samples\).This method can be found in the `opencv_interpolation()` in the `ScanConversion` class.

We chose to use cubic interpolation, which is done by passing to method the `Imgproc.INTER_CUBIC` constant. There are many other scan conversion algorithms choice available. You'll find [here](http://www.swarthmore.edu/NatSci/mzucker1/opencv-2.4.10-docs/modules/imgproc/doc/geometric_transformations.html#cv.Resize) some of them such as `Imgproc.INTER_NEAREST` for nearest neighbour interpolation or `Imgproc.INTER_LINEAR` for bilinear interpolation

**To understand further the technological internals of the ultrasound probe, we refer the reader to our **[**start-kit**](https://echopen.gitbooks.io/starterkit/content/intro.md/readme.html)** GitBook**

We reach a performance of 30 FPS on a 512x512 image.

## Home-made scan conversion

The home made implementation scan conversion process is processed from the `compute_interpolation()` in the `ScanConversion` class, under the `preproc` package.

Contrary to the `OpenCV` implementation, there are much more paramaters to set. See [here](https://echopen.gitbooks.io/android-app/content/constants.html) for further informations about these parameters.

We reach a performance of 10-12 FPS on a 512x512 image.

## OLPC implementation

In 2007, some echOpen team members worked on an early implementation of an ultrasound probe on an [OLPC](https://fr.wikipedia.org/wiki/One_Laptop_per_Child) device. It faced scan conversion issues, you'll find [her.e](http://echopen.org/index.php/Scan_Conversion) a short story of this and some technical explanation about how the problem was tackled.

## List of authors

[Clément Le Couedic](https://github.com/clecoued)

[@nowami](https://github.com/benchoufi)

