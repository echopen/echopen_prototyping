# Product backlog

> The product backlog comprises an ordered list of requirements that a scrum team maintains for a product. It consists of features, bug fixes, non-functional requirements, etc.—whatever must be done to successfully deliver a viable product. The product owner orders the product backlog items \(PBIs\) based on considerations such as risk, business value, dependencies, and date needed.
>
> Items added to a backlog are commonly written in story format. The product backlog is what will be delivered, ordered into the sequence in which it should be delivered. It is visible to everyone but may only be changed with the consent of the product owner, who is ultimately responsible for ordering product backlog items for the development team to choose. \[Wikipedia-Scrum\]\([https://en.wikipedia.org/wiki/Scrum\_\(software\_development\)\#Product\_backlog](https://en.wikipedia.org/wiki/Scrum_%28software_development%29#Product_backlog)\)

Here is a synthesis of the technical constrains to be addressed by the device. These ones are deduced from the CapMed that took place on June 18th, 2016.

## Usage

The echOpen device is meant to be a universal ultra-portable ultrasound imaging or medical visualization tool, intended to accompany health professionals in clinical practice of diagnostic orientation. Echostethoscopy is primarily aimed at physicians who have never take ultrasound images and who have taken a 48-hour training program to master the gesture and the concept.

The echOpen probe is an internal echo-anatomy visualization tool used in the clinical examination, enabling healthcare professionals to:

* See inside the body
* Find an organ, a vascular structure, ...
* Estimate its volume \(large, medium, small\) and its dynamics, without tissue analysis
* Supplement clinical semiology for diagnostic guidance for general practitioners and specialists

It is not :

* A complementary review tool
* A per se imaging tool
* A tool for tissue analysis

For now, Doppler ultrasonography is out of the scope of the developments.

The device goes with an app which allows to display the images on a smartphone, control some device parameters, store and share screenshots or video sequences. Some sets of parameter settings have to be pre-defined, allowing the user to load some pre-determined settings depending on the patient's characteristics \(gender, height, weight...\) and the targetted organ.

## Image characteristics

The echOpen device is meant to produce ultrasound images in [B-mode](http://assets.cambridge.org/97805217/57102/excerpt/9780521757102_excerpt.pdf). For a real-time usage, the images are expected to be displayed with a minimal framerate of 10fps.  
The image quality must be compatible with the medical usage described above. For this reason, the expected resolution must be about 1mm at distances that are relevant for the examination of a patient. The detailed technical constrains related to image characteristics are listed in [Technical constrains](backlog/technical.md).

## Main technical requirements

* Three different frequencies \(3.5 MHz, 5MHz, 7.5MHz\) for different medical applications
* Mechanical probe: rotative or oscillant head with one piezo per frequency
* Ultra-portable: the whole device can be carried in a blouse pocket, limited weight
* Robust: the device should be resistant to a 50cm fall \(which approximately corresponds to the height of a bed\)
* Sufficient battery life: at least one hour of continuous use
* Waterproof and easy to clean
* Low-cost: affordable for a healthcare professionnal



