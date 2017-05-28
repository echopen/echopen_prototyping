This page is an adaptation of a scan conversion that worked on a [OLPC](https://fr.wikipedia.org/wiki/One_Laptop_per_Child)!

## Presentation of the scan conversion

The Scan Conversion allows one to recreate a clinical image from a set of data sent by a probe. The received image depends on the geometry of the probe. This process intends to recreate the 'real' image.

An ultrasound beamformer generates coherently summed image data in polar format while the standard TV raster display is rectangular. Hence, polar to Cartesian scan conversion is necessary before display. A combined design scheme for polar to Cartesian scan conversion using nearest neighbor and linear interpolations has been implemented which optimizes both image quality and hardware requirement.  
The scan converter takes polar data as input and produces corresponding rectangular data which is used for image formation. The radial distance becomes somewhat larger as one moves deeper into the body and this produces serious artifacts in the image called Moiré artifacts. Hence interpolation becomes necessary. The nearest neighbor interpolation is a simple method although it makes the image blocky. On the other hand, linear interpolation needs a few computations but is free from these artifacts in the far field.

![ alt tag](http://wiki.echopen.org/images/c/c6/Image02.jpg)

Indeed, the probe stores a series of sampled scan-lines, whatever the geometry of the scanned area.

Which can be represented with clinical images such as :

![alt tag](http://wiki.echopen.org/images/7/7d/Image04.png)  
![alt tag](http://wiki.echopen.org/images/b/b8/Image03.png)

These two images are before/after scan conversion of an image of a liver

For the [OLPC](https://fr.wikipedia.org/wiki/One_Laptop_per_Child), we had to build our own scan conversion algorithms, because the versions that already exist were too heavy.

We studied a C++ scan conversion program, but it was very complicated. So we mainly used a Matlab version that we translated into a C program.  
All the algorithm used in this document are based on 8 bits pixels values. For the sake of the programing, and in order to allow the use of colors, the colors are declared in a color table. Out of 256 colors, it is possible to create a 224 greyscale palette and a 32 colors palette.

In order to display a two-dimensional image, we must re-sample these scan-lines onto an array of actual pixel locations that will be output to the display. Therefore, we will have to calculate the value of each pixel in functions of the input’s pixels value. For this, we have three different options:

### The Nearest Neighbor algorithm \(NN\)

This algorithm just consists in a simple local transformation of a Cartesian space into a polar space. One can just assign the value of a pixel from the nearest pixel already mapped in the pre scan converted image.

### The 2tap conversion

This algorithm is a little more complicated. During the transformation, it also takes into account not only the nearest pixel, but also its immediate neighbors. Then we make an average with the four values according to the distance to the final pixel. This way the image is a little bit more clinical looking.

### The 4tap conversion

It is the same principle as the 2Tap, but instead of considering 4 pixels \(2x2\), we take 8 pixels \(4 in the width and 2 in the height\) and we make an average with a cardinal sinus function. But, considering the gain in quality, this algorithm needs too much computation and is too slow on the [OLPC](https://fr.wikipedia.org/wiki/One_Laptop_per_Child).

## Current algo choice

### RenderScript

The best performances are at the moment of the writing \(_07.05.17_\) are obtained with RenderScript. We achieved a performance of around 90-100 fps. however the limit is that the user don't control the allocation to GPU or CPU, and it seems that on most modern architecture, GPU is consistently used, which explains the high frame rate. In a near future, we would like to carry the scan conversion on Vulcan. For the moment \(_07.05.17_\), it is not widely supported or implemented on smartphones.

### OpenCV

To process scan conversion in our implementation, we use OpenCV. The OpenCV implementation scan conversion process is processed from the `opencv_interpolation()` in the `ScanConversion` class, under the `preproc` package.

OpenCV uses essentially the number of lines and the number of samples in order to run its scan conversion method `Imgproc.linearPolar` \(see [here](https://echopen.gitbooks.io/android-app/content/constants.html) for further informations about number of lines and of samples\).This method can be found in the `opencv_interpolation()` in the `ScanConversion` class.

We chose to use cubic interpolation, which is done by passing to method the `Imgproc.INTER_CUBIC` constant. There are many other scan conversion algorithms choice available. You'll find [here](http://www.swarthmore.edu/NatSci/mzucker1/opencv-2.4.10-docs/modules/imgproc/doc/geometric_transformations.html#cv.Resize) some of them such as `Imgproc.INTER_NEAREST` for nearest neighboor interpolation or `Imgproc.INTER_LINEAR` for bilinear interpolation

**To understand further the technological internals of the ultrasound probe, we refer the reader to our **[**start-kit**](https://echopen.gitbooks.io/starterkit/content/intro.md/readme.html)** GitBook**

### Home-made scan conversion

The home made implementation scan conversion process is processed from the `compute_interpolation()` in the `ScanConversion` class, under the `preproc` package.

Contrary to the `OpenCV`  implementation, there are much more paramaters to set. See [here](https://echopen.gitbooks.io/android-app/content/constants.html) for further informations about these parameters.

### OLPC implementation

In 2007, some echOpen's team worked on an early implementation of an ultrasound probe on an [OLPC](https://fr.wikipedia.org/wiki/One_Laptop_per_Child) device. It had to be faced scan conversion issue, you'll find [her.e](http://echopen.org/index.php/Scan_Conversion) a short story of this an some technical explanation about how the problem was tackled.

