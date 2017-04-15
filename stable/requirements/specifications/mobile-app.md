\# Use cases Android App

1 Welcoming

1. 1 SplashScreen

2 echO Exam

2.1 user accesses a full screen displaying the image caught by the ultrasound probe

2.2 user can manipulate image

2.2.1 user can adjust image contrast in order to get a better look to details inside organs. This helps the operator to detect anomalies, often revealed by contrast breaks

\# Functional Specs Android App

1 Welcoming

1. 1 SplashScreen

2. echO Exam

2.1 user accesses a screen displaying the image caught by the ultrasound probe

\* the image is a full screen image

\* the image frame rates relies heavily on the what is transmitted by the hardware. today, the frame-rate is 5 frames per second \(fps\). In the current hardware configuration

\* the image is displayed in a conic shape, due to ScanConversion processing. This is done through

```
\* a custom algorithm 

\* or a through a GPU-based framework
```

\* the image has been pre-filtered to remove noise, This is done through

```
\* a detection envelope algorithm corresponding to Hilbert transform implementation
```

2.2 user can manipulate image

2.2.1 user can adjust image contrast in order to get a better look to details inside organs.

* This helps the operator to detect anomalies, often revealed by contrast breaks

* Contrast can be adjusted by selecting a customized intensity-to-pixels linear or exponential look-up table.

* The image intensity can also be amplified uniformally through a gain filter

3.Communication with echOpen hardware Device

image data are received as pixels streams in TCP, or local \(from an asset file\), format

* the are two modes

```
\* the TCP mode, the raw data come from the hardware as stream of pixels

\* the first image thrown by the hardware carries as its first bytes the header information 

\* the first 2 bytes of the packet corresponds to the number of lines
```

* the local mode,

```
\* the image are fetched from a local folder and so emulates the real ones

\* image filters are implemented in order to improve contrast and image quality. These settings will then be reported in the production app, without letting the user to modify them -&gt; clement for more details
```

* the raw data are received from the transducer, before envelope detection and ScanConversion

* each image displays a predefined number of lines, 64 lines, each of which carries a predefined number of samples : 1478

* each image pixel is encoded with 2 bytes



