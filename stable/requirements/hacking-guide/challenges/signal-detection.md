# signal detection

## Challenge

The contributor have to propose a signal envelope detection technic

## Difficulty \(1-5\)

3

## MISSION

### PROBLEM

There are many techniques to recover the signal envelope. In general, one operates a Hilbert transform to recover an analytical representation of the signal.

Besides, it appears that the signal phase is generally not exploited. This can provide a relevant use of this type of data

For the record, echOpen team uses a pseudo-Hilbert transformation, that is to say by crushing to 0 the Fourier transform for negative frequencies.

#### side problem but related

One short comment about signal filtering that can be also challeging. The data output of ADC \(ADC\) are 8bit or 14bit signed. It would be of very interest to filter the data in the spectral domain of interest: for example, using a Hamming or Hanning windowing or other!

Let's say there are two types of filtering

* fundamental, dedicated to deep organs exploration
* harmonic, solution for a better resolution

![alt tag](http://wiki.echopen.org/images/c/ca/Screen_Shot_2015-09-08_at_15.10.24.png)

### REWARD

* Residency in our [Head Quarters](https://www.google.fr/maps/place/Point+Zéro+des+Routes+de+France/@48.8533289,2.3467055,17z/data=!4m13!1m7!3m6!1s0x47e671e10bc2d769:0x93bcbce92cd56429!2sParvis+Notre-Dame+-+Pl.+Jean-Paul+II,+75004+Paris!3b1!8m2!3d48.8533289!4d2.3488942!3m4!1s0x0:0x16a14abd23a6dd0d!8m2!3d48.8534033!4d2.3487836) located at the very center of Paris, on le Parvis de Notre Dame \(hosting and breakfast \)
* DevBox USB keys at your name, T-shirts and other Goodies 
* Mention on our Hall of fame of open sources dudes

### RESSOURCES

* The device output dataset of echOpen hardware is available on the Github repo [kit-soft](https://github.com/echopen/kit-soft/tree/master/data) 

You'll find a `raw_data.txt` file is the raw data of an image

* 61 lines
* On each line, there are 16385 values. The first is the number of the line \(it is recommended to remove this mark\), and other values correspond to the acquired signal in volts on the line.

If you want to access the data simulation, please check this [doc](https://echopen.gitbooks.io/android-app/content/playing_with_data.html)

#### libraries

Check libraries serving FFT !

### REPOS

Pull-requests are submitted on this [REPO](https://github.com/echopen/kit-soft)

### SUDOERS

[@jerome2echopen](https://github.com/jerome2echopen), jerome@echopen.org

### ECHPERTS

[@jerome2echopen](https://github.com/jerome2echopen), jerome@echopen.org

