# Ongoing work by Polytech'Nantes students

## Objectives

* Explore possible digital envelope extraction methods that would be good alternatives to the Hilbert transform
* Benchmark FPGA devices and find the one that is best suited to perform a digital envelope extraction in the echOpen probe
* Implement the best solution on the FPGA device

## Steps of the project

### Explore envelope extraction algorithms

* Using the [jupyter notebook playground](https://github.com/echopen/PRJ-medtec_sigproc/blob/master/SigProc_101/SigProc-101-pimped.ipynb), explore different implementations of the envelope detection
* Write some documentation about your findings : what were the algorithm tested, what results where achieved \(RMSE, computation time\) ? Give references of articles if you have some.

### Challenge the current implementation in the echOpen device

* Use the [Protocol for comparing envelope extraction methods](/inprogress/mobile_app/protocol-for-comparing-envelope-extraction-methods.md) to compare your own envelope detection algorithms to the one currently implemented in the echOpen probe
* Determine what is the best solution in terms of image quality and computation time
* Write documentation about your findings : what is the best algorithm and why ?

### Implement the best solution on a FPGA

* Find the best FPGA for implementing the solution : it must be as cheap as possible, and have performances that allow to reconstruct 10-12 images per second
* Implement \(or simulate\) your best solution on the FPGA
* Check it allows to achieve the desired framerate and image quality
* Write documentation : how to install/use the code, conclusion about performances

## Expected deliverables

* Documentation : our main information medium is this gitbook. Your documentation must be written in markdown so that we can include it here ;-\)
  With your permission, we will put some links to your github accounts in the files you have written. 

* Codes : Python/C++ codes of the different solutions explored + FPGA implementation of the retained algorithm.



# List of authors

[Aurélie](https://github.com/aurelie-mutschler)



