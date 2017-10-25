# Protocol for image quality assessment

## Measurement of spatial \(detail\) resolution

### A few remarks about spatial resolution

* We want to measure both lateral and axial resolutions :

  * **lateral resolution** : perpendicular to the propagation axis of the acoustic pulse, in the plane of the image  
    depends mainly on the transducer's focalization, but may also by affected by the number of lines, post-processing such as envelope extraction, signal-to-noise ratio, etc...

  * **axial resolution** : parallel to the propagation axis of the acoustic pulse  
    depends mainly the transducer's frequency, but may also be affected by ADC sampling rates, post-processing such as envelope extraction, possible defaults in the TGC, signal-to-noise ratio, etc...

* **Spatial resolution vary as a function of depth** \(relatively to the transducer's position\)

  * For lateral resolution, this is directly linked to the focalization of the transducer. Axial resolution may vary as well because of possible defaults in the TGC or because of noise. For this reason, we have to monitor the resolution as a function of depth in both cases.

  * To do so, we need to perform measurements while being able to **fix precisely the distance** to the transducer

  * The distance interval in which a transducer will be used depends on its frequency \(and this latter directly determines the axial resolution\). So we need to **compare the resolutions only for transducers that have comparable frequencies**.

  * Resolutions have to be measured in the range of depths that have been previously determined depending on the transducers' frequencies \(see table below\). For each range, we need to perform several measurements \(let's say about 10 for example, which would roughly correspond to measuring the resolutions with a step of 1cm in depth\)

    | Frequency \(MHz\) | Focal zone \(mm\) |
    | :--- | :--- |
    | 3.5 | 50 - 150 |
    | 5 | 30 - 105 |
    | 7.5 | 10 - 75 |

### Phantoms for spatial resolution

The phantoms that could be used for spatial resolution are represented in the figure below \(the position of the probe is represented by a trapezium\). The resolution corresponds to the minimum value of x that allows to distinguish two neighboring wires \(black dots\).

* D must be carefully fixed for reproducibility
* d is the \(constant\) step in depth for resolution measurements. Typically, d=1cm. Knowing D, we can assess the distance for each point of measurement
* From the table above describing the ranges of interest, L=10cm typically.
* For each kind of measurement \(lateral vs. axial\), several phantoms have to be made, by varying x. As the resolution is expected to be about a few millimeters, interesting values for x are : 1mm, 2mm, 3mm, 4mm, 5mm

![](/assets/phantom_spatial_resolution1.png)

### Protocol for spatial resolution

For a given combination of transducer + acquisition/processing chain :

* Fix one phantom by respecting the chosen value for D \(D must be the same for each device being tested, obviously\)

* **Save a few images and the corresponding raw signals \(this is for the specific task of envelope extraction, jump **[**here**](/inprogress/mobile_app/characterization/specific-protocol-for-tests-of-alternative-methods-for-envelope-detection.md)** for more details\)**

* Repeat with each phantom

* The lateral/axial resolution corresponds to the minimal value of x allowing to distinguish two neighboring wires.

**The figure below shows the curve that is expected from these measurements \(one curve for lateral and another one for axial resolution\) :**

![](/assets/spatial_resolution_curve.png)

## Measurements of sensitivity

coming soon...

## Measurement of contrast resolution

coming soon...



# List of authors

[Aurélie](https://github.com/aurelie-mutschler)

