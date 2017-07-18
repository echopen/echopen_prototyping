# Tissue mimicking phantoms

## Introduction
A tissue mimicking phantom is an object made of a material that is supposed to reproduce the acoustic properties of the human body. They
can be divided into two categories:
* those used by physicians to train themselves to perform certains exams,
* those used by engineers for image quality assesment. For the moment we at echOpen are a lot more interested by that second category.


## Commercially available tissue mimicking phantoms
As said before, there are two types of commercially available tissue mimicking phantoms. Here you can see an example of an ultrasound 
training model.

<figure>
  <img src="/references/sigproc/images/ultrasound_training_model.jpg" alt="" />
  <figcaption> Figure 1: ultrasound training model
  
  https://www.bluephantom.com/product/FAST-Exam-Real-Time-Ultrasound-Training-Model.aspx?cid=411</figcaption>
</figure>

But the phantoms we are interseted in are those that can be used for image quality assesment. Indeed, they can be used to measure certain
parameters such as:

* Spatial resolution. The spatial resolution can be measured by placing a series of two points that can be detected by the scanner close 
to each other, but at different distances from each other. Then you just have to take a look on the screen to see which points are still
distinguishable from their counterpart. You can also compare the values of the neighbouring pixels.

* Contrast resolution. There can be some areas in the phantom where the acoustic properties of the material are slightly different. You 
can estimate the value of contrast resolution by determining which of those areas you are able to distinguish on the screen. Contrast 
resolution is a key issue as it will strongly impact the device's capacity to detect tumors and cysts.

* Uniformity. Except for the areas and details dedicated to the resolution measurements, the material is supposed to be uniform in the 
object. So uniformity can be simply tested by evaluationg the noise at different depths.

Phantoms can also be used to test the quality of the scan conversion algorithm. Easily detected objects are put on a horizontal line at
regular intervals. Then you just have to check if those objects are still detected on the same horizontal line. The same thing can be 
done with a vertical line.

Here you  can see an example of such a tissue mimicking phantom.

<figure>
  <img src="/references/sigproc/images/phantom.jpg" alt="" />
  <figcaption> Figure 2: tissue mimicking phantom for image quality assesment.
  
 http://www.cirsinc.com/products/all/67/multi-purpose-multi-tissue-ultrasound-phantom/ </figcaption>
</figure>

Those phantoms are reliable but they are expansive: they cost about $2000.


## Home-made tissue mimicking phantoms



## References
