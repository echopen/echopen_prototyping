# Download repo github : prj\_medtec-kit

@todo - AJOUTER UN SCHÉMA D’ATTRIBUTION DES PISTES

## **Mother board**

Ref : RS 528-0661 
@todo where does this ref come from?

The original stripboard presents 39 vertical tracks

![](images/1_Mother_board/IMG_20170315_102911.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

We need 19 tracks cut on the track of the middle of the board so that 19 tracks can be preserved, composing the base of the motherboard. One can use a dremel and then smooth the cut. 

![](images/1_Mother_board/IMG_20170315_103225.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

![](images/1_Mother_board/IMG_20170315_103230.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

![](images/1_Mother_board/IMG_20170315_103333.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

### *Sockets *

We use 0.1" sockets to connect the daughter boards to the motherboard

![](images/1_Mother_board/IMG_20170315_104039.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

### Preparation

For this, we'll be needing 9 sockets of size 1x19

* first socket on one border (1) for power supply
* second socket on (6)

![](images/1_Mother_board/IMG_20170315_104927.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

## **Power supply**

### BOM 

[To download the BOM, refer here](https://github.com/echopen/PRJ-medtec_kit/blob/master/electronic/daughter_boards/DB-supply/DB-supply_v1/src/DB-supply_v1.csv).

* PCB : DB\_Supply\_v1 (custom echOpen)
@todo: what does it mean?

Locations of each component are indicated on the PCB.

![](images/2_power_supply/IMG_0661.JPG){width="5.763888888888889in"
height="4.322916666666667in"}

#### Capacitors 

they are polarized white side corresponds to lowest
potential and must be plugged on white part of the mark on the PCB

![](images/2_power_supply/IMG_0663.JPG){width="5.763888888888889in"
height="7.685416666666667in"}

#### Integrated circuits 

The dot on the component must be plugged where there is a « line break » (see below for direction)

![](images/2_power_supply/IMG_0665.JPG){width="5.763888888888889in"
height="7.685416666666667in"}

#### Voltage regulator 
They must be plugged according to the mark on the PCB,
i.e. additionnal rectangle corresponds to the part of the voltage
regulator that has sort of a « growth »

![](images/2_power_supply/IMG_0666.JPG){width="5.763888888888889in"
height="7.685416666666667in"}

#### LED

See scheme below to identify the cathode

![](images/2_power_supply/LED.png){width="5.763888888888889in"
height="4.240972222222222in"}

On the PCB, there is an additionnal line where the cathode must be
plugged

#### Transistor 

Match the small strip with the footprint 

![](images/2_power_supply/){width="5.763888888888889in"
height="7.685416666666667in"}

#### Diods

![](images/2_power_supply/){width="5.75in"
height="7.708333333333333in"}

Beware in terms of direction. A line marks the correct side, which is also marked on the PCB footprint. 

*REsistors : Tableau code couleur ?*

En cas d’erreur, utiliser la tresse à dessouder pour enlever l’étain.
Pour cela poser la tresse sur la soudure puis venir appliquer le fer à
souder par dessus. Forcer un peu sur les pattes pour décrocher le
composant retenu par l’étain résiduel.

![](images/2_power_supply/){width="5.75in" height="7.708333333333333in"}

Tous les composants sont désormais en place !

### Testing the board

La carte que l’on vient de construire est une carte d’alimentation qui
fournie plusieurs tensions continues stabilisées. Il convient de la
tester en l’alimentant correctement et en vérifiant que les tensions en
sortie soient les bonnes. Pour ce qui est de l’alimentation on utilisera
de préférence une alimentation de laboratoire qui présente l’avantage
d’intégrer une protection contre un éventuel court circuit.
![](images/2_power_supply/){width="5.75in" height="7.708333333333333in"}On
choisit le mode générateur de tension idéal (C.V) et une tension de 18V
(qui correspond aux deux piles de 9V qui alimenteront le circuit) et on
limite le courant à 800mA. ![](images/2_power_supply/){width="5.75in"
height="7.708333333333333in"}

This power supply can be plugged to pins 1 and 12 (respectively GND and 18V) 

![](images/2_power_supply/){width="5.763888888888889in"
height="7.680555555555555in"}

When powering on the supply, the power supply should indicate a current use of 45mA. 


![](images/2_power_supply/){width="5.763888888888889in"
height="4.305555555555555in"}Ensuite on mesure les tensions entre la
terre (pin 1 i.e. GND) et les des pins 2, 6, 8, 18 et 19. Pour cela un
voltmètre suffit (un oscilloscope peut aussi être utilisé). On doit
mesurer respectivement 5, 12, -12, -5 et 3,3V. Si l’on n’obtient pas ces
résultats, il convient de vérifier que chaque composant est à sa place
et que les soudures ont bien été réalisées.

![](images/2_power_supply/){width="5.75in"
height="7.708333333333333in"}![](images/2_power_supply/){width="5.75in"
height="7.708333333333333in"}

Once the board validated, one can trim the remaining legs. 

## **High voltage**

BOM :
<https://github.com/echopen/PRJ-medtec_kit/blob/master/electronic/daughter_boards/DB-high_voltage/DB-high_voltage_v1/src/DB-high_voltage_v1.csv>

PCB : DB-high\_voltage (custom echopen)

SMA connector : les trois pattes doivent être superposées avec les trois
marques de la carte PCB (à l’avant) et les deux pattes se retrouvent à
l’arrière

![](pictures/3_High_voltage/IMG_20170315_153217.jpg){width="5.763888888888889in"
height="7.680555555555555in"}

Attention : vérifier que le condensateur en C14 supporte bien 100V

Carte terminée :

![](pictures/3_High_voltage/IMG_20170315_160124.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

*Tests*

Attention il faut un oscillo qui supporte 100V, ou bien utiliser une
sonde d’oscilloscope qui divise la tension par 10

La masse se trouve en haut

![](pictures/3_High_voltage/IMG_20170315_161755.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

We should get -90V on the output.

## **Pulser**

This daughter uses an external pulser : the MAX4940 evaluation kit, that
is connected to the daughter via the P3 connector.

![](pictures/4_Pulser/IMG_20170315_164106.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

Intégrer chéma du MAX4940 :

<https://github.com/echopen/PRJ-medtec_kit/tree/master/electronic/modules/hardware/MDL-pulser/MDL-pulser_v2>

ATTENTION : ERREUR SUR LE SCHÉMA, VEE DOIT ÊTRE RELIÉ AU -12V DE LA
DAUGHTER, ET VCC AU +12V A CHANGER SUR LE SCHEMA

Connect the GND to pins 2 and 3 and VPP1 :

![](pictures/4_Pulser/IMG_20170315_162614.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

Plug components on the pulser daughter board. See BOM :
<https://github.com/echopen/PRJ-medtec_kit/blob/master/electronic/daughter_boards/DB-pulser/DB-pulser_v2/src/DB-pulser_v2.csv>

Connect the MAX4940 to the daughter board as shown below :

![](pictures/4_Pulser/IMG_20170315_162614.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

![](pictures/4_Pulser/IMG_20170316_120338.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

The high voltage is connected as follows : blue wire corresponds to the
(+), white corresponds to the ground.

*Tests*

Pour tester le pulser, connecter l’output de la carte (P6) à
l’oscilloscope.

![](pictures/4_Pulser/IMG_20170316_114545.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

Il faut injecter un signal logique +0-5V et de durée 140ns. Pour cela,
connecter le motor control avec le code de test à la carte mère.

![](pictures/4_Pulser/IMG_20170328_183729.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

Le signal en sortie du pulser doit avoir la même durée que le signal
logique d’entrée et une amplitude de -90V :

![](pictures/4_Pulser/TEK0026.JPG){width="5.763888888888889in"
height="3.4583333333333335in"}

## **TGC + T/R switch**

BOM :
<https://github.com/echopen/PRJ-medtec_kit/blob/master/electronic/daughter_boards/DB-tr_switch_tgc/DB-tr_switch_tgc_v1/src/DB-tr_switch_tgc_v1.csv>

Pour souder les CMS (composants montés en surface) : mettre au préalable
un point de soudure.

![](pictures/5_TR_switch/IMG_20170316_144737.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

Ensuite utiliser une pince brucelles pour maintenir le circuit et le
souder.

![](pictures/5_TR_switch/IMG_20170316_122800.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

Ampli OP : le trait à gauche des chiffres doit être placé en face du
point

![](pictures/5_TR_switch/IMG_20170316_144737.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

![](pictures/5_TR_switch/IMG_20170316_122624.jpg){width="5.763888888888889in"
height="7.685416666666667in"}

### *Tests T/R switch*

* Brancher toutes les cartes-filles sur la carte-mère
* brancher la sortie SMA du pulser sur l’input SMA du T/R switch
* Relier la piste 9 de la carte mère à la voie 1 de l’oscillo
* Relier le test point W1 du T/R switch à la voie 2 de l’oscillo

![](pictures/5_TR_switch/IMG_20170328_184945.jpg){width="5.763888888888889in"
 height="7.685416666666667in"}

 On doit visualiser le résultat suivant :

 ![](pictures/5_TR_switch/TEK0028.JPG){width="5.763888888888889in"
 height="3.4583333333333335in"}

* Visualiser la commande du pulser (voie 1) et le test point W1 du T/R
    switch (voie 2)

Exemple de signal si le T/R switch a grillé : le pulse d’excitation du
transducteur est à -20V au lieu de -100V

![](pictures/5_TR_switch/TGC/TEK0029.JPG){width="5.763888888888889in"
height="3.4583333333333335in"}

Ce qu’il faut visualiser :

![](pictures/5_TR_switch/TGC/TEK0029.JPG){width="5.763888888888889in"
height="3.4583333333333335in"}

@todo this picture above is not the good one, we don't have it

* Brancher un transducteur sur la seconde sortie SMA du pulser et le plonger dans un aquarium
* Visualiser les bornes du transducteur (P4 ou P7 du pulser) sur la voie 1
* Visualiser le test point W1 du T/R switch sur la voie 2

On doit visualiser un écho sur les deux voies :

![](pictures/5_TR_switch/TGC/TEK0032.JPG){width="5.763888888888889in"
height="3.4583333333333335in"}

### Connecting the TGC

* Solder two wires, one on  +5V and the other on GND (for the power supply)
* Souder deux pins de header sur GAIN et GND pour pouvoir plugger des
    fils dessus (ou au choix : souder les fils directement) (sera
    branché à la red pitaya pour le contrôle du gain)

    ![](pictures/5_TR_switch/TGC/IMG_20170328_191304.jpg){width="5.763888888888889in"
    height="4.322916666666667in"}

* Brancher TGC IN du T/R switch sur INH du TGC
* Brancher TGC OUT du T/R switch sur VOUT du TGC
* Connect 5V and GND of the TGC on the tracks 2 and 1 of the motherboard

### Tests

* Visualiser le test point W1 du T/R switch sur la voie 1

* Visualiser le TGC out de la carte mère (piste 3) sur la voie 2

    On doit visualiser un echo amplifié (2V environ) sur la voie 2 :

    ![](pictures/5_TR_switch/TGC/TEK0033.JPG){width="5.763888888888889in"
    height="3.4583333333333335in"}

## **RedPitaya**

### Connectiques (to do three times)

> - Couper un SMA-mâle SMA-mâle en deux
>
> - Dénuder le bout du câble
>
> ![](pictures/5_TR_switch/TGC/IMG_20170328_192324.jpg){width="5.763888888888889in"
> height="7.685416666666667in"}
>
> - Détresser les petits brins avec un petit tournevis plat
>
> - Rouler les brins entre ses doigts pour les mettre ensemble en étant
> désolidarisés de l’âme
>
> ![](pictures/5_TR_switch/TGC/IMG_20170328_192401.jpg){width="5.763888888888889in"
> height="7.685416666666667in"}

* Dénuder l’âme

    ![](pictures/5_TR_switch/TGC/IMG_20170328_192452.jpg){width="5.763888888888889in"
    height="7.685416666666667in"}


> - Souder les brins à un fil (ce sera la masse)
>
> - Souder l’âme à un autre fil (ce sera la signal)
>


> ![](pictures/5_TR_switch/TGC/IMG_20170328_192539.jpg){width="5.763888888888889in"
> height="7.685416666666667in"}

* Relier le IN1 de la RedPitaya aux pistes 3 et GND de la carte mère

* Relier le IN2 de la RedPitaya aux pistes 4 et GND de la carte mère

* Relier le OUT1 de la RedPitaya aux IN et GND du TGC

    **Configuration including all modules : **

![](pictures/configuration/IMG_20170331_174120.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

![](pictures/configuration/IMG_20170331_174204.jpg){width="5.763888888888889in"
height="4.322916666666667in"}

## **RedPitaya and Arduino codes installation**

* Format the RedPitaya SD card in FAT-32
* Refer to the instructions available on our GitHub repo to install
    codes :     <https://github.com/echopen/PRJ-medtec_kit/tree/master/installation/>

## Mechanics**
