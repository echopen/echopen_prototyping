# Functional specifications

Below are listed the functional specifications from the user app's point of view.

## Welcoming

1. **SplashScreen**

## Registration

1. **user registers with personal information**
2. **user validates CGUs**

## Echographic exam

1. **user accesses a full screen displaying the image caught by the ultrasound probe**
2. **user chooses pre-settings**
   1. user sets patients informations: medical informations, even as simple as the age, gender, the corpulence, are important:
      * to set correctly the hardware. Indeed the depth parameters will not be set the same whether the patient is a child or an adult, is fat or not
      * the data that will be stored will be critical to the machine learning part of the echOpen project. More generally, IA techniques will help denoise the image, map the patient anatomy real time, and in a long term prospective will help detect automatically anomalies
      * id informations will be eventually required for legal reasons, depending of the current state of the law.     
   2. user chooses pre-selected organs: each organ is so different in depth and structure that some settings are usual to be set accordingly to them. In place of setting them manually each time, we provide the possibility to set them in quick and easy way. Moreover, even if an utrasound exam is prescribed for one or some specific target organs, it happens that the examiner broadens the scope of the exam and investigates other organs than the one prescribed. Thus, we provide a way to change the organs settings current the exam
3. **user can constantly set main hardware parameters**
   1. gain        
   2. depths: this setting corresponds to the choice of a transducer frequency. There are 3 standard frequencies used in an ultrasound exam : 3.5, 5 and 7.5Mhz each of which corresponding to different analysis depth. 
      So, for 3.5 Mhz, this setting is typical used for digestive examination, 5 Mhz for medium depth examination such as heart examination and 7.5Mhz is used for superficial tissue such as bones and joints
4. **user can manipulate image** 
   1. take a screenshot of the current image displayed and store it: this is used in order to display some metrics: the user drags and drop some line on the screen in order to take measure of some pathological lesions, or some distances between points of organs, which are critical informations 
      this is used to share with medical colleagues 
      this is used for legal reasons to leave a medical proof of the exam and pretended diagnosis
   2. freeze the screen and get back to the 10 last elapsed seconds image acquisition. Indeed, often the user wants to go back to recent images and slow it down to fine-grain the reading 
   3. acquire a sequence of images and store it: this is used to share with medical colleagues and for legal reasons to leave a medical proof of the exam and pretended diagnosis
5. **user can access the settings page**
   1. hardware related settings: the user sets depth and gain. Further developments could lead to more advances settings, such as filters, hardware parameters or customized organs pre-settings
   2. image quality settings
6. **user can access the profile**
   1. register ID informations
   2. register medical informations
7. **displays shows main meta-informations**
   1. patient related information as detailed in point 3.2.1, age, gender, weight 
   2. clinical exam related information: the user can immediately access the main informations such as current depth, current gain 

## List of authors

[Clément Le Couedic](https://www.gitbook.com/book/echopen/echopen_prototyping/edit#)

[@nowami](https://github.com/benchoufi)

