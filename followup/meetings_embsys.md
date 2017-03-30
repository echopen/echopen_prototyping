# 2017

Embsys meetings usually take place each wednesday at 20 o'clock on [jitsi](https://meet.jit.si/echopenEmbedded).

Everyone is welcomed.

## 2017.03.22 - HD - 20.00 (Paris time)

Notes will be availabled next week.

They can be updated [here](https://mensuel.framapad.org/p/CR_embsys-2017-03-22).

## 2017.03.01 - HD - 20.00 (Paris time)

### Design

#### Polytech-team

Focus on two topics :

* Design a unique PCB + miniaturization. [\@eiffel](https://echopen.slack.com/team/eiffel) notices that the Clarius uses 4 PCB : do we really need a unique PCB ? However, with several piled PCB, component shielding must be handled
* Improve acquisition/treatment in the RedPitaya : design an [intellectual property (IP)](https://en.wikipedia.org/wiki/Semiconductor_intellectual_property_core ) in [VHDL](https://en.wikipedia.org/wiki/VHDL ) for the acquisition, implement numerical envelope detection (double FFT) in VHDL (currently implemented in C)

**Remark** : RedPitaya's ADC are clocked at 100MHz which is quite powerful

Next week's objectives : Focus on analog part --> study circuits, remove useless components, study the noise in the system


#### Lausanne antenna

[\@massoud](https://echopen.slack.com/team/massoud) wants to benchmark an ADC to see if he can get a sampling frequency of 50 MHz from the latter.


### Frequencies of transducers

The frequencies of the 3 transducers will be:

* 3.5 MHz,
* 5 MHz (this transducer requires an ADC at 25 MHz to be suitably used),
* 7.5 MHz

## 2017.02.15 - HD - 20.00 (Paris time)

### Aim of the echopen device

The ideal goal would be to get 15 medical quality images per second that can detect 1 mm defects while remaining low-cost.
If compromises have to be made it is necessary to maximize the quality of the image leaving to lose **a little** on the low-cost side.

All calculations (signal processing) must be done on the device. It is necessary to minimize the execution on the phone.


### Current Device

The current arrangements include:

* A 18 V supply generates several voltages, one of which is -100 V to operate the transducer. To excite it also requires a pulse with a MOSFET. However, it is necessary to curb the voltage with a T / R switch so as not to grill everything. A band-pass filter (analog or digital) makes it easier to detect envelopes.
* The system entries are:
* The viewing angle of the image,
* The line number of the image that impacts the framerate,
* Depth of vision

* The Red Pitaya card handles the digital side:
* ADC,
* DAC

The ADC and DAC of the Red Pitaya are addressed from the FPGA of the card.


### Altran

The goal at the end of the collaboration would be to have about a hundred devices that can be clinically tested **in some countries** (with monetary standards binding as the United States or France).

#### The needs that Altran could fill

There are therefore several needs that Altran could fill:

* In mechanics: with the probe head (with 3 transducers encapsulated in an oil bath, the liquid must have an impedance close to water),
* Analog: amplification (45 dB to 90-100 dB), electromagnetic shielding (noise protection) and transformer (wires will not do the job due to the movement induced by the transducer),
* An industrialization dossier,
* Medical certifications,
* Mechanical packaging (integration),
* Open source community project management,
* Someone who can manage the life cycle of a product
* Envelope detection: digital or analog

To seduce Altran you need:

* A block diagram,
* A document summarizing the needs and bottlenecks

The ideal ADC should allow to have 100 MHz (which is rather big). The ideal DAC should convert 100 KB / s.

Bottlenecks and the theoretical figures of the desired performance are absolutely necessary.

Altran should not lose sight of the **open source side** (they should not give us files usable only with proprietary software linked to very expensive licenses).


### Digital System and Analog System Comparisons

Digital system:

* numeric (manipulation of 0 and 1 only),
* Doppler (this is not in the specifications of the first version),
* more expensive,
* requires a 45 MHz ADC

Analog system:

* cheap,
* less flexible

### Proposed approaches

Romain proposes a double approach:

* Acquisition developed and optimized for us in pure analog
* Non-low-cost digital approach combining an embedded system and an FPGA
* It is necessary to keep in mind the mechanical constraints (dimensions) of the box and the thermal questions related to the miniaturization

**The mechanics** fixes a large part of the constraints, it is necessary to design something industrializable.
It is also necessary to keep in mind the fact of being certified medical device (for example with the extensions of video file).

## 2017.01.04 - HD - 20.00 (Paris time)

### Agenda

1. Introduction and presentations (newcomers)
2. Current status of the embedded platform
3. Hardware/processing needs and wishes
4. Processing split (Hardware/Embedded Software/Smartphone)
5. Hardware proposals

### Attendees

[\@rbo](https://echopen.slack.com/team/rbo)
[\@benchoufi](https://echopen.slack.com/team/benchoufi)
[\@eiffel](https://echopen.slack.com/team/eiffel)
[\@aurelie](https://echopen.slack.com/team/aurelie)
[\@omaciu](https://echopen.slack.com/team/omaciu)

Benjamin, Mohammed, ??? sorry if I missed someone

### Discussions

#### Introduction and presentations (newcomers)

Everyone gives a short presentation of him/herself and his/her interests in the project.


#### Current status of the embedded platform

[\@jcbillard](https://echopen.slack.com/team/jcbillard) being absent, this point is not discussed further.


#### Hardware/processing needs and wishes

Before going to deep in the specifications of the system a list of needed and wished features must be established.
Besides the raw acquisition from ADCs and scan conversion, the embedded system will have to support additional features.
Identified features and functionalities include:

1. WiFi communication with the smartphone
2. Commands/configuration from the smartphone (gain adjustment, frequency,...)

To identify all needed and wished features a brainstorm document has been created by [\@rbo](https://echopen.slack.com/team/rbo) so that everyone can put his ideas:
https://annuel.framapad.org/p/embsysBrainstorm


#### Processing split (Hardware/Embedded Software/Smartphone)

Today signal processing and scan conversion are performed on the embedded system (RedPitaya) and images are sent to the smartphone.
An analysis should be done to know the better way to split the processing between the embedded system and the smartphone. Should the embedded system perform the signal processing and scan conversion or should raw signals be sent to the smartphone and the processing done on the smartphone ?

#### Hardware proposals

##### [\@jcbillard](https://echopen.slack.com/team/jcbillard)

__Main CPU__:
[Texas Instruments OMAP-L138](http://www.ti.com/product/OMAP-L138)

* ARM9 + C674x DSP cores at 450 MHz
* uPP (Universal Parallel Port) useful for interfacing ADC
* Available Linux support

__ADC__:
[Texas Instruments ADS6142](http://www.ti.com/product/ADS6142)


##### [\@rbo](https://echopen.slack.com/team/rbo)

__Main CPU__:
[NXP i.MX7](http://www.nxp.com/products/microcontrollers-and-processors/arm-processors/i.mx-applications-processors/i.mx-7-processors:IMX7-SERIES)
* ARM Cortex A7 single/dual core \@ 1 GHz + ARM Cortex M4 at 200 MHz:

__ADC__:

### Action items

How do we handle tasks/issues ? Github issues, [Markdown task lists](https://github.com/blog/1375-task-lists-in-gfm-issues-pulls-comments), bugtracker ?

Methodology to use on github repositories and way of handling tasks/issues to be discussed and harmonized at project level for all repositories/groups.


### Next meetup

January 6 2017, 20:00 to discuss some hardware specific stuff with [\@jcbillard](https://echopen.slack.com/team/jcbillard)