# EchOpen mobile application

## Pre-requisites

## User Experience

to be completed with mobile app existing templates and user workflows 

## Specifications

## Development Strategy

The mobile application development is currently focus on:

* finalize prototype on** master branch **to support new data format received from echOpen device

* migrate from prototype to healthcare compliant application on** **_**phaino branch**_

  * integrate new UI 
  * secure and plug one by one prototype backend module on the new healthcare compliant application 
  * improve unit test coverage 

## Architecture

#### prototype architecture

![](/assets/ExistingMobileHighLevelArchitecture.jpg)

#### 

#### healthcare compliant architecture

The new architecture will follow the MVP design guidelines. 

It can be split in different parts: 

* **RealTimeImageProvider: **it will receive data from echOpen device and generate a to-be-displayed image on a separate thread.
* **EchOpenActivity**: the main echOpen app activity that will handle application lifecycle and connection with data sources
* **Presenters**: each Presenter will implement a single application functionnality logic.
* **LayerDrawable**: a multi-layer drawable that will allow us to blend Ultrason image with graphics objects and patient annotations 

![](/assets/FuturDesignMobileAppArchitecture.jpg)

## Source Code

The EchOpen mobile application source code is open source, distributed under BSD 3-clause license and available on [Github](https://github.com/echopen/PRJ-medtec_androidapp).

