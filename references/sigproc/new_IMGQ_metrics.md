# Image Quality Assessment

## Introduction

Being able to measure the quality of the image displayed by our device is of crucial importance. It would allow the community to quantify the progress between two versions of the device, but it may also be useful to prove that the echOpen device is reliable. Even if some parameters such as the framerate or the transducer’s bandwidth can be measured and are known for having an impact on the image quality, a global approach taking the whole system into account is necessary.

However, quantifying the quality of an ultrasound imaging system is difficult as no objective criteria has yet been fully developed and accepted for the evaluation of clinical image quality. For the moment, the evaluation of the quality of a clinical image is generally performed subjectively by a specialist, even if a few techniques providing relevant measures have been developed in the past years. 

The first point of this document is a presentation of the criteria that may be used to characterize the image quality and the corresponding parameters, the second one is about existing methods that are used for image quality assessment, and the last one is about the relevance of those different techniques in the echOpen project. It must be pointed out that clinical trials are expensive and time consuming. They should be used for the final device only, in order to get medical certifications.


## Criteria to characterize the quality of an ultrasound image 
Some of the relevevant parameters for the quality assesment are described in the following list. Their values are primarily affected by the properties of the transducer and the ADC(analog to digital device), by the pulser and the amplifier and by the signal processing.

### Spatial resolution
In ultrasound imaging the spatial resolution is usually divided into two concepts. Lateral resolution is the capability to resolve details from each other when they are near each other on lines perpendicular to the ultrasound beam. Accordingly, axial resolution is the capability to resolve details that are near each other on lines parallel to the ultrasound beam. A third resolution called elevation resolution defines how thin a layer the transducer is capable of separating from adjacent layers in the object. The spatial resolution may be affected by some of the transducer’s properties such as its geometry, as it affects the beam width (for the lateral resolution) or its bandwidth that may change the pulse’s length (for the axial resolution). The frequency of the transducers also changes the depth at which the better resolution is observed.

### Contrast resolution
The contrast resolution is a measure of the ability to distinguish objects that have close acoustic properties. It can correspond to the detection of different tissues, of anechoic objects (objects that are free from echoes and reverberation such as cysts) or scattering objects such as tumours. 

### Time resolution
The temporal resolution is a measure of the fastest object motion that can be detected by the device. It is relative to the transducer and the framerate.

### Sensitivity
Sensitivity is a measure of the minimum detectable inhomogeneity. It can be quantified either by the Signal to Noise Ratio (SNR) or by the penetration, the depth at which the SNR falls below 6dB.


### Uniformity
Before being digitalized and analysed, the received signal is amplified by a Time Gain Compensation device. Signals coming from deeper tissue/organ interfaces are amplified more than others in order to compensate the attenuation that occurs all along the waves’ way. Yet, the quality or the simple fact that it also amplifies noise affects the image uniformity.


