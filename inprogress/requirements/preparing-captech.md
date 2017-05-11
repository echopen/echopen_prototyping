# Preparing next iteration

This section is meant to gather ideas about the objectives for the next iteration :-\)

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

* **Store images with their metadata**
    * [DICOM](https://en.wikipedia.org/wiki/DICOM) is standard used to borrow metadata of medical pictures. We can see this format like an XML file which will accompany our medical picture.
    * DICOM is compatible with ultrasound pictures.
    * We can use it to store, for example,  the patient's name or the software's version used to get the pictures.
    * [\@eiffel](https://echopen.slack.com/team/eiffel) thinks that it could be a good idea to read the standard to get more information about this format.
* Need to list what information need to be stored within this metadata 
