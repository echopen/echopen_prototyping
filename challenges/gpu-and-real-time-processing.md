# GPU & real time processing

## Context

It is of critical importance that the image that is displayed on the device is in perfect adequation with the position of the probe. Indeed, the healthcare operator holding the device needs to put together the position of his hand, and so the anatomical perspective he should see, and the displayed image. Therefore, real time processing is one of the greatest challenge echOpen’s software has to face.

Some developers of our community think that, as far as algorithms are parallel processable, we should use GPU implementation. Historically, we developed an OpenCL solution which appeared to be great wth regards to performance and quite deceptive because OpenCL is not supported any more. The framework that is supported by a fast-growing community is called VULCAN.

So your challenge will be to implement a VULCAN solution to some algorithm that are already in use. We think ScanConversion algorithm is good candidate to begin to get hands on VULCAN. All the informations about ScanConversion are available [HERE](../introduction/new_introduction.md). We stress the fact that your job is not create a new ScanConversion algorithm but to implement a VULCAN solution on this algorithm.

We are going to release soon an encapsulate of ScanConversion algorithm in a single android app.

Of course, any real time complementary solution to GPU is welcome. Just tell us ;\)

## **NB \(07.05.17\)**

At the time of writing this paragraph, the current implementation \(available [here](https://github.com/echopen/PRJ-medtec_androidapp/) @ commit \) for running our algos are based on \`RenderScript\`. Indeed, Vulcan seems to be still poorly supported and scarcely implemented on Android smartphones. Anyway, the challenges is still valid ;\)

## Difficulty \(1-5\)

4

## REWARD

* Residency in our [Head Quarters](https://www.google.fr/maps/place/Point+Zéro+des+Routes+de+France/@48.8533289,2.3467055,17z/data=!4m13!1m7!3m6!1s0x47e671e10bc2d769:0x93bcbce92cd56429!2sParvis+Notre-Dame+-+Pl.+Jean-Paul+II,+75004+Paris!3b1!8m2!3d48.8533289!4d2.3488942!3m4!1s0x0:0x16a14abd23a6dd0d!8m2!3d48.8534033!4d2.3487836) located in the very center of Paris, on le Parvis de Notre Dame \(hosting and breakfast \)
* DevBox USB keys at your name, T-shirts and other Goodies
* Mention on our Hall of fame of open sources dudes

  ## SUDOERS

[@nowami](https://github.com/benchoufi) nowami@echopen.org

