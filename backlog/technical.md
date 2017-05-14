## Technical specifications


| Item | Target | Achieved | Completion status |
| :--- | :--- | :--- | :--- |
| Spatial resolution (mm) | longitudinal : 1mm <br> lateral : 1mm | to be quantified | - |
| Number of transducers | 3 | 1 (transducer A) | 33% |
| Angular sector (°) | 60 | 60 | 100% |
| Number of lines | 128 | 64 | 50% |
| Framerate (fps) | 10-20 | 2 | 10-20% |
| Cost (€) | 500 | 1200 | 40% |

## Transducer characteristics
| Transducer | Frequency (MHz) | Focal distance (mm) | Maximal depth (mm) |
| :--- | :--- | :--- | :--- |
| A | 3.5 | 50-150 | 200 |
| B | 5 | 30-105 | 150 |
| C | 5 | 10-75 | 100 |

## *PBL-mec* : Mechanics

To address several medical use cases, 3 transducers with different frequencies (respectively 3.5, 5 and 7.5 mHz) are expected to be incorporated in the probe. Image acquisition will be performed with one transducer at a time.

A number of the echOpen probe's functionalities must be implemented by mechanical devices.

### *PBL-mec_scn* : scanning mechanism

Design a mechanical device to scan a 60 ° sector with an ultrasonic beam 15 times per second.

#### *PBL-mec_scn_mov* : Choose between oscillating and continuous rotary motion

Choose the type of movement of the ultra-sound beam and design the mechanism by which it can be obtained (continuous rotating, oscillating, acoustic mirrors, etc.)

##### *PBL-mec_scn_mov_mot* : Motorization

Choose or design a type of motorization to obtain the chosen movement.

###### *PBL-mec_scn_mov_mot_drv* : Motor control electronics

Design or choose a electronic driver for the selected motor.

###### *PBL-mec_scn_mov_mot_enc* : Position sensors

Design a means of knowing the position of the transducer during its movement.

##### *PBL-mec_scn_mov_cnx* : Transducer / electronic card connection

Design an electrical connection for carrying the signal between the mobile transducer(s) and the fixed electronic processing PCB.

##### *PBL-mec_scn_mov_brk* : Transducer support

Design a bracket suitable for receiving the transducer capsule without interfering with ultrasonic emission or impeding maintenance.

#### *PBL-mec_scn_tri* : Choose between interchangeable and tri-frequency mono frequency

Design the device to move three different resonant transducers at frequencies of 3.5, 5 and 7 MHz.

### *PBL-mec_us* : Acoustic continuity

Ensure the continuity of acoustic impedance between the transducer surface and the body of the patient.

#### *PBL-mec_us_oil* : Oil

Design a system to immerse the sensor in an acoustically compatible liquid bath.

##### *PBL-mec_us_oil_sel* : Select a compatible oil

Select a liquid (a priori an oil) that meets the following criteria:
* Low-cost
* Organic Compatibility
* Acoustic compatibility
* Electrical compatibility
* Material compatibility
* Good durability

##### *PBL-mec_us_oil_seal* : Sealing

Design all systems that seal the oil-containing enclosure:
* Choice of what is immersed in oil: piezo / mechanism / motor / position sensors / PCB / battery.
* Type of seals: static on housing, static on cables, dynamics on shaft, flexible.
* Seal material maintenanceability: removable or glued.

##### *PBL-mec_us_oil_fil* : Filling

Design the procedure for filling the cavity containing the oil:
* Filling hole
* Air bubble removal system
* Pre-maintenance dumping (protection of dry areas)

#### *PBL-mec_us_case* : Case

The part of the case that will be traversed by the ultrasounds must have a shape and be in a material compatible with this function.

##### *PBL-mec_us_case_mat* : Material

Select a material that is as transparent as possible to ultrasound, while remaining low-cost and easy to use. Several parts of different materials may be considered.

##### *PBL-mec_us_case_shp* : Shape

The portion of the housing which will be in contact with the skin of the patient will have to have a minimum radius of curvature in order, for example, to allow examination between two ribs.

#### *PBL-mec_us_gel* : Gel

Design or select a recipe for the gel used to ensure good continuity between the case and the patient's skin. This recipe should be low-cost and easily achievable.

### *PBL-mec_nrg* : Energy

Design a power system that meets the needs of the echOpen probe in terms of autonomy, safety, space, ease of use and cost.

#### *PBL-mec_nrg_bat* : Battery type

Select the good battery type

#### *PBL-mec_nrg_load* : Loading

Design the recharging system, either wired through a sealed plug or by induction.

#### *PBL-mec_nrg_therm* : Thermal Management

The response of the system to the various thermal stresses will be studied:
* Internal heating (motor, electronics, battery) during operation or charging.
* Operating temperature range.
* Storage temperature range

### *PBL-mec_case* : Casing, ergonomics

Design a housing that meets the needs of the echOpen probe

#### *PBL-mec_case_ergo* : Ergonomics, grip

An ergonomic study will be conducted by a designer with the help of practitioners to deduce the ideal format of the probe. Moreover the case must be of an easy cleaning.

#### *PBL-mec_case_mat* : Material

Select the material(s) used to make the case according to the following criteria:
* Ultrasonic Transparency
* Ease of implementation
* Strength
* Bio-compatibility

#### *PBL-mec_case_dock* : Loading Dock

Given the choice of interface of the box with the outside, especially for the loading (wired or induction). The design of a loading dock in which the box will fit will be required.
 (See: Reloading *PBL-mec_nrg_load*)
 
#### *PBL-mec_case_body* : Case

Design a case of volume and shape capable of housing the electronic mechanical parts as well as the batteries and the whole wiring.

##### *PBL-mec_case_body_asm* : Assembly Method

Choosing a method for assembling the various parts and shells which allows easy assembly / dismantling with conventional means while meeting the safety standards for a medical device.
