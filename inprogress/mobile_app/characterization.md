# Characterization

We're currently working on several paths related to characterization issues. Now that we have a fully functional prototype, the objective is to develop a set of reproducible processes that will allow us to determine quantitative metrics to assess the image quality.

## Why ?

On our way towards industrial pre-series, we're facing some open questions that have to be addressed :

* Anticipating some requirements for certifications processes, we would like to **develop a set of simple, low-cost and reproducible methods for assessing basic image quality metrics**, among which :

  * **Detail resolution** \(or resolution integral\), which is related to the frequency and the focalization of transducers
  * **Sensitivity** / Signal-to-Noise Ratio / Penetration \(these metrics are linked together\)

  * **Contrast resolution**  
    For more details about these metrics, jump [here.](/references/sigproc/new_IMGQ_metrics.md)

* To refine our technical specifications, we want to **characterize some existing ultrasound-imaging devices** in terms of the metrics cited above, so as to **define some reference quality metrics** to be achieved by our device.

* We're currently sourcing some transducers. We roughly know the specifications that are required but we need to be able to compare different solutions, and in particular to **find the best trade-off between image quality and the cost of the transducers**. Then, one important question is : How much can we deteriorate the characteristics of transducers relatively to our specifications, in order to lower the costs of production ?

* One important step in the image construction is the so-called envelope detection. This latter can be performed either numerically or within an electronic component. The choice of analog vs. digital implementation has a huge impact on the whole acquisition chain and then on costs \(the analog solution would be cheaper\). We'd like to **test whether it's possible to implement an analog envelope detection that would still allow to get a good quality image**, i.e. comparable to a gold standard obtained from a digital Hilbert transform.  
  Besides, digital methods that are less computer-costly than the Hilbert transform are being investigated by some students from Polytech'Nantes. The alternative implementations they will propose will be evaluated by comparing the quality of the images they obtain to gold standards obtained from an Hilbert transform.

## Ongoing work

In this section, you'll find some documents about ongoing developments related to characterization :

* **Focal zone of transducers** : description of our home-made test bench for the sourcing and test of transducers
* **Protocol for image quality assessment** : description of the procedures and phantoms required to extract basic quality metrics and compare two different devices
* **Benchmark of existing devices **
* **Protocol for envelope detection methods** : specific procedure for comparing analog and digital \(Hilbert transform or alternatives\) envelope extraction methods.

## List of Authors

[Aurélie](https://github.com/Aurelie-Mutschler)



