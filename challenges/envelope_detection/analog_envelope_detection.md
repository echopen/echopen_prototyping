# Analog envelope detection

## Short description
The transducer sends an ultrasound pulse at a given frequency (5 MHz for axample). The pulse lasts about two periods. If the wave hits an interface between two different tissues, an echo is received by the transducer. That echo is also a pulse. Its amplitude is much lower than the emitted pulse, but its shape is supposed to be quite similar (if we don't take dispersion in the media into account). Envelope detection is a process that allows the detection of a pulse. It usually turns a high frequency signal into a low frequency signal. It can be processed directly on the analog signal or later on the digitalized signal. For the moment, envelope detection is performed thanks to a diode and a low pass filter, but it is not really satisfying. The challenge here is to find a better solution.

<figure>
  <img src="/challenges/envelope_detection/envelope_detection_principle.png" alt="" />
  <figcaption> Figure 1: ideal envelope detection. The blue curve is the high frequency signal, the red curve is the envelope.
  
  Image source: https://mysliceofraspberrypi.files.wordpress.com/2013/10/4248c-analytic.png</figcaption>
</figure>

## Objectives


## Current solution
The current solution is a simple diode in series with a low pass filter.


## State of the Art

## Challenge progress

## Resources

## Details

### Skills 
* Skill 1
* Skill 2
* Skill 3

## Level 3
e.g. difficulty of the challenge (from 1 to 5).

## Team
This challenge was suggested by the Hardware team. Information to contact them is available [here](./howto/teams.md).