## Methods and techniques to quantify those criteria
### Image quality measure based on error sensitivity
Mean Squared Error (MSE) is the most commonly used image quality measure. The goal of this measure is to compare two images by providing the quantitative score that describes the degree of similarity or the level of distortion/error between the two images. MSE is easy to calculate, memory less and it has a clear physical meaning as it defines the energy of the noise image.
The MSE can be converted into Peak Signal to Noise Ratio (PSNR). MSE and PSNR are easy to calculate, memory less and have a clear physical meaning (MSE is a measure of the energy of the image and PSNR defines the energy of the noise image. However, those measures may not correspond to human perception because digital pixel values may not exactly represent the light stimulus entering the eye, because the summation process implemented in those techniques has little to do with the way our brain perceives a distortion between two images and because two distorted image signals with the same amount of error energy may have very different structure of errors.

### Tissue mimicking phantoms
A tissue mimicking phantom is an object designed to test the ability of ultrasound scanners to detect particular objects. It is composed of materials that can reproduce the acoustic properties of human tissues. Tissue mimicking phantoms are interesting as we know their geometry. 
There are some areas in the object where the properties of the materials are slightly different, and the operator can test whether the limits of those areas are detected or not (contrast resolution). The spatial resolution can be measured by placing a series of two points that can be detected by the scanner close to each other, but at different distances from each other. Then you just have to take a look on the screen to see which points are still distinguishable from their counterpart. You can also compare the values of the neighbouring pixels.

### The Resolution Integral
The Resolution Integral is a mathematical transformation that produces a single figure of merit for image quality from individual measurements of resolution over a range of depths. The idea is that a good image is correlated with a narrow beam width and a good penetration into soft tissues, so a notional metric of performance could calculated as the ratio R = Penetration / Beam Width. For weakly focused imaging beams, the variation of ultrasound beam characteristics with depth can be accounted for using an integral approach. The metric can then be written as: $$R = \int_{0}^\infty    L(\alpha)\,d\alpha  where 2/\alpha $$ is the effective beam width and L(α′) is the axial distance over which the effective beam width is less than 2/α′.

<figure>
  <img src="/references/sigproc/resolution_integral.jpg" alt="" />
  <figcaption> Figure 1: resolution integral
  
  Image source: http://orbit.dtu.dk/files/4656580/Hemmsen_2010_SPIE%5B2%5D.pdf</figcaption>
</figure>

 
The L-α curve is bounded on the y-axis by L0, the ‘length of the beam’. Beyond that point, the beam still exists but cannot be distinguished from the noise because its intensity is too low. This is also called the noise limit. On the x-axis, the curve is limited by 1/a0, where a0 represents the best spatial resolution. A transducer with a good penetration and a good spatial resolution tends to have a large value for the Integral Resolution. L and α can be determined by scanning particular phantoms.

## What we could do at echOpen 
In this section, I write some of the ideas that came to my mind when I read articles about Image Quality Assessment. I am not an expert, these are only suggestions that could be used to start further reflections on that topic.

At echOpen we try to design a low-cost ultrasound scanner. In order to measure the quality of the image displayed by our system, we could use a scanner that is considered as a good one and compare the images with the Mean Squared Error method. As we work in a hospital, it shouldn’t be so difficult to access such a scanner, the main practical problem is that it must be difficult to take the exact same picture twice with different probes. 

It would also be interesting to use a tissue mimicking phantom to measure some of the parameters above including the Resolution Integral. The problem is that tissue mimicking phantoms for quality assessment cost about $2,000. Some recipes to make home-made and cheap tissue mimicking phantoms exist, but those phantoms are mostly used for the training of students in medicine, not for scanners quality assesment. A 2-axis table that could be put in an aquarium is currently being developed by the community, to test the basic resolution properties of the scanner.

 
## References
1_Alasaarela, E. and Koivukangas, J., Evaluation of image quality of ultrasound scanners in medical diagnostics, 1990.

2_Rangaraju, Kashyap Swathi and Kumar, Dr Kishor and Renumadhavi, C. H., Review Paper on Quantitative Image Quality Assessment Medical Ultrasound Images, IJERT, 2012.

3_Joy, J et al., Automated performance assessment of ultrasound systems using a dynamic phantom, 2014.

4_VenkatNarayanaRao, T. and Govardhan, A., Assessment of Diverse Quality Metrics for Medical Images Including Mammography, 2013.

5_Ibrahim, Aya et al., Assessment of Image Quality vs. Computation Cost for Different Parameterizations of Ultrasound Imaging Pipelines, 2015.

6_Hemmsen, Martin Christian et al., Ultrasound image quality assessment: a framework for evaluation of clinical image quality, 2010.

7_Ortega R., Leija L. and Vera A, Measurement of Ultrasonic Properties of Fat Biological Phantom, 2009

# List of authors
[@ApollineF](https://github.com/ApollineF)
[Aurélie](https://github.com/Aurelie-Mutschler)
[K. Ghosh](https://github.com/kelu124)
