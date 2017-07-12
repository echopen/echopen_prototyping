# Data format

## Description
DICOM (Digital Communications in Medicine) is a standard for handling, storing, transmitting and printing information in medical imaging. It includes a file format definition and 
a network communication protocol. You can find a more detailed description of DICOM [here](./echopen_prototyping/challenges/data_format/). We would like our device to be able to export images in DICOM so that physicians may be able to exchange those 
images or to use already existing specialized software for example. A DICOM file contains all the data a physician would need to establish a diagnosis even if he didn't perform the exam himself (data about the set-up of the scanner for axample). DICOM would also allow consistency in time and a proper tagging for images. 
 
 ## Objectives
 There are many DICOM data formats. Some of them were created for X-ray imaging, others were disigned for RMI or ultrasound imaging etc ... And even among those of the latter category, there is till a lot of different formats ! Some of them are adapted for old and basic scanners, others were created for the last generation of ultra poratble ultrasound probes and so on. 
 
So, the main objective here is to find the DICOM data format(s) that will suit the echOpen probe the best ! There may be several formats as the purpose is to export either fix images (screenshots) or US (cine) videos. 

Once the data format is chosen, the second objective or to implement a solution to create such files. To do that, very detailed information about the format such as the mandatory will be needed.
 
 ## Current solution
 For the moment, we managed to export JPG images.
 
 
 ## State of the Art
Every company selling ultrasound scanners must publish its ultrasound DICOM conformance statements (id est the format they use for each one of their products). It may be interesting to take a look at the format they use for devices that are quite similar to the echopen probe, such as:
* The VScan Extend from General Electrics Healthcare. Conformace statements are [there](file:///C:/Users/Apolline/Downloads/GEHC-DICOM-Conformance_VScan-Extend-v1-0-3_DOC1821494_Rev3.pdf). If you want to read about the conformace statements of other products by the same firm, click [here](http://www3.gehealthcare.com/en/products/interoperability/dicom/ultrasound_dicom_conformance_statements).
* The Philps Lumify. Conformance statements are [there](http://incenter.medical.philips.com/doclib/enc/12720755/Lumify_2_0_DICOM_Conformance_Statement.pdf%3ffunc%3ddoc.Fetch%26nodeid%3d12720755). f you want to read about the conformace statements of other products by the same firm, click [here](http://www.usa.philips.com/healthcare/resources/support-documentation/dicom-ultrasound). 
 
 
 ## Challenge progress
0%

This chart's purpose is to allow contributors to write their ideas and what they managed to do, so that other contributors may knom what has been done so far.

| Contributor                  | Achievment                                | Next step or help needed        | 
| :---                         | :---                                      | :---                            | 
|                              |                                           | -                               |

 
 ## Ressources
There is an introductory document to DICOM at the following address, which may be helpful: 
* [https://orthanc.chu.ulg.ac.be/book/dicom-guide.html](https://orthanc.chu.ulg.ac.be/book/dicom-guide.html)

 You can also read the [subsection about DICOM](./echopen_prototyping/challenges/data_format/).
 
 
 ## Details 
 
 ### Skills
 * Good knowledge of the DICOM format
 * Basic skills in computer science
 
 
 ### Level 4
Difficulty of the challenge (from 1 to 5).

### Team
This challenge was suggested by the Mobile App team. Information to contact them is available [here](./howto/teams.md).
