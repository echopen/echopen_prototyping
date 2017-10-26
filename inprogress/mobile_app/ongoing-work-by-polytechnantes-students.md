# Ongoing work by Polytech'Nantes students

## Objectives

* Explore possible digital envelope extraction methods that would be good alternatives to the Hilbert transform
* Benchmark FPGA/DSP devices and find the one that is best suited to perform a digital envelope extraction in the echOpen probe
* Implement the best solution on the FPGA/DSP

## Steps of the project

### Explore envelope extraction algorithms

* Using the [jupyter notebook playground](https://github.com/echopen/PRJ-medtec_sigproc/blob/master/SigProc_101/SigProc-101-pimped.ipynb), explore different implementations of the envelope detection
* Write some documentation about your findings : what were the algorithm tested, what results where achieved \(RMSE, computation time\) ? Give references of articles if you have some.

### Reproduce echOpen images and evaluate their quality

_pre-requisites : codes of Hilbert transform and scan-conversion implemented in the echOpen pipeline, raw signals and corresponding images of phantoms_

* Use the codes provided by echOpen engineers to reconstruct images from raw signals

* Check that the reconstructed images are exactly the same as the reference ones, by computing the RMSE

* Deduce the corresponding value of axial resolution as well as the curve of lateral resolution vs depth. See the [Protocol for image quality assessment](/inprogress/mobile_app/characterization/protocol-for-image-quality-assessment.md) for more details.

### Challenge the current implementation in the echOpen device

_pre-requisites : codes of scan-conversion implemented in the echOpen pipeline, raw signals and corresponding images of phantoms_

* Use the [Protocol for comparing envelope extraction methods](/inprogress/mobile_app/protocol-for-comparing-envelope-extraction-methods.md) to compare your own envelope detection algorithms to the one currently implemented in the echOpen probe
* Determine what is the best solution in terms of image quality
* Write documentation about your findings : what is the best algorithm and why ?

### Assess the feasibility of a Hilbert transform on a FPGA/DSP

* Simulate an implementation of \(pseudo-\)Hilbert transform on FPGA, and find a FPGA that would allow to reconstruct 10-12 images per second, while being as cheap as possible
* Simulate an implementation of Hilbert transform on a DSP, and find a DSP that would allow to reconstruct 10-12 images per second, while being as cheap as possible
* Write documentation about your findings : pros/cons of each solution

### Assess the feasibility of an alternative for envelope extraction on a FPGA/DSP

* Simulate an implementation of the alternative method for envelope extraction on FPGA, and find a FPGA that would allow to reconstruct 10-12 images per second, while being as cheap as possible
* Simulate an implementation of the alternative method for envelope extraction on a DSP, and find a DSP that would allow to reconstruct 10-12 images per second, while being as cheap as possible
* Write documentation about your findings : comparison of Hilbert transform vs alternative method, and best choice for the implementation \(based on costs and performances\)

### Implement the best solution

* Implement the best solution
* Check that it allows to achieve the desired framerate and image quality
* Write documentation : how to install/use the code, conclusion about performances

## Expected deliverables

* Documentation : our main information medium is this gitbook. Your documentation must be written in markdown so that we can include it here ;-\)  
  With your permission, we will put some links to your github accounts in the files you have written.

* Codes : Python/C++ codes of the different solutions explored + implementation of the retained algorithm.

# List of authors

[Aurélie](https://github.com/aurelie-mutschler)

