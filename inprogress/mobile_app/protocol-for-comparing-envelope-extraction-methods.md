# Protocol for comparing envelope detection methods

## Context

The aim is to determine a very simple protocol to compare different solutions for the envelope extraction which allows to construct the image from the raw electrical signals. This step can be either performed analogically or numerically.

The [last stable version](/stable/doc_pipeline.md) of the echOpen prototype implements a Hilbert transform, which represents the gold standard for envelope extraction.

## Comparing different digital envelope extraction methods

The objective is to find a method that reduces the computational time, while preserving the image quality. The envelope detection steps mainly affects the axial resolution, this latter is hence a good metric to decide whether a given solution is suitable.

For introductory explanations about image quality, jump [here](/references/sigproc/new_IMGQ_metrics.md). For more details about ongoing work as regards characterization, jump [here](/inprogress/mobile_app/characterization.md).

The different solutions will be compared in terms of :

* **Axial resolution** : a good solution is one that allows to achieve an axial resolution that is equal or lower than the values obtained with a Hilbert transform.
* **Lateral resolution **: this latter may not be directly affected by the envelope extraction step, unless there are inconsistencies in the reconstruction from one line to another. For this reason, we want to monitor the curve of lateral resolution vs depth \(see the [Protocol for image quality assessment](/inprogress/mobile_app/characterization/protocol-for-image-quality-assessment.md) for further details\)

Images obtained from the last stable version of the echOpen device will be used as a baseline. The objective is to get images with a quality that is comparable or better !

## Principle

From raw signals, reconstruct images by applying an alternative to the Hilbert transform. Compare the axial/radial resolution to the reference ones obtained with the echOpen device \(on which a Hilbert transform is implemented\).

**Remark** : in the echOpen data processing pipeline, another important step is the scan-conversion, which allows to perform a conversion from polar to cartesian coordinates. For more information about the processing pipeline, jump [here](/introduction/new_introduction.md). Before comparing the reconstructed images to the echOpen ones, a step of scan-conversion has to be performed. The corresponding algorithm will be provided by echOpen engineers.

## Required inputs

* Phantom images obtained with the echOpen device, allowing to measure the axial/radial resolution as a function of depth \(see the [Protocol for image quality assessment](/inprogress/mobile_app/characterization/protocol-for-image-quality-assessment.md) for further details\)
* Corresponding curves of axial/radial resolution vs. depth obtained in the echOpen processing pipeline \(with Hilbert transform\), that will constitute a baseline
* Corresponding raw signals  
  Remark : these ones have to be taken with the probe and phantom in the **exact same position** as for the images !

* Scan-conversion algorithm implemented in the echOpen image processing pipeline.

## Protocol to compare one alternative solution to the Hilbert transform

* From the raw signals, extract the envelope, by implementing your own solution
* Apply the scan-conversion algorithm to reconstruct the images \(with the same format as the echOpen phantom images\)
* Compute the mean RMSE between the reference images and the reconstructed ones : can you explain the differences ?
* Deduce the axial resolution and draw the curve of lateral resolution vs. depth  
  Optional : develop a code that allows to do it automatically ;-\)

* The obtained values must be lower or equal to the ones obtained for the reference image, in the whole range of depths

# List of authors

[Aurélie](https://github.com/aurelie-mutschler)

