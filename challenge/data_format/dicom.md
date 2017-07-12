# DICOM

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



