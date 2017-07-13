# Analog envelope detection

## Short description
The transducer sends an ultrasound pulse at a given frequency (5 MHz for axample). The pulse lasts about two periods. If the wave hits an interface between two different tissues, an echo is received by the transducer. That echo is also a pulse. Its amplitude is much lower than the emitted pulse, but its shape is supposed to be quite similar (if we don't take dispersion in the media into account). Envelope detection is a process that allows the detection of a pulse. It usually turns a high frequency signal into a low frequency signal. It can be processed directly on the analog signal or later on the digitalized signal. For the moment, envelope detection is performed thanks to a diode and a low pass filter, but it is not really satisfying. The challenge here is to find a better solution.

<figure>
  <img src="/challenges/envelope_detection/envelope_detection_principle.png" alt="" />
  <figcaption> Figure 1: ideal envelope detection. The blue curve is the high frequency signal, the red curve is the envelope.
  
  Image source: https://mysliceofraspberrypi.files.wordpress.com/2013/10/4248c-analytic.png</figcaption>
</figure>

## Objectives
We would like to perform a good envelope detection before the ADC conversion. Indeed, as the pulses' length is of two periods approximately, the signal frequency would be divided by two and a slower ADC devise could be used, which would make the echOpen device cheaper than if we performed envelope detection after the ADC conversion.

The characteristic time of the detector has to be chosen so that the envelope can be detected at each of the three working frequencies (3.5MHz, 5MHz and 7.5MHz). But on the other hand, it has to be possible to detect two interfaces that are close to each other, so a compromise has to be found.


## Current solution
The current solution is a simple diode in series with a low pass filter.
<figure>
  <img src="/challenges/envelope_detection/envelope_detector.gif" alt="" />
  <figcaption> Figure 2: simple envelope detector
  
  Image source: https://www.st-andrews.ac.uk/~jcgl/Scots_Guide/RadCom/part9/fig2.gif</figcaption>
</figure>

It is not satisfying because: 
* the quality of the obtained envelope signal is not good enough
* if a secod pulse arrives at the transducer just after a first one, it is not detected with its real amplitude.

## State of the Art
Different solutions exist to perform analog enveloppe detection, using transistors or operational amplifiers. Each of them has advantages and inconvenients. Below are a few examples of envelope detectors:

<figure>
  <img src="/challenges/envelope_detection/Envelope_Detector.png" alt="" />
  <figcaption> Figure 3: example of an envelope detector with op-amps
  
  Image source: http://n1qq.com/wordpress/wp-content/uploads/2016/04/Envelope-Detector.png</figcaption>
</figure>

<figure>
  <img src="/challenges/envelope_detection/envelope-detector-common-base-detector-circuit.png" alt="" />
  <figcaption> Figure 4: common-base envelope detector
  
  Image source: http://www.interfacebus.com/envelope-detector-common-base-detector-circuit.png</figcaption>
</figure>

<figure>
  <img src="/challenges/envelope_detection/envelope-detector-common-emitter-detector-circuit.png" alt="" />
  <figcaption> Figure 5: common-emitter envelope detector
  
  Image source: http://www.interfacebus.com/envelope-detector-common-emitter-detector-circuit.png</figcaption>
</figure>



## Challenge progress
0%


## Resources
The probe sends pulses at different frequencies. Each pulse lasts between 1.5 and 2 periods. 3 frequencies are used in the probe: 3.5MHz, 5 MHz and 7.5MHz. The amplitude of the envelope ranges from 0V to 1V.

A few links that may (or may not) be helpful:
* [http://www.interfacebus.com/Glossary-of-Terms-transistor-envelope-detector-circuit.html](http://www.interfacebus.com/Glossary-of-Terms-transistor-envelope-detector-circuit.html)
* [http://n1qq.com/blog/2016/05/](http://n1qq.com/blog/2016/05/)


## Details

### Skills 
* Fair skills in electronics
* Basic knowledge of envelope detection or amplitude demodulation


## Level 3
e.g. difficulty of the challenge (from 1 to 5).

## Team
This challenge was suggested by the Hardware team. Information to contact them is available [here](./howto/teams.md).
