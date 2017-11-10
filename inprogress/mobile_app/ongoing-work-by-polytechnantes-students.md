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
  _External material : An echOpen volunteer has implemented a pseudo-Hilbert transform on an ICE40HX4. This latter doesn't have any multiplier in its architecture, which makes it a cheap FPGA. You can inspire yourselves from his code \(see below\). Here are some links to useful references :  
  http://docplayer.net/29710944-30-minutes-vhdl-design-for-very-fast-fir-filter-on-low-cost-fpga.html  
  http://www.claysturner.com/dsp/asg.pdf  
  https://github.com/halipster/for\_echOpen_

```
////////////////////////////////////////////////////////////////////////////////
//
// Autor : Alister Trabattoni
// Date : 14/04/2017
// license : GPL
//
// This module perform a so called AB demodulation according to the article 
// "An Efficient Analytic Signal Generator" by Clay S. Turner (which can be 
// found at http://www.claysturner.com/dsp/asg.pdf). We do count on compiler
// optimisation to remove multiplication with zero coefficients since it allows
// a much more readeble code.
//
////////////////////////////////////////////////////////////////////////////////

module abdemod (output [9:0] dout,
            	input signed[9:0] din,
            	input clk);
  
  // parameter declaration
  parameter width = 10; 
  parameter n = 32;   
  // coefficents are stored in a big vector. As vector are by default in big
  // endian notation first coefficients will come out last. It suits our purpose
  // since coefficients need to be flipped in a convolution. Nota bene that 
  // vector part select is by default unsigned. The $signed() system task will
  // be needed.
  parameter coefs = {10'b0000000000,10'b0000000000,10'b0000000000,
	10'b0000000010,10'b0000000000,10'b0000000101,10'b0000000000,
	10'b0000001011,10'b0000000000,10'b0000010101,10'b0000000000,
	10'b0000101000,10'b0000000000,10'b0001010101,10'b0000000000,
	10'b0111001011,10'b0000000000,10'b1101101011,10'b0000000000,
	10'b1111000111,10'b0000000000,10'b1111100011,10'b0000000000,
	10'b1111110001,10'b0000000000,10'b1111111001,10'b0000000000,
	10'b1111111101,10'b0000000000,10'b1111111111,10'b0000000000,
	10'b0000000000};
  
  // register declaration
  reg signed [width-1:0] sr;
  reg signed [2*width-1:0] mult [0:n-1];
  reg signed [2*width-1+$clog2(width):0] a_pipeline [0:n-1];
  reg signed [2*width-1+$clog2(width):0] b_pipeline [0:n-1];  
	wire signed [(2*width-1+$clog2(width))*2:0] square;
  
  // loop variable declaration
  integer i; 

  // behavioral modeling
  always @(posedge clk) begin
    sr <= din;  
    // transposed FIR with both coefs and reversed time coefs (a and b signals)
    for (i=0; i<n; i=i+1) begin
      mult[i] <= sr * $signed(coefs[i*width+:width]);  
      if (i==0) begin
        a_pipeline[i] <= mult[i];
        b_pipeline[i] <= mult[n-i-1];
      end
      else begin
        a_pipeline[i] <= a_pipeline[i-1] + mult[i];
        b_pipeline[i] <= b_pipeline[i-1] + mult[n-i-1];
      end
  	end  
  end
  
  // truncation according to a gain of 2^(width-1)
  assign square = a_pipeline[n-1]*a_pipeline[n-1] + b_pipeline[n-1]*b_pipeline[n-1];	
	assign dout = square[35:26];
	
  
endmodule
```

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

* Codes : Python/C++/Verilog codes of the different solutions explored + implementation of the retained algorithm.

# List of authors

[Aurélie](https://github.com/aurelie-mutschler)

[Alister](https://github.com/halipster)

