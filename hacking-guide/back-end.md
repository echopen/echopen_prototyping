# constants

Setting constants is critical for the code to work. These are set in the `Constants.PreProcParam` static class.

The 3 key constants to be set are the number of lines, the number of samples per line and the bounded values of the image size \(width and height\).

* The tranducer, which is the technical master piece of an ultrasound probe, lives inside on a mecanical device that swipes left and right the zone to be explored. In the course of this pendulum movement, the tranducer emits and receives mecanical ultrasound waves. And, for one acquisition of one image, these waves are emited step by step to cover an angle of around 60 degrees, each step corresponding to a precise angle. Then the number of lines account for the number of steps.

* When the ultrasound waves echoes are received by the transducer, our device samples a number of data corresponding to a precise frequency, the inverse of which correspond to the number of samples per line. Let's remark that since the sound propagation speed is constant, this frequency can be translated into distances, and this is the key that enables to use data to locate and display the organs.

* The image size are denoted `N_x` and `N_z`. They are currently both set to `512`.

These constants are found under the `Constants.PreProcParam` static class and there are critical for the Scan Conversion algorithm to take place. Conventionnaly, the are named and `*_IMG_DATA` and `*_NUM_SAMPLES`. The star depending on the way the data is processed : locally, from `TCP` or from `UDP`.

For local usage, the data are taken from the `assets/data/raw_data` folder and the `data_phantom.csv` needs these constants

```
public static final int LOCAL_NUM_SAMPLES = 511;

public static final int LOCAL_IMG_DATA = 120;
```

_**The suffix **_`_IMG_DATA`_** can be misleading, indeed the number of image lines to be processed has same value. This is an abuse of notation and should be changed.**_

for `TCP`,`UDP`, you should adjust the `TCP_NUM_SAMPLES, UDP_NUM_SAMPLES,TCP_IMG_DATA, UDP_IMG_DATA` accordingly to your hardware settings choice. In our current implementation we use `TCP_NUM_SAMPLES=1024, UDP_NUM_SAMPLES= 1052,...`.

There are basically two implementations of Scan Conversion.

## Home-made scan conversion

The home made implementation scan conversion process is processed from the `compute_interpolation()` in the `ScanConversion` class, under the `preproc` package.

Contrary to the `OpenCV`  implementation, there are much more paramaters to set. Here there are with a quick documentation in comment.

```
/* speed of sound in m.s^{—1} */
        public static final int SPEED_OF_SOUND = 1540;

        /* speed of acoustic wave in m. s^{-1} */
        public static final int SPEED_OF_ACOUSTIC_WAVE = 1480;

        /* sampling frequency in Hz */
        public static final int SAMPLING_FREQUENCY = (int) 125 /32 * (int) Math.pow(10,6); //deprecated sampling frequency

        public static final int SAMPLING_FREQUENCY_BIS = (int) 125 /8 * (int) Math.pow(10,6); //real sampling frequency

        public static final double ADC_FREQUENCY_CLOCK = 125 * Math.pow(10, 6);

        public static final int N_x = 512;

        public static final int N_z = 512;

        public static final int NUM_LINES = 64;

        public static final float IMAGE_SIZE = (float) 0.201;

        /* image width in rad */
        public static final double IMAGE_WIDTH = 0.5 * Math.PI;

        public static int NUM_SAMPLES = 1024;

        public static int NUM_IMG_DATA = 64;

        public static Integer NUM_SAMPLES_PER_LINE = 1689;

        public static Integer NUM_LINES_PER_IMAGE = 64;

        public static Integer NUM_BYTES_PER_SAMPLE = 2;
        /* this parameter takes in account the size of the image in order to wrap it properly in the OpenCV MAT */
        public static int SCALE_IMG_FACTOR = 1;

        /* Settings for displaying a local pixel file : data/raw_data/data_phantom.csv*/
        public static final int LOCAL_NUM_SAMPLES = 511;

        public static final int LOCAL_IMG_DATA = 120;

        public static final int LOCAL_SCALE_IMG_FACTOR = 1;

        /* Settings for TCP protocol */
        public static final int TCP_NUM_SAMPLES = 2048;

        /* Settings pixel intensity range */
        public static final int MIN_INTENSITY_PIXEL_VALUE = 0;
        public static final int MAX_INTENSITY_PIXEL_VALUE = 65535;

        public static final int TCP_IMG_DATA = 64;

        public static final int TCP_SCALE_IMG_FACTOR = 2;

        /* Settings for UDP protocol */
        public static final int UDP_NUM_SAMPLES = 1052;

        public static final int UDP_IMG_DATA = 60;

        public static final int UDP_SCALE_IMG_FACTOR = 1;


        public static final int UDP_NUM_UDP_PACKET_CHUNKS = 4;

        public static final double RADIAL_IMG_INIT = 0.013;

        /* depth for start of data in m (meters) */
        public static final double RADIAL_DATA_INIT = SPEED_OF_SOUND/2*1/(double) SAMPLING_FREQUENCY;

        public static final int ANGLE_INIT = 0;

        /* no dimension param */
        public static final float STEP_ANGLE_INIT = (float) (IMAGE_WIDTH/NUM_LINES);

        /* sampling interval for data in m (meters)*/
        public static final double STEP_RADIAL_INIT = SPEED_OF_SOUND/2*1/(double) SAMPLING_FREQUENCY;

        public static final int SCALE_FACTOR = 1;

        public static final int tmp_SAMPLING_POINTS = 1052;

        public static final int tmp_NUM_UDP_PACKET_CHUNKS = 4;

        public static final int opencv_RELATIVE_ANGLE = 512;

        public static final double BAND_PASS_FILTER_LOWER_CUTOFF_FREQUENCY = 2 * Math.pow(10, 6);

        public static final double BAND_PASS_FILTER_UPPER_CUTOFF_FREQUENCY = 5 * Math.pow(10, 6);
```

## OpenCV

The OpenCV implementation scan conversion process is processed from the `opencv_interpolation()` in the `ScanConversion` class, under the `preproc` package.

OpenCV uses essentially the number of lines and the number of samples in order to run its scan conversion method `Imgproc.linearPolar`. This method can be found in the `opencv_interpolation()` in the `ScanConversion` class

**To understand further the technological internals of the ultrasound probe, we refer the reader to our **[**start-kit**](https://echopen.gitbooks.io/echopen_prototyping/content/)** GitBook**

