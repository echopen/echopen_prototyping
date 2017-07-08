# add current Mobile app UI

You'll find here the current UI. It is for the moment dead simple. Indeed, for this version, we choose to fix only a one screen app, figuring the main functionalities :





* a splashscreen ;\)
* displaying the image
* set a communication pipeline, enabling the choice between
  * a local mode 
    * displaying a local file 
  * a TCP mode 
    * getting the image sent through TCP protocol. NB : the data are sent via WIFI
  * a UDP mode
    * getting the image sent through UDP protocol
  * **Rmq 1:** these layers were built and added one after the other, following the history of hardware evolution. The Android app sticked to these settings : first faking local utrasound data from batch files grabbed on the web, then getting data thrown through UDP protocol, hardware developers estimating that had to be tested and could be a gain of speed, but which proved not to be as consistent as we wanted related to data loss, then getting data from TCP, which is the current default choice.
  * **Rmq 2:** The current implementation stores the data in local and are served on a web local port through TCP protocol 
* scrolling with seekBars to control contrast and image intensity
  _Remark: _
  * _contrast can be adjusted by selecting a customized intensity-to-pixels linear or exponential look-up table._
  * _The image intensity can also be amplified uniformally through a gain filter_



![](/assets/Screenshot_2017-04-15-16-56-57.png)
<img src="/assets/Screenshot_2017-04-15-16-56-57.png" alt="alt text" width="300px">

![](/assets/Screenshot_2017-04-15-16-56-10.png)![](/assets/Screenshot_2017-04-15-16-43-41.png)

