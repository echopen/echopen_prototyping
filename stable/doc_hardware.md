# Hardware documentation

In this section we present a short documentation of our kit. More informations about the hardware can be found in our [website](http://echopen.org/doc-website/CAT-configuration/CFG-sweeping_probe/content.html) or download our [github folder](https://github.com/echopen/PRJ-medtec_kit), aquarium configuration (PRJ-medtec_kit/configuration/CFG-aquarium_kit/readme.md). We show block and synaptic diagrams of the kit and give some informations about daughter boards and modules.

### Block diagram

![](./doc_hardware/block_diagram.png)

### Synoptic diagram

![](./doc_hardware/synoptic_diagram.png)

## Device informations

### Acoustic

* We use a commercial transducer from imasonic with a central frequency of 3.27 MHz. Technical informations about the transducer (temporal and frequential pulse respectively) can be found in the following images

![](./doc_hardware/signalt.png "Temporal pulse of the transducer") 

![](./doc_hardware/signalf.png "Frequential pulse of the transducer")

* Pulse duration at -6 dB is 382 ns, so we have a precision of 0.56 mm.

* Transducer pass-band is 2.13 MHz, from 2.21 to 4.33 MHz.

* Focal depth: 120 mm.

* Excitation time: around half the period = 142 ns.

* Excitation voltage: around -100 V.

### Electronic

Actually we still use two evaluation kit:

* Pulser: MAX4940EVKIT
* ADC: AD8331-EVAL

and three commercial boards:

* Stepper driver: A4988
* Arduino: arduino nano
* Acquisition: RedPitaya

We use an arduino nano because the GPIO of the RedPitaya are two slow to drive the pulser (minimum 500 ns), with the arduino (16 MHz clock) the command can be a multiple of 62.5 ns.

The output of the high voltage circuit is around -97 V.

Pass-band filter is centered around 3.5 MHz.

TGC caracteristic:

* Amplification command: between 0 and 1 V
* Amplification on LO gain mode: from -4.5 to +43.5 dB
* Amplification on HI gain mode: from +7.5 to +55.5 dB
* Output: between -2.5 and +2.5 V


### Mechanic

For making a sector image, we must transmit a sweeping movement to the transducer. This is done with a stepper motor. With the stepper driver we can easily change the direction of the steps. At start the motor turn and fix to a mechanical stop (so we now it's position) and the we make the sweeping movement.

### Acquisition

Acquisition is made with a RedPitaya, caracteristic:

* Sampling rate: 125 or 125/8 Msps
* Precision: 14 bits
* Voltage range: +/- 1 V or +/- 20 V
* Buffer maximum size: 16384 points

Considering that the acoustic waves makes back and forth, depth of measurement is given by d=v*t/2. So maximum depth at 125 Msps is **97 mm** and at 125/8 Msps it is **775 mm**.

### Settings

Defaut settings are:

* RedPitaya intput range: +/- 20 V (because TGC output range is +/- 2.5 V)
* RedPitaya sampling rate: 125/8 Msps (because depth of measurement is to short at 125 Msps)
* TGC: LO gain mode (less amplification but too much noise on HI gain mode)
* TGC amplication command: between 0.3 and 1 V (so amplification is between 10 and 43.5 dB)
* Depth of measurement: between 80 and 160 mm
* Pulser command duration: 125 ns

A sampling rate of 125/8 Msps would be preferable but depth is too short and the transmission of data become quite longer (because there is 8 more data to sent).

Even if TGC output is theoretically in range +/- 2.5 V, generally it is between +/- 1V. For safety we must keep an input range of the RedPitaya in range +/- 20 V. These means that instead of having 16384 points of precision, we just have around 800 points of precision.

