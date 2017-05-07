# Quantifying image quality

## Remarks

* Most of the image quality assessment in the articles review has been done by doctors - not quantitative, automated metrics.
* Quantitative metrics are not a silver bullet: some images have parameters that are good for a medical use, but bad for others
 * Information relevant for a case can be stored in what can be noise for another case
* Qualitative review of the images quality has to be done at the first stage - prototyping (Ultrasound Image Quality Assessment: A framework for evaluation of clinical image quality)
* We've talked about Hilbert transform - it may also be interesting to use IQ demodulation.
* The __Medical ultrasound: a new metric of performance for grey-scale imaging__ article can be of reference


## Suggestions

__Objective__: the objective is to provide metrics to assess the image quality.

The image is the results of several factors:

* _Transducer characteristics_ - quality is limited by transducer physical properties
* _Analog front end (pulser - amplifier)_ - quality is limited by noise, bandwidth, ...
* _ADC (analog-to-digital device)_ - quality limited by ADC specs
* _Digital processing_

However, one can consider this set of elements as a single "block" processing ultrasound to an image, and it's characterization could be done as one block, which does not prevent doing further testing on each single element.

### Tests

Tests could be run in two phase: the first, a simple one, measuring the resolution of the "probe" block.

### Preliminary characterisation of the block

Wires can be positioned at different depths and angles within the probe field of view, and resolution measured.

With two wires close to one another, again at different depths and angles, it is also possible to check the axial and lateral resolution of the probe.


### More advanced metrics

Excellent first steps are indicated in the article below. It measures a couple of key metrics that are relevant for grey-scale ultrasound imaging using a home-made, reproducable fantom which recipe is provided.
* Key metrics: _Resolution Integral_, _Depth of Field_, and _Characteristic Resolution_
* Math theory is well detailed
* Phantom recipe is "easy" to make and simple


## Medical ultrasound: a new metric of performance for grey-scale imaging

* 2004
* https://pdfs.semanticscholar.org/1eae/a3fcfd9eca87ebaccb5d6b605655f1f003b3.pdf
* 10.1088/1742-6596/1/1/041

### Key issue
The objective evaluation of grey-scale ultrasound is particularly difficult because it is not a quantitative imaging technique. However, it is possible to quantify some of the physical limitations that directly influence image quality.

Two key characteristics of high quality ultrasound images are :
* narrow beam width and
* good penetration into soft tissue.

-> a notional metric of quality or performance could be calculated as the ratio R = Penetration / Beam Width

### Some applications

The concept of a Resolution Integral is a general one and can be realised by various methods, the main distinction between these being the way in which the effective beam width is determined. Techniques for quantifying effective beam width include:

1. Hydrophone measurements of the transmitted beam.
2. Imaging fine wires or plastic filaments lying perpendicular to the scan plane.
3. Imaging point scatterers, such as small metal spheres.
4. Imaging a series of anechoic cylinders lying perpendicular to the scan plane.
5. Imaging an array of anechoic spheres positioned in the scan plane.
6. Imaging a series of anechoic pipes positioned in the scan plane.



## Reviewed documents

See [image quality metrics bibliography](/references/sigproc/IMGQ_biblio.md)
