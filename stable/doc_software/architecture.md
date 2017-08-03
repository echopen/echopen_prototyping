# Mobile Application Functional Architecture

This diagram is a representation of the functional components of the mobile application. We will give a short description of each module's role.

![](../../assets/MobileFunctionnalArchitecture2.png)

The EchOpen mobile application is divided into the following components:

* **Device Pairing Service:** _ensures robust connection and communication to EchOpen echography device through Wifi via TCP/IP protocol_

* **Device Data Source:** _receives and reads TCP/IP messages from echOpen echography device and formats information into raw image data streaming_

* **Local Data Source:** _emulates an echOpen device. To do so it reads mobile phone local files and formats information into image raw data streaming_

* **Echography Image Builder:** _transforms an image raw data sequence into a displayable bitmap image by applying a sequence of filters\(envelope detection, scan conversion, ...\)_

* **Echography Image Realtime Visualisation:** _provides realtime image streaming rendering_
* **Echography Image Manipulation:** _allows user to manipulate on-the-fly image contrast_

* **Measure:** _allows user to deposit a ruler on the image and display associated precise measure_

* **Global UI components:** _handles common UI navigation elements_

# Mobile Application Class Diagram

This diagram is a representation of the mobile application implementation. It provides an overview of the Java class architecture and locates main code entry points.

![](../../assets/MobileAppHighLevelArchitecture.jpg)

To get detailed class description, please refer to [Doxygen documentation](https://github.com/echopen/PRJ-medtec_androidapp/tree/master/doc/app_javadoc)

## List of authors

[Clément Le Couedic](https://www.gitbook.com/book/echopen/echopen_prototyping/edit#)

[@nowami](https://github.com/benchoufi)

