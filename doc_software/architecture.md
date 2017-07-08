# Mobile Application functionnal Architecture
This diagram is a representation of the functionnal components of the mobile application. We will give a short description of each module role.

<br>
![](../assets/MobileFunctionnalArchitecture2.png)

The EchOpen mobile application is divided into the following components:

 * **Device Pairing Service:** *ensures robust connection and communication to EchOpen echography device through Wifi via TCP/IP protocol*
<br>
 * **Device Data Source:** *receives and reads TCP/IP messages from echOpen echography device and formats information into image raw data streaming*
 * **Local Data Source:** *emulates an echOpen device. To do so it reads mobile phone local files and formats information into image raw data streaming*
<br>
 * **Echography Image Builder:** *transforms an image raw data sequence into a displayable bitmap image by applying on a sequence of filters(envelop detection, scan conversion, ...)*
 * **Echography Image Realtime Visualisation:** *provides realtime image streaming rendering*
 * **Echography Image Manipulation:** *allows user to manipulate on-the-fly image contrast*
<br>
 * **Measure:** *allows user to deposit a ruler on the image and display associated precise measure*
<br>
 * **Global UI components:** *handles common UI navigation elements*

# Mobile Application Class Diagram
This diagram is a representation of the mobile application implementation. It provides an overview of the Java class architecture and locates main code entry points.

<br>
![](../assets/MobileAppHighLevelArchitecture.jpg)
<br>

To get detailed class description, please refer to [Doxygen documentation](https://github.com/echopen/PRJ-medtec_androidapp/tree/master/doc/app_javadoc)
