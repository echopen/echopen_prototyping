# Preparing next iteration

This section is meant to gather ideas about the objectives for the next iteration :-\)

## Hardware

## Mechanics

* **Bring the probe out of water !**
  * to be completed

## Embedded systems

Challenge an envelope detection algorithm (or many) on different architectures :

* Singlecore CPU (used as reference),
* Multicore CPU,
* [SIMD](https://en.wikipedia.org/wiki/SIMD) CPU,
* Multicore SIMD CPU,
* GPU,
* FPGA
* DSP

Since it is not possible to simulate precisely the performances of the different architectures we will have to test them.
The objective of this is to summarize performances of the different architectures and taking their prices into account. A good result will be to obtain an Optimum of Pareto between the price (which has to be as low as possible) and the performances (which have to be as high as possible).

One prerequisite of this is to have a **good knowledge** of **at least one** envelope detection algorithm.


## Signal processing

* **Find the best choice for envelope extraction**
  * Analog implementation
  * Digital implementation
    * challenge v1 : "dummy" quality assessment --&gt; gather knowledge about state-of-the-art
    * challenge v2 : implement solutions picked from v1 on the device and evaluate image quality, computation time and achievable framerate, ...
  * Decide for good between analog and digital implementations based on image quality and cost constrains
  * Implement the chosen solution on the device

## App - software

* **Store images with their metadata**
	* [DICOM](https://en.wikipedia.org/wiki/DICOM) is standard used to borrow metadata of medical pictures. We can see this format like an XML file which will accompany our medical picture.
	DICOM is compatible with ultrasound pictures.
	We can use it to store, for example,  the patient's name or the software's version used to get the pictures.
	[\@eiffel](https://echopen.slack.com/team/eiffel) thinks that it could be a good idea to read the standard to get more information about this format.