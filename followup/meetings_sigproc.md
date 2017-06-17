# 2017

## 2017.06.14

### Envelope extraction challenge

**Leaderboard**

* @loic is working on errors catching

* password recovery still to be handled

* then we'll recruit guinea pigs to beta-test the leaderboard \(help needed!\)

**Notebook**

* @aurelie will add some explanations in the notebook :

  * this challenge is meant to test our leaderboard
  * and benchmark alternatives to Hilbert transform, which is very computationally costly  
    --&gt; contributors have to be creative to find "simpler" algorithms

  * the score is just a pretext !

## Time for the great merge

* from now Wednesday meetings will be merged in one prototyping meeting :-\)
* let's all meet on June 21st 7:00pm !

## 2017.05.31

### Envelope extraction challenge

* @luc has pushed a PR with noised images for the score assessment

* @lecoued has pushed a PR for evaluating the algorithms on different images in a loop

* @loic has still some tickets : password recovering, and some others

* @loic @lecoued @aurelie will plan a "django for dummies" session ;-\)

### Documentation

* the documentation of v3.0.0 is taking shape!
* the "howto contribute" instructions will be beta-tested by @loic @benjamin @soobash

## 2017.05.10

* Envelope extraction
  * leaderboard : @clement is working on the scoring for multiple images --&gt; still a couple of weeks needed to finish
  * @luc has included in the notebook some piece of code to generate realistic noise on images --&gt; he will create some noised version of the images
* Documentation
  * it's critical now that the hardware documentation is done !!

## 2017.05.03

