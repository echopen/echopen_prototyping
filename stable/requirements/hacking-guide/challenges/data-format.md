# data format

Current raw data format has been defined at [Commons rules for raw data structure](http://wiki.echopen.org/index.php/Challenge:_Data_format#Solution:_Common_rules_for_structuring_raw_data)

### Challenge

#### Brief

Hi there community!

Here's an interesting challenge for you guys : wouldn't it be interesting to have an '''open file format''' for all files being created with the echOpen kits - those being images, on the one hand, and raw signals on the other hand?

The project already acquires some data on which one can work - being images or data - it would then be awesome to capitalize on this and allow those who want to do some signal processing to work on a couple of files that can be given to data processing specialists.

The objective is to set a format that

* allows consistency in time, 
* captures all relevant information about the data since the very first images, 
* allows the use of consistent tools to work on these data
* allows a proper tagging for images.

### Solution: Common rules for structuring raw data

* First part is classical CSV **note that the first item contains the position of the line, in arbitrary unit**
* Second part is comments \(starting with \#\).

In comments can be found meta data, storing for example the following items

* `#timestamp:XX` for the timestamp when the image was taken
* `#lines:XX` contains the number of lines in the image
* `#length:XX` contains the number of pixels per line
* `#frequency:XX` is the frequency of acquisition
* `#piezofrequency:XX` is the piezo frequency
* `#angle:XX` is the angle of the acquisition
* `#anglestep:XX` is the multiplicator between the first item of each line to obtain the position in degree.

Some images in this format can be found [here](https://github.com/kelu124/murgen-dev-kit/tree/master/software/examples_csv) with preview of the raw data in PNG.

#### Need to make it compatible with DICOM

##### Commentaires

Au niveau des formats de fichiers, la situation en imagerie médicale numérique est extrêmement simple : tout doit être encodé au format DICOM :\) Cela permet une prise en charge unifiée et pérenne par tous les PACS \(des mini-PACS Orthanc/dcm4chee, aux PACS "enterprise" du type Agfa/Télémis/...\), ainsi que par tous les logiciels destinés à l'imagerie \(du style Ginkgo CADx/medInria/OsiriX/Syngo.via/...\). Le format DICOM assurera une durabilité de facto de l'information d'echOpen : l'existence de logiciels libres comme Orthanc permettra de faire des passerelles en écosystèmes propriétaires.

Le revers de la médaille est évidemment sa complexité et une grosse courbe d'apprentissage. Il n'en demeure pas moins que c'est le seul et unique standard de l'imagerie au sein des hôpitaux : echOpen devra de facto y passer pour être utile dans le cadre de la routine clinique. Il existe un document introductif au DICOM à l'adresse suivante, il pourrait vous être utile :

* [https://orthanc.chu.ulg.ac.be/book/dicom-guide.html](https://orthanc.chu.ulg.ac.be/book/dicom-guide.html)

Dans le cas des images d'échographie \(ultrasons\), voici un pointeur vers la partie de la spécification DICOM qu'il s'agirait d'implémenter :

* S'il s'agit d'images fixes \(screenshots\) : [http://dicom.nema.org/medical/dicom/current/output/html/part03.html\#sect\_A.6](http://dicom.nema.org/medical/dicom/current/output/html/part03.html#sect_A.6)
* S'il s'agit de vidéos US \(cine\) : [http://dicom.nema.org/medical/dicom/current/output/html/part03.html\#sect\_A.7](http://dicom.nema.org/medical/dicom/current/output/html/part03.html#sect_A.7)

La spécification liste un ensemble de modules \(càd. un ensemble de tags DICOM\) qui sont soit obligatoires \("M"\), soit optionnels \("U"\), soit conditionnels \("C"\). Un module donne une liste hiérarchique de tags \(le préfixe "&gt;" indique un nœud-enfant de cette hiérarchie de tags\), dont chaque tag peut être obligatoire et non vide \(type 1\), obligatoire et possiblement vides \(type 2\), et optionnels \(type 3\). La présence de chacun de ces tags peut éventuellement être liée à une condition \(type 1C et 2C\).

L' objectif serait de créer un "DICOM-izer" qui prendrait en input une image d'echOpen et générerait en output un ensemble de fichiers DICOM. Évidemment, dans un premier temps, il s'agit de faire le minimum, càd. d'ajouter les champs 1/1C/2/2C des modules M/C. L'outil "dciodvfy"  permet de vérifier automatiquement si un fichier DICOM comporte tous les tags DICOM requis \(c'est le must pour créer un DICOM-izer\) :  
[http://www.dclunie.com/dicom3tools/dciodvfy.html](http://www.dclunie.com/dicom3tools/dciodvfy.html)

L'API REST d'Orthanc permet de créer des fichiers DICOM directement à partir de fichiers JSON. Il y a quelques exemples dans les tests d'intégration d'Orthanc \(c'est l'URI "/tools/create-dicom"\) :  
[https://bitbucket.org/sjodogne/orthanc-tests/src/962274ebd797a2b6aca2b44d06596ff52be50c52/Tests/Tests.py?at\#\#default&fileviewer\#\#file-view-default\#Tests.py-1279](https://bitbucket.org/sjodogne/orthanc-tests/src/962274ebd797a2b6aca2b44d06596ff52be50c52/Tests/Tests.py?at##default&fileviewer##file-view-default#Tests.py-1279)

##### TODO

Un hackaton pour une app qui exporte le format echopen en DICOM ?

#### Comments from SebJ

### Wikipedia definitions of an open file format

An open file format is a published specification for storing digital data, usually maintained by a standards organization, and which can be used and implemented by anyone. For example, an open format can be implemented by both proprietary and free and open source software, using the typical software licenses used by each. In contrast to open formats, closed formats are considered trade secrets. Open formats are also called free file formats if they are not encumbered by any copyrights, patents, trademarks or other restrictions \(for example, if they are in the public domain\) so that anyone may use them at no monetary cost for any desired purpose

### DICOM

#### Introduction

The Digital Imaging and Communications in Medicine \(DICOM\) standard was created by the National Electrical Manufacturers Association \(NEMA\) to aid the distribution and viewing of medical images, such as CT scans, MRIs, and ultrasound. Part 10 of the standard describes a file format for the distribution of images. This format is an extension of the older NEMA standard. Most people refer to image files which are compliant with Part 10 of the DICOM standard as DICOM format files. A complete copy of the standard \(in PDF format\) is avaiable for download \(drafts of the standard are organized by year\).

#### An example

![alt tag](http://wiki.echopen.org/images/e/e0/Header.gif)  
![alt tag](http://wiki.echopen.org/images/5/52/Dicm.gif)

The Image above  shows a hypothetical DICOM image file. In this example, the first 794 bytes are used for a DICOM format header, which describes the image dimensions and retains other text information about the scan. The size of this header varies depending on how much header information is stored. Here, the header defines an image which has the dimensions 109x91x2 voxels, with a data resolution of 1 byte per voxel \(so the total image size will be 19838\). The image data follows the header information \(the header and the image data are stored in the same file\).

Further down, I show a more detailed list of the DICOM header as displayed by my software. Note that DICOM requires a 128-byte preamble \(these 128 bytes are usually all set to zero\), followed by the letters 'D', 'I', 'C', 'M'. This is followed by the header information, which is organized in 'groups'. For example, the group 0002hex is the file meta information group, and \(in the example on the left\) contains 3 elements: one defines the group length, one stores the file version and the third stores the transfer syntax.

The DICOM elements required depends on the image type, and are listed in Part 3 of the DICOM standard. For example, this image modality is 'MR' \(see group:element 0008:0060\), so it should have elements to describe the MRI echo time. The absence of this information in this image is a violation of the DICOM standard. In practice, most DICOM format viewers \(including MRIcro and ezDICOM\) do not check for the presence of most of these elements, extracting only the header information which describes the image size.

The NEMA standard preceded DICOM, and the structure is very similar, with many of the same elements. The main difference is that the NEMA format does not have the 128-byte data offset buffer or the lead characters 'DICM'. In addition, NEMA did not explicitly define multi-frame\(3D\) images, so element 0028,0008 was not present.

Of particular importance is group:element 0002:0010. This defines the 'Transfer Syntax Unique Identification' \(see the table on the left\). This value reports the structure of the image data, revealing whether the data has been compressed. Note that many DICOM viewers can only handle uncompressed raw data. DICOM images can be compressed both by the common lossy JPEG compression scheme \(where some high frequency information is lost\) as well as a lossless JPEG scheme that is rarely seen outside of medical imaging \(this is the original and rare Huffman lossless JPEG, not the more recent and efficient JPEG-LS algorithm\). These codes are described in Part 5 of the DICOM standard. A nice introduction to this the transfer syntax is provided at www.barre.nom.fr.

Note that as well as reporting the compression technique \(if any\), the Transfer Syntax UID also reports the byte order for raw data. Different computers store integer values differently, so called 'big endian' and 'little endian' ordering. Consider a 16-bit integer with the value 257: the most significant byte stores the value 01 \(\#\#255\), while the least significant byte stores the value 02. Some computers would save this value as 01:02, while others will store it as 02:01. Therefore, for data with more than 8-bits per sample, a DICOM viewer may need to swap the byte-order of the data to match the ordering used by your computer.

#### Read more

Read more about the format there :

* [http://dicom.nema.org/dicom/2013/output/chtml/part10/chapter\_7.html](http://dicom.nema.org/dicom/2013/output/chtml/part10/chapter_7.html) 
* [http://www.mccauslandcenter.sc.edu/mricro/dicom/](http://www.mccauslandcenter.sc.edu/mricro/dicom/)



