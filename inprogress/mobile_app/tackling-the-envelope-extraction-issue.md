# Tackling the envelope extraction issue

The aim is to benchmark different solutions for the envelope extraction which allows to reconstruct the image from the raw electrical signals.

The [last stable version](/stable/doc_pipeline.md) of the echOpen prototype implements a digital envelope extraction based on a Hilbert transform. This step is currently performed on the smartphone, which raises problems of low framerate : only 2-3fps is achieved, to be compared to an objective of 10-12fps. Because the envelope extraction is performed on the smartphone, the whole digitized raw signals are transferred through WIFI, which causes low framerate because of bandwidth limitations.

The next step is obviously to perform the envelope extraction on the device itself. It can be performed either analogically or numerically.

## Analog envelope extraction

Some analog solutions for the envelope extraction are currently being explored. The main advantage of such an implementation is cost reduction :

* If there's no Hilbert transform to be computed on the device, the performances required for digital post-processings are much lower, hence a cheaper FPGA/DSP can be used
* Analog envelope extraction is obviously performed prior to the analog-to-digital conversion. In this case, the sampling frequency could be reduced, which would then reduce the costs of the ADC.

## Digital envelope extraction

The gold standard for envelope extraction is the well-known [Hilbert transform](/references/sigproc/envelope_extraction.md). We'd however like to check if there exist alternative methods that would require lower computing resources. This is to optimize the performances needed for the FPGA and hence, lower the costs.

Some students from Polytech'Nantes are currently exploring alternatives to the Hilbert transform. Jump [here](/inprogress/mobile_app/ongoing-work-by-polytechnantes-students.md) for more details.



# List of authors

[Aurélie](https://github.com/aurelie-mutschler)

