# Preparing next iteration

This section is meant to gather ideas about the objectives for the next iteration :-)

## Hardware

## Characterization

* Confirm the approach proposed in the first review
* Benchmark the Ultramark, our solution, and chinese probe to test the metrics on devices at hands

## Transducer

* Now is the time to explore transducer sourcing, update the possible suppliers, and build relationship with suppliers

## Mechanics

* **Bring the probe out of water !**
  * to be completed

## Embedded systems

### Explore a Raspberry benchmarking tool

* Raspberry has a huge community
* Simple miniaturized "benchmarking tool" with Analog front end + 10Msps acquisition
    * It's motors+transducer agnostic: can be tested with servo, with ATL probes, with stepper motors, ..
    * Allows benchmarking by providing a "level 0" benchmark
    * Low cost (170$ of electronics, 50$ of PCBs, 10$ of Rapsberry pi)
* RPi allows different types of optimisation (see embsys @eiffel)
* The RPi also allows a server-based approach

### Challenge an envelope detection algorithm (or many) on different architectures

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
  * Using 

## App - software

* **Iterate on mobile application usability**
    * starting from Mockups done with *Hetic Internet school* last year, prepare detailed user workflows that will be challenged by designers, doctors, ultrasound users and engineers during the next session
    * document the usability iteration
    * complete work started by Maroccan team on User Interface *phaino branch* and include new usability inputs

* **Re-architecture mobile application**
    * break dependencies and user functionnality code bindings in order to ease unit/integrated tests and ensure medical code compliance
    * implement MVP architecture design - see [Android Architecture Blueprint](https://github.com/googlesamples/android-architecture)

* **Continuous integration** 
    *  set-up or update unit/integrated tests frameworks (*JUnit*, *Monkey runner*, ...)
    *  increase overall test coverage for each application components
    *  set-up a continuous integration pipeline
        * set-up an automated test framework or use existing *Travis* one
        * implement hook mechanism for each new integration to ensure every automatic tests passed and to check that the commit has been properly reviewed
        * (optionnal) add static code analysis tool before integration (ie *Sonar Qube*)

* **Iterate on Formal Documentation**
    * find standard document template for every listed below documents following norm iso...
    * ramp up on Product Development Lifecycle tool 
    * Write *version-0* specifications (SRS)
    * write *version-0* verification plan (VP) 
    * wirte *version-0* software architecture design (SAD)

* **Store images with their metadata**
    * [DICOM](https://en.wikipedia.org/wiki/DICOM) is standard used to borrow metadata of medical pictures. We can see this format like an XML file which will accompany our medical picture.
    * DICOM is compatible with ultrasound pictures.
    * We can use it to store, for example,  the patient's name or the software's version used to get the pictures.
    * [\@eiffel](https://echopen.slack.com/team/eiffel) thinks that it could be a good idea to read the standard to get more information about this format.
* Need to list what information need to be stored within this metadata 
