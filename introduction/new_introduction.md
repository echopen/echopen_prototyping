# Introduction
_This section is in construction_

## How medical ultrasound works ?

This imaging technique is based on the propagation of ultrasound in the human body in order to realize medical diagnosis. Ultrasound is sound waves at frequency higher than those our ear can perceive. It behaves as the traditional sound we know and with a view to visualize how it propagates we can think at waves undulating on the surface of water. 

### Using the pulse echo sequence for ranging objects 

To localize objects we use the pulse echo concept. Remember last time you yelled in a valley ? Your voice bounced on the mountains and came back to your ear after some delay. To know how far is a cliff in front of you for example the idea is to measure the time your cry takes to come back to your years. Knowing the  sound speed in air you can easily retrieve the distance as it is half the delay times the sound speed. The half factor count for the fact that our cry traveled a two way trip. A lot of animals use this principle to perform echolocation as bats or dolphins allowing them to "see with their ears". 

### Both an emitter and a receiver: the transducer

In the case of medical ultrasound, we both emit and receive ultrasounds with a unique device called transducer. This latter is made of a special material subject to a phenomenon called piezoelectricity. When a mechanical stress is applied to such a material, it reacts by accumulating electric charges. As sound is nothing else than a mechanical vibration, the sound arriving on the transducer implies a mechanical stress which is converted in a electrical tension that can be measured. The contrary is also possible. If a voltage is applied to the transducer this will lead to a mechanical stress which will propagate as ultrasound waves through the medium we want to investigate. 

### Reflections: a matter of acoustical impedance 

Unlike echolocation that aims to locate objects from reflection on their surface, medical ultrasound aims to produce an image of a medium by making ultrasounds penetrating it. Our body is made of bones, liquids, tissues... offering a complex geometry for our waves. To understand how waves are reflected in this complex medium, we first must understand how a wave is reflected at an ideally flat interface of different material.

At the interface between two mediums any incident wave splits in a transmitted and a reflected wave. The proportion of the reflection in relation to the transmission only depends on what we call the acoustical impedance of our two mediums. It is the product of the density with the sound speed. The more the acoustical impedances of the two mediums are different, the more the wave is reflected. For example the interface between air and water is really reflective as the density of water is much superior as the one of air (while the speed of sound is five times faster in water than in the air). This explain why we must use gel between a probe and the body : any left air would prevent ultrasound to penetrate our skin.

### Ultrasound imaging: a reflectivity map

Our body is mainly composed by water so the acoustic impedance of our different tissues don't variate so much around the value of the one of water. As we don't have huge differences of impedance the body is not so reflective for ultrasounds (except for the bones). If we send ultrasounds it will be mainly transmitted and at each depth a small partially reflected wave will propagates back. The more the variation of the local acoustic impedance is important, the more the wave is reflected. This leads us to what is an ultrasound image, it is a map of the reflectivity to ultrasound. So what is highlighted by this modality of imagery are interfaces. It's quite natural for our brain to think to objects by their edges so almost no further processing is needed to interpret this image.

### Assessing the origin of reflections by focusing

The delay between pulse and echo allows us to range the depth of the reflections occurring along the path of the ultrasonic pulse. But to form a proper 2D image we also need to know the direction those reflections come from. In order to fulfill that need a solution is to focus the waves we send so that they travel along a line instead of propagating in every direction. It's the same idea than putting your hand around your mouth to direct your voice to somebody. By using acoustical lenses (that behaves the same as a classical magnifying glass but for sound) or by shaping the transducer in a parabolic way we can form a narrow beam along the which our pulse will propagate. This done, we know that the echoes we will receive will come from reflections along that line.

This improvement permit to probe our medium line by line. To form an image we must scan an area. A way to do that is to rotate the transducer. The transducer is placed fully at left for example. A first pulse is emitted, echoes are recorded. Then the transducer is rotated just a bit and another pulse echo sequence is achieved. We repeat this process until the area of interest is swept. More modern approaches use several transducers to achieve both synthetic focusing and fast scanning with improved resolution but they are out of reach for this introduction. 

## Our solution: be simple, be low cost

We could keep talking for hours on ultrasound imaging as this technology have been under heavy development since decades. But we will stop here for the theory and go straight to the minimal hardware required to achieve an ultrasound image. More will be explain when needed. 

### A unique rotating transducer

Our solution to tackle the imaging processed is based on the first generations of scanners because of their simplicity. Those latter were based on a unique rotating transducer. To gain versatility, probes were usually embedding several transducers as a unique transducer design couldn't fit all imaging purposes.

### The minimal acquisition chain

To summarize the process of acquisition we first must get the transducer into position thanks to a motor then excite this latter with a circuit called a pulser. Once this is done, the transducer is switched in a listening mode. The signal is amplified by a variable gain amplifier as signal coming from deeper reflection need to be further amplified because of the attenuation of ultrasound by human tissues. The signal is then digitalized and some processing is achieved to extract the envelope as it is the relevant information we want to display. Some denoising can be applied at this step. The collected lines are then send to the smartphone via wifi where the scan conversion is achieved. This last step consists at rendering a conical image from the different recorded lines. 

Here a simplified flowchart of the full device. Click any part to learn more about it !

```mermaid
graph TD;

p[pulser]
s{switch}
t[transducer]
m((medium))
a[variable gain amplifier]
d[digitalization]
e[envelope detection]
c[scan conversion]
l[display]

subgraph device
a-->d
d-->e

p--high voltage <br/> emission-->s
s--low voltage <br/> reception-->a
s---t  
end

subgraph smartphone 
c-->l
end

e-.wifi.->c
t-.ultrasound <br/> propagation.->m
```

## Scan conversion

The Scan Conversion allows one to recreate a clinical image from a set of data sent by a probe. The received image depends on the geometry of the probe. This process intends to recreate the 'real' image.

An ultrasound beamformer generates coherently summed image data in polar format while the standard TV raster display is rectangular. Hence, polar to Cartesian scan conversion is necessary before display. A combined design scheme for polar to Cartesian scan conversion using nearest neighbor and linear interpolations has been implemented which optimizes both image quality and hardware requirement.  
The scan converter takes polar data as input and produces corresponding rectangular data which is used for image formation. The radial distance becomes somewhat larger as one moves deeper into the body and this produces serious artifacts in the image called Moiré artifacts. Hence interpolation becomes necessary. The nearest neighbor interpolation is a simple method although it makes the image blocky. On the other hand, linear interpolation needs a few computations but is free from these artifacts in the far field.

![ alt tag](http://wiki.echopen.org/images/c/c6/Image02.jpg)

Indeed, the probe stores a series of sampled scan-lines, whatever the geometry of the scanned area.

Which can be represented with clinical images such as :

![alt tag](http://wiki.echopen.org/images/7/7d/Image04.png)  
![alt tag](http://wiki.echopen.org/images/b/b8/Image03.png)

These two images are before/after scan conversion of an image of a liver
