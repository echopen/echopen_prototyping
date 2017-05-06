# Preparing next iteration

This section is meant to gather ideas about the objectives for the next iteration :-\)

## Hardware

## Mechanics

* **Bring the probe out of water !**
  * to be completed

## Embedded systems

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