* Envelope detection challenge
  * [\@alister](https://echopen.slack.com/team/alister) points that the relevance of simulated raw data is very limited. He proposes to retrieve some real raw data and take the corresponding image of a commercial device. Problem is that the image will then be the result of different treatments \(filtering, scan conversion,...\) and not only the envelope detection.
  * To account for the noise in the leaderboard evaluation, [\@luc](https://echopen.slack.com/team/luc) proposes to create several different versions of the raw signal by adding some noise to the one simulated from the ground truth image. [\@luc](https://echopen.slack.com/team/luc) will create those images.
  * [\@hackolite](https://echopen.slack.com/team/hackolite) points the importance of having an ultrasound image database --&gt; [\@luc](https://echopen.slack.com/team/luc) knows someone who handles DICOM databases
  * Challenge V2 : need to have a pool of echOpen images + metrics for quality assessment \(cf. bibliography done by [\@luc](https://echopen.slack.com/team/luc)\)

## 2017.04.19

* prototyping gitbook / documenting v3.0.0 release
  * [\@luc](https://echopen.slack.com/team/luc) has pushed a version of the production guide, there are still some bugs with image displaying + mechanical part needs to be completed --&gt; [\@aurelie](https://echopen.slack.com/team/aurelie) & [\@luc](https://echopen.slack.com/team/luc) work on it
  * documenting of the hardware is ongoing. [\@embSys](https://echopen.slack.com/team/embSys) team could help for the characterization of the device
* leaderboard
  * front is ok
  * [\@hackolite](https://echopen.slack.com/team/hackolite) is working on password retrieval
  * [\@hackolite](https://echopen.slack.com/team/hackolite) needs help/time to implement the scoring on multiple images

## 2017.04.12

* prototyping gitbook / documenting v3.0.0 release
  * [\@alister](https://echopen.slack.com/team/alister) has volunteered to rewrite the introduction
  * "how to contribute" section is online
  * [\@luc](https://echopen.slack.com/team/luc) : production guide is ongoing
  * [\@luc](https://echopen.slack.com/team/luc) [\@soobash](https://echopen.slack.com/team/soobash) volunteered to make some bibliography about image quality assessment
* leaderboard
  * [\@loic](https://echopen.slack.com/team/loic) is working on password retrieval
  * [\@loic](https://echopen.slack.com/team/loic) still needs help to finalize the scoring, any volunteer is welcome

## 2017.04.03

* focusing on documentation
* prototyping gitbook
  * v3.0.0 app
    * rendering pipeline passing through envelope detection with 16-bit encoding is now functional.
    * Next step : test it with the device
    * documentation is ongoing. Might be finished by the end of the week
  * v3.0.0 hardware
    * documentation is running late --&gt; hardware improvements must be stopped for now, documenting v3.0.0 release is top priority
    * [\@eiffel](https://echopen.slack.com/team/eiffel) will "beta-test" the part of the documentation describing the redpitaya
    * production guide : [\@luc](https://echopen.slack.com/team/luc) will manage it
  * how to contribute section --&gt;[\@aurelie](https://echopen.slack.com/team/aurelie) will handle it by the end of the week
* report of activity
  * [\@luc](https://echopen.slack.com/team/luc) shared a draft
  * [\@benchoufi](https://echopen.slack.com/team/benchoufi) [\@aurelie](https://echopen.slack.com/team/aurelie) will complete it

## 2017.03.29 - HD - 20.00 \(Paris time\)

* [\@aurelie](https://echopen.slack.com/team/aurelie) & [\@lecoued](https://echopen.slack.com/team/lecoued) : point about the documentation
* with [\@luc](https://echopen.slack.com/team/luc) :  digression to deal with the mechanical ultramark probe - the idea is to use the material to put a ultrasound-transparent hull
* [\@hackolite](https://echopen.slack.com/team/hackolite) challenge platform
  * -&gt; could not move forward the development
  * [\@hackolite](https://echopen.slack.com/team/hackolite) is going to prepare a django app working guide hackpad

## 2017.03.22 - HD - 20.00 \(Paris time\)

### Methodology

* this is the first report directly lettered  in the GitBook ;\)
* the leaderboard contributors can find the tickets on the GitHub's agile [dashboard](https://github.com/echopen/PRJ-medtec_sigproc/projects/)

### Envelope detection challenge

* discussion on metrics [\@luc](https://echopen.slack.com/team/luc) [\@aurelie](https://echopen.slack.com/team/aurelie) [\@lecoued](https://echopen.slack.com/team/lecoued)

  * RMSE is not satisfactory as a metric, but it can be valid as a starter
  * [\@luc](https://echopen.slack.com/team/luc) suggests the use of a sight

* [\@hackolite](https://echopen.slack.com/team/hackolite): leaderboard is online. There are lot of remaining implementations to be done such as password recovery & such

  * TODO: look for pythonists in the community, ongoing ping on GitHub by [\@aurelie](https://echopen.slack.com/team/aurelie)

  * this is documented [here](https://github.com/echopen/PRJ-medtec_sigproc/projects/)

## 2017.03.15 - HD - 20.00 \(Paris time\)

### Methodology

* [\@aurelie](https://echopen.slack.com/team/aurelie) : feedback on the evolution of the methodology implementation
  starter kit
  * github cards
  * gitbooks : on starter kit, and a unique medico-technical gitbook, assembling software and hardware part
* long discussion on repo structures
  * each project has its repo + a production repo
  * or : one giant common repo
  * pros for separate repos
    * easy to download
    * “separation of concerns”, maintain a separate environment for development, contribution and enforces an “emulator way of thinking”
    * ease of continuous integration if using “travis”
  * pros for a single repo
    * easy for the user
    * maintain transversality between the repos

### Envelope detection challenge

* [\@soobash](https://echopen.slack.com/team/soobash): presentation of an other detection envelope algorithm
* [\@hackolite](https://echopen.slack.com/team/hackolite): learboard should be online tomorrow !!
  * dockers are plugged
* Score assessment on the leaderboard
  * the score will be computed by evaluating the reconstruction error on a set of different images from the vscan.
  * [\@soobash](https://echopen.slack.com/team/soobash) will check the raw data simulation from those images and the reconstruction
  * then [\@hackolite](https://echopen.slack.com/team/hackolite) can change the leaderboard scoring.
  * [\@hackolite](https://echopen.slack.com/team/hackolite) : total computation time on the leaderboard shouldn’t be over 2 minutes. The image size might be reduced to fulfill this constraint.

## 2017.03.08 - HD - 20.00 \(Paris time\)

### methods

working week of [\@aurelie](https://echopen.slack.com/team/aurelie) to implement concretely the CapMeth guidelines

### envelope detection challenge

new front of the site is available -&gt; css by [\@jayjay](https://echopen.slack.com/team/jayjay)  
docker 4 rabbitMQ & docker 4 django -&gt; bugs currently under investigation by [\@hackolite](https://echopen.slack.com/team/hackolite)  
[\@hackolite](https://echopen.slack.com/team/hackolite) : development of functionality to see the source code of any challengers + debugging some password recovery  
proposition of [\@djabbz](https://echopen.slack.com/team/djabbz) : ranking challengers by time processing, currently  
production scheduled  on monday !

## 2017.03.02 - HD - 20.00 \(Paris time\)

### Documentation

* [\@soobash](https://echopen.slack.com/team/soobash) started to draw a detailed scheme of the pipeline for current kit, as well as identifying the bottlenecks
* [\@aurelie](https://echopen.slack.com/team/aurelie) will study the schemes by focusing on missing information for a hypothetical new contributor who would like to jump in the signal processing / hardware
* [\@soobash](https://echopen.slack.com/team/soobash) pointed the critical importance of fixing the specs \(this includes fixing costs\) and gather all this information on a single support

### Envelope detection challenge :

* the notebook and leaderboard have been beta-tested.
* [\@hackolite](https://echopen.slack.com/team/hackolite) will add the possibility of downloading other contributor’s codes
* we have to change the way performances of the algorithms are assessed on the leaderboard. Currently, the score is determined by processing the same image as the one being used in the notebook. [\@soobash](https://echopen.slack.com/team/soobash) will create a set of images + simulated raw data from vscan records. the score will be averaged on this set of images.
* [\@aurelie](https://echopen.slack.com/team/aurelie) will add an introduction to ultrasound imagery principles in the notebook
* integration is in progress. [\@hackolite](https://echopen.slack.com/team/hackolite) is reviewing CSS
* Deadline for launching the challenge : 12/3/17

### Sampling rate tests for ADC :

* [\@soobash](https://echopen.slack.com/team/soobash) is studying the possibility of using “random” sampling so as to decrease the ADC frequency without losing precision on the signal envelope

## 2017.02.17 - HD - 20.00 \(Paris time\)

* recap [\@aurelie](https://echopen.slack.com/team/aurelie): NoteBook updated with some clarifying remarks for the user
  leaderboard site
* [\@hackolite](https://echopen.slack.com/team/hackolite) deployed the site here: [http://37.187.117.106:8888/](http://37.187.117.106:8888/)
  precisely the code for the envelope detection is here: [https://github.com/echopen/PRJ-medtec\_sigproc/blob/master/echopen-leaderboard/processor\_node/uploaded\_custom.py](https://github.com/echopen/PRJ-medtec_sigproc/blob/master/echopen-leaderboard/processor_node/uploaded_custom.py)
* [\@jayjay](https://echopen.slack.com/team/jayjay) will work on the css of this site to homogenize it with the current echopen.org stylesheet
* [\@lecoued](https://echopen.slack.com/team/lecoued) implemented image filters
  this is done on the android app: several types of gain filters
  suggests to integrate ITK full featured framework with optimized filters
* feedback of the testing work of  [\@jerome](https://echopen.slack.com/team/jerome), @noureddine and @soobash
  * test of rotating probe: replaced faulty transducer with old one, tested rotating probe on stationary target in water tank
  * system can do one image per second. system can show target image even     \* without envelope detection
  * bottle neck is digital envelope detection. Need to speed up the envelope detection code to reach 15 frame per second to have a real-time system
* discussed the signal processing chain and the need to have an onboard DSP
* ALL pointed the necessity to get better and more structured informations flow between different groups: embsys, sigproc, androidapp and define clear roadmap and dedicated objectives and related milestones This is the precise the goal of the 11.02.17 CapMeth holding \@echOpen

## 2017.02.01 - HD - 20.00 \(Paris time\)

* feedback, several measures were done [\@jerome](https://echopen.slack.com/team/jerome) [\@noureddine](https://echopen.slack.com/team/noureddine) [\@soobash](https://echopen.slack.com/team/soobash) [\@benschan](https://echopen.slack.com/team/benschan)
* [\@jerome](https://echopen.slack.com/team/jerome) proposal, [\@lecoued](https://echopen.slack.com/team/lecoued) is currently developing an app android : look-up table/contrast, envelope detection
* V0 & V1 challenge definition [\@luc](https://echopen.slack.com/team/luc) : the first and up-coming one consists in getting the best envelope detection, to narrow the spotting and the second, given the transducer specifications, consists in processing the signal in such a way to get the narrowest spot
* Definition of the phantom : we need to design  one out of strip board, we can get luc’s one for testing, consisting in stems
* waiting for [\@hackolite](https://echopen.slack.com/team/hackolite)’s PR, and @aurelie will give us the go ! on principle kicking the challenge next week ;\)

## 2017.01.25 - HD - 20.00 \(Paris time\)

### Envelope detection

* NoteBook :
  * [\@aurelie](https://echopen.slack.com/team/aurelie) cleaned the notebook, and is now prepared to kick-off
  * Notebook is available [here](https://github.com/echopen/PRJ-medtec_sigproc/blob/master/SigProc_101/SigProc-101-pimped.ipynb)
  * [\@aurelie](https://echopen.slack.com/team/aurelie) will explicit a little bit further the submisssion process on the notebook, especially to aware contributors that reconstruction methods are available inside the python notebook
  * when ready, the challenge will be made public and spread out
* Leaderboard
  * [\@hackolite](https://echopen.slack.com/team/hackolite) integrated the score scripts, the leaderboard is updated.     \* Submission are now possible by uploading
  * [\@hackolite](https://echopen.slack.com/team/hackolite) suggests user to stress test the platform and that we can call for contribution to clean some UI part
    $ discussion about the security breaches when installing libs. Solution [\@djabbz](https://echopen.slack.com/team/djabbz) : add a requirements.txt file with all the necessary libs that can be installed using pip. For other libs, submitters should contact the admin.

### Electronics

* [\@noureddine](https://echopen.slack.com/team/noureddine) inspected on 20.01.17 the echOpen’s elctronics and has a whole list of simple improvements, in order to consolidate the electronics consistency. [\@noureddine](https://echopen.slack.com/team/noureddine) stresses the point that we should get precise specs, either for the hardware development or for challenge. All this is convergent and coherent with the importance of a CAPMeth
* [\@noureddine](https://echopen.slack.com/team/noureddine) and [\@soobash](https://echopen.slack.com/team/soobash) are going to drive bunch of electronics tests in coordination with jerome

## 2017.01.18 - HD - 20.00 \(Paris time\)

* presentation of new comers Clement Le Couedic and Mickaël-André
* Discussions about the python notebook and kick-off of the challenge
* [\@noureddine](https://echopen.slack.com/team/noureddine) proposes to check more in depth the electronics. A visit is scheduled on 20.01.17

## 2017.01.11 - HD - 20.00 \(Paris time\)

* [\@luc](https://echopen.slack.com/team/luc) and [\@aurelie](https://echopen.slack.com/team/aurelie) : produced a python notebook on a envelope detection challenge. For the moment raw data are simulated from images by modulating with a sinusoïdal function, the frequence of which corresponds to the echOpen piezo frequence.
* [\@aurelie](https://echopen.slack.com/team/aurelie) and [\@luc](https://echopen.slack.com/team/luc) will add more information about the metrics used
* [\@luc](https://echopen.slack.com/team/luc) wants to change the implementation of the Baseline envelope detection function \(replace decimation by bicubic interpolation\)
* [\@aurelie](https://echopen.slack.com/team/aurelie) and [\@djabbz](https://echopen.slack.com/team/djabbz) will complete the notebook to build up a starting kit
  python notebook will be pushed on [\@hackolite](https://echopen.slack.com/team/hackolite)’s server and then kick-off the challenge
* [\@jerome](https://echopen.slack.com/team/jerome) will produce raw data in the next few days with the help of a calibrated phantom
* redpitaya code runs now at fast sample rate and needs now optimisation. \* [\@djabbz](https://echopen.slack.com/team/djabbz) suggests to pass the algo to GPU specialist and challenge him. @hackolite is working on CUDA and could be interested to work on this challenge.
* Loïc is adding nbviewer to the challenge platform
* [\@soobash](https://echopen.slack.com/team/soobash) will document the metrics used for the denoising challenge \(docstrings containing simple intuition plus the corresponding formulae\)
* [\@djabbz](https://echopen.slack.com/team/djabbz) suggests a roadmap for the AI team:
  * work on the current echOpen images in order to enhance the image quality \(potentially using knowledge transfer and Vscan data\)
  * start a separate workgroup on organ detection and anomaly detection applied to the other available data \(primarily from the AP-HP datalake\)
    include the data collection \(data repatriation\) in the very design of the UX
    * \([\@benchoufi](https://echopen.slack.com/team/benchoufi)'s suggestion\) \[long term\] crowdsource annotations on echOpen images from practitioners.

## 2017.01.04 - HD - 20.00 \(Paris time\)

* welcoming of a new participant Kevin
* kit/redpitaya image debugging pointed by [\@luc](https://echopen.slack.com/team/luc) and [\@aurelie](https://echopen.slack.com/team/aurelie)
  -&gt; strikes appear on images, related to a trigger delay effect.
* However, [\@jerome](https://echopen.slack.com/team/jerome) succedeed in a brand new implementation of the kit/redpitaya \(using a digital processing filter, instead of the analog filter\), getting more data, exploiting the full abilities of the sample rate \(125Msps instead of 125/8Msps previously\), and the 14 bits precision of the device. Should have the new images in the next days
* kevin wants to contribute to phantom
* ALL agree upon the necessity to develop a better signal processing before treating the images - and that the processing needs to be aligned on the implementation of the medical prototype
* So a challenge is proposed in order to make the communities suggest filter from the new kit raw datasets
* [\@luc](https://echopen.slack.com/team/luc) and [\@aurelie](https://echopen.slack.com/team/aurelie) are going to push a jupyter notebook, to expose the challenge pedagogically and provide synthetic raw data. \(this also enables one to understand what was the source of the error with the first set of data acquired in the aquarium\).
* [\@jerome](https://echopen.slack.com/team/jerome) provides the dataset along with a calibration phantom. The phantom must be sufficiently well calibrated in order to get a gold standard of the output datasets
* kevin will start playing with algo on raw datasets
* [\@aurelie](https://echopen.slack.com/team/aurelie) suggests to develop an ML approach of a hyper-resolution system -&gt; \* [\@benschan ](https://echopen.slack.com/team/benschan) is going to develop some related compression tool

# 2016

## 2016.12.20 - HD - 20.00 \(Paris time\)

* running and testing different materials to get images on real devices
* UltraMark device
* echOpen kit
* recent ultrasound device
* echOpen images lacks of contrasts. Addendum : this CR is edited the 23.12.16 and we got a far more image on echOpen’s kit by amplifying the signal : the RAMP is varied from 0.8 to 1, instead of 0 to 1
* The ultrasound phantom is not working properly : only half of the insiders objects appear and appear not as neatly as clearly as it should. Btw, echOpen’s kit seem not to be as performant to detect it.
* acquarium nodejs platform is now all set up : it enables to get ultrasound data from remote, after passing some parameters such as : number of lines, decimation, RAMP values, angle of sector acquisition, number of images. It should be deployed as soon as the team decide to do so ;\)
* [\@aurelie](https://echopen.slack.com/team/aurelie) states that denoising echOpen’s images is useless since we do not have as much resolution as would need those type of problematics to emerge.
* [\@djabbz](https://echopen.slack.com/team/djabbz) [\@aurelie](https://echopen.slack.com/team/aurelie) [\@benschan ](https://echopen.slack.com/team/benschan) was decide to begin playing with real data, so that acquarium datasets have to be released. At the time of writing this post, this was done on the 23.12.16 : with a sponge, a gelpad and [\@jerome](https://echopen.slack.com/team/jerome)'s hand

## 2016.12.14 - HD - 20.00 \(Paris time\)

Soobash: work in progress on the metrics to validate the algos, still need images

Aurélie: denoising night in general to the accurate restitution of the outlines

Sami proposes to bring back a V-scan next time, we understand that Echopen must have the precision of the dinosaur

To foresee: a point doctors and interveners along the chain of acquisition \(Jerome in particular\) to reflect on what is important as characteristics for diagnosis.

In ultrasound, it is mainly the dynamics of the image, the video that is important.

By Saint-Louis, one can recover many videos of V-Scan according to Sami. In addition, they would be annotated.

In Saint-Louis they store a lot of videos, especially since there are not 36000 diagnoses to do.

The basis of the diagnosis is not the image but the video.

## 2016.12.07 - HD - 20.00 \(Paris time\)

* [\@noureddine](https://echopen.slack.com/team/noureddine) : need for a calibration measurement campaign
* [\@djabbz](https://echopen.slack.com/team/djabbz) : need to monitor the phantom to get the first feeling
* [\@djabbz](https://echopen.slack.com/team/djabbz) : need to customize NN to the operator behaviors
* objective of 14.12.16 : compare algo of Djalel’s and Benjamin’s algos. The dataset is the kaggle one : ultrasound image of some nerve segmentation
* [\@noureddine](https://echopen.slack.com/team/noureddine) suggests to be aware of the limits of noising artificially the images, because the nature of noise is singular
* we acted to test [\@benschan](https://echopen.slack.com/team/benschan) and [\@djabbz](https://echopen.slack.com/team/djabbz)’s algo on current implemetation of echOpen’s images dataset
* [\@aurelie](https://echopen.slack.com/team/aurelie) is going to help finish the redpitaya API to get image datasets from th node interface. @mohammed va épauler [\@djabbz](https://echopen.slack.com/team/djabbz) pour le challenge de la semaine prochaine
* [\@hackolite](https://echopen.slack.com/team/hackolite) split the work with @edem : this way
  * Investigation Connection \* mongondb-django
  * Creation of the data model
  * Metric Resource host: cpu / memory
  * Deployment scripts and update
  * Secure executions:
  * scripts SHA-1
  * analysis of the source
    \*capcha
* Improved graphical interface
  * Display detailed info by run
  * Displays images by run
  * Displaying the code for each run
* Automation control of ultrasound
* Production process
* Clean source code

## 2016.12.14 - HD - 20.00 \(Paris time\)

remark the CR is unsualy short because the main typograph had to leave prematuraly the meeting

* [\@noureddine](https://echopen.slack.com/team/noureddine) presented a quick sketch of a review of \(french\) articles
  TODO : contact the authors, mainly at Telecom Paris Tech, Poitiers University, etc
* [\@djabbz](https://echopen.slack.com/team/djabbz) presented his approach on neural networks

## 2016.11.24 - HD - 20.00 \(Paris time\)

* Greating point with Aurélie Mutschler, nuclear physics PHD and Mahdi Mohamed, student currently mastering in Ecole Mines Paris Tech
* [\@hackolite](https://echopen.slack.com/team/hackolite) : GitBook update, GitHub ticketing on place, needs feedback of challenge web-server installation from Edem
* [\@djabbz](https://echopen.slack.com/team/djabbz) [\@noureddine](https://echopen.slack.com/team/noureddine) : mini-course on deep learning approach for denoising images
* ALL Brain Storming on the Kind of Noise
  * How to create a noise as close as possible to the ultrasound conditions
    From a scientific litterature review, we get a handy formula, that should and will be tested -&gt; it is some logxnormal noises
  * It is discriminated between normal electronic noise vs physical noise
    Hence, the question is “how to learn“ ? The process that was agreed on is
    * inject normal noises
    * inject log\*normal noises
    * and acquire aquarium images with moving position, average the signal to get the denoised image
  * It was noticed that the electronic noise is additive vs the physical noise can be reasonably  expected as multiplicative. There will be some challenge around that issue
  * It was noticed that working with a dataset such as kaggle, injecting noise and then train the neural networks could lead to learn the noise itself. This is a point of vigilance
* Upcoming Challenge for the 01.12.16 -&gt; Benjamin vs Djalel : Frequentist vs Deep learning approach
* for the hacker team [\@luc](https://echopen.slack.com/team/luc) [\@benoit](https://echopen.slack.com/team/benoit) [\@hackolite](https://echopen.slack.com/team/hackolite) : we need to acquire in a week long session ultrasound data with moving target in the aquarium, the several positions should be as precise as possible

## 2016.11.17 - HD - 20.00 \(Paris time\)

* new incomer Sébastien Tréguer, data-scientist \#deep learning, came with a colleague, Jan Schlüter, which is a famous one, he is the developer and maintainer of Lasagne, a famous library in Machine Learning, Neural Networks  \(but sorry I didn’t know about that ;\)\)
* Lomé developers were presented to the team because they want to join. The same one are currently deploying a full echOpen instance in Lomé fablab called minodoo.
* [\@hackolite](https://echopen.slack.com/team/hackolite) : finished the web platform and working on the net steps are enhancement
* points were raised about the interest of letting people process the metric extraction scripts on their local with advantages of dealing with different development environment, security, not to worry about infra-structure, concurrent processing
* it was opposed that the idea is to upload algorithms in order to share them publically. But the security concern is a good argument
  provide a cluster architecture in case Big Data training is needed or required
* Remark : if the big data cluster appear not be needed, which tends not to be the case, a complementary solution could emerge for further developments and scripts could be processed locally, denoised images could be sent together with the raw source file of the algorithms
* it is scheduled to implement a data architecture for the probe in the acquarium : the idea is to let the acquire data on regular interval of time, and the average of the acquisition will be a correct sample of denoised images.
* implement the resource metrics CPU, mem and document on GitBook
* [\@benschan](https://echopen.slack.com/team/benschan) is working on a denoising algo with a statistical approach , will finish the implementation for next week and document on GitBook the SigProc metrics choice explanation
* [\@djabbz](https://echopen.slack.com/team/djabbz) is working on a neural network to denoise images through neurla networks, from artificially, will finish the implementation for next week
* [\@noureddine](https://echopen.slack.com/team/noureddine) kicks off a discussion about the noise structure, and suggests to act on noise as soon as possible. A coordination with the electronics team will be scheduled as soon as the hardware is set up.
  The idea is that acting twice both on signal and image denoising could lead to images hard to analyse for the doctors
  It was opposed that signal treatment will be quite simple, mainly envelope extraction and not the phase extraction, which limits the possibility to act at this step. Second, the machine learning will be done on the basis of the image datasets we want to access to. Indeed, the image provider, namely APHP, serves medical imagery devices images and not raw signals

## 2016.11.10 - HD - 20.00 \(Paris time\)

* Annonce d’un nouvel arrivé dans la team Signal Processing : Mohamed Mahdi, polytechnicien de tunis,en ce moment à l’école des Mines, spécialité Robotique & Traitement du Signal
* [\@benschan](https://echopen.slack.com/team/benschan) + [\@djabbz](https://echopen.slack.com/team/djabbz) : travail sur 1 réseau de neurones pour débruitage d’images echo à partir de bruits artificiels.
* [\@benschan](https://echopen.slack.com/team/benschan) rapporte que les algo à l’usage sont aujourd’hui spécifiques des organes explorés. 1 point particulier est relevé autour d’1 algo autour de la carotide et qui est particulièrement efficace
* [\@djabbz](https://echopen.slack.com/team/djabbz) propose d’universaliser les approches par du deep learning
* [\@hackolite](https://echopen.slack.com/team/hackolite) a terminé la plate-forme d’upload d’algo, d’extraction des metrics d’update de leadrboard. Accessible ICI
* prez du code du RAMP, Rapid Analytics and Model Prediction proche de ce que [\@hackolite](https://echopen.slack.com/team/hackolite) a fait
  * [\@djabbz](https://echopen.slack.com/team/djabbz) était un des commiters.
  * [\@djabbz](https://echopen.slack.com/team/djabbz) fait état des besoins d’installation de Tensor Flow, [\@hackolite](https://echopen.slack.com/team/hackolite) est dessus
* proposition de hackolite d’utiliser un sys. de ticketing, sans doute celui de github, car nous commençons à être nombreux;\)

## 2016.10.27 - HD - 20.00 \(Paris time\)

* proposition par Soobash d'un score pour le ranking du leaderboard + discussion sur l'adaptation des métriques de frames d'images
* évolution de l'interface leaderboard par [\@hackolite](https://echopen.slack.com/team/hackolite) TODO : adaptation de l'algo pour calculer les métriques sur une séquence image, plutôt qu'une image tel que c'est le cas aujourd'hui
* présentation par [\@benschan](https://echopen.slack.com/team/benschan) d'une méthode d'injection sur images de bruit spécifique à l'écho. TODO : implémentation d'un premier réseau de neurones pour débruiter des images;\)

## 2016.10.19 - HD - 20.00 \(Paris time\)

* discussion du Challenge online qui sera lancée dès que tout est prêt
  interface web, django app, de récupération, d'analyse des soumissions, et de leaderboard achevée thanks [\@hackolite](https://echopen.slack.com/team/hackolite);\)  TODO :  analyse non d'une image mais d'une boucle d'images + système de login
* scripts de métriques des soumissions terminés thanks Soobash;\) TODO constituer les métriques qui nous sont propres
* demeure la question de l'analyse de la typologie de bruit en vue de pouvoir l'injecter à des "images saines" à des fins d'apprentissage. C [\@benschan](https://echopen.slack.com/team/benschan) qui s'y colle pour la semaine pro thanks;\)

## 2016.10.12 - HD - 20.00 \(Paris time\)

* Présentation de Nourredine Ellouze, ancien dir. de recherche en traitement du signal, avec une focale sur le denoising + ingénieur électrique + plein de choses
* Plate-forme web : achever la plate-forme d'upload/extraction des métriques des algorithmes de débruitage + branchement de la sonde dans l'acquarium
  Challenge : monter un challenge à partir de datasets, soit existant & accessibles via un récent challenge de Kaggle, soit à partir des data d'echOpen
* Algo
  * quel spécificité du bruit échographique ? savoir reproduire artificiellement le bruit pour les injecter dans les images -&gt; priorité de la semaine qui vient
  * les reverse engineerer par réseaux de neurones. A ce titre, Djalel, animateur du groupe IA d'echOpen était présent, car important de maintenir une articulation entre le groupe `Image processing` et le groupe `IA` et a donné des pistes de travail : débruitage, compression du signal
* Au plan pratique, les membres du groupe choisissent de se retrouver tous les jeudis à compter du 27.10.16. Mais semaine pro, la réu a bien lieu un mercredi, soit le 19.10.16

## 2016.10.05 - HD - 20.00 \(Paris time\)

* Soobash continue de scripter les métriques, mais on en a l'essentiel

* hackolite a packagé le script de récupération des algo et d'extraction des métriques selon les scripts de soobash

* l'arcghitecture pour le contributeur évolue dans le sens suivant

  * l'espace ide collaboratif \(cloud9\) permet d'exposer et de jouer avec les codes des contributeurs et leurs libs
  * une interface web/python notebook : avec un "how to" pour package un algo python et qui permet de le soumettre. Le contributeur fait le choix de son environnement de dev et garde ainsi toutes ses routines
    nous processons le package, extrayons les métriques et updatons le leaderboard

* Au total, on est prêt dans 2 ou 3 semaines.

* le bottle neck est la mise en route de l'acquisition dans l'acquarium, idéalement avec fantômes \(rdv à ce sujet dans 2 semaines avec medicalem pour livraison d'un fantôme carotidien\).

## 2016.09.08 - HD - 20.00 \(Paris time\)

* sortie des premiers scripts et métriques. pour les spécialistes, il s'agit calcul  de mse, rmse, ssim -&gt; en cours pour la semaine prochaine
* hackolite commence à updater la boucle de soumission en ajoutant le calcul des précédentes métriques dans son workflow
* soobash finit les scripts relatifs aux calculs de 6 métriques complémentaires
* benschan fait une review de "Despeckle filtering for ultrasound imaging and video, Vol. I: Algorithms and software" , notamment pour explorer les techniques statistiques à l'usage en débruitage



