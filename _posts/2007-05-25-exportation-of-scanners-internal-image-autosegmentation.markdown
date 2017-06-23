---

title: Exportation of scanner's internal image auto-segmentation
abstract: A method and system are disclosed for exporting metadata from an image capture device, for example a scanner, preferably using a standard application programming interface. The metadata may be associated with a pixel, a page, or a region/object of the image, and could be used by an application, for example, to improve the quality of the image when printed or to facilitate the conversion from a single layer of image information to multi-mask mixed raster content (MRC).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08390877&OS=08390877&RS=08390877
owner: Xerox Corporation
number: 08390877
owner_city: Norwalk
owner_country: US
publication_date: 20070525
---
In the operation of a copier or printer particularly color machines it is highly desirable to have means for variably processing and enhancing text graphical and pictorial image quality. A typical workflow in a production publishing environment involves the following steps scanning the hardcopy originals outputting the scanned image data and printing the image data through a DFE Digital Front End to a printer. The quality of the printed images is limited to the standard processing features and capabilities of the DFE. Particularly in the case of single or multi pass color printers it is highly desirable that an image processing system be employed to reduce imaging problems caused by rendering systems which may not be well suited to each type of image.

Auto segmentation techniques are known which can select the most appropriate method to render the various object types e.g. black and white or color images text etc. present in an image. Such techniques permit an image to be divided into segments which correspond to structural aspects of the image and may be used to distinguish various objects of interest within the entire image on a page and allow different printing properties or methods to be applied to the different document image segments by the DFE.

Specified regions of an image page are separated into classes such as the typical text graphics and pictures. Scanned or computer generated electronic document images may be rendered according to various colorization contrast and or halftoning techniques for example. Some rendering techniques are more suitable for printing text regions while others are more suitable for printing graphics or picture bitmap regions. The quality of the printed image can be efficiently improved by first separating all the regions in a document image that need to be evaluated for differential rendering and then classifying these regions according to the desired rendering techniques. Automatic processing of document images is performed by classifying various regions in a document image into logically separate classes. These classes may be text graphics and pictures. The image segmentation stage separates an input image into regions or objects. Output of the segmentation stage contains region labels at each pixel in the input image.

Currently auto segmentation software applications for example ELAN ELP from ELAN GMK are only capable of adding index information or metadata after the image data has been exported from a scanner and saved to file.

The inventors have recognized that if the DFE processing step had more information about each pixel in the image then more intelligent processing could be applied to improve the overall quality of the output image. The Xerox FreeFlow Scanner 665 scanner for example produces per pixel information for its own internal use when processing images inside the scanner s hardware firmware image processing path e.g. in Automatic Mode . However this information is presently not exported from the scanner.

Thus the inventors have recognized that it would be desirable to export metadata associated with the image data from the image capture device to enable more intelligent post scan processing of the images.

In a first embodiment a method for exporting image metadata from an image capture device is provided comprising generating electronic image data comprising a plurality of pixels representative of an image using the image capture device generating metadata associated with the image data the metadata representing a characteristic of an associated division of the image and exporting the image data and the metadata from the image capture device.

The metadata may preferable comprise pixel by pixel metadata page by page metadata or object by object metadata or a combination thereof. Similarly the division of the image may comprise a pixel a page a region an object or a combination thereof.

The metadata may be embedded or linked with the image data for example in an image file capable of accepting metadata.

The image capture device may be selected from the group consisting of scanner a digital copier a facsimile machine a multi function device a digital still camera and a digital video camera.

The image data including the metadata associated with the image data may be exported from the image capture device through an interface for example an application programming interface preferably selected from the group consisting of TWAIN SANE ISIS and WIA.

The metadata may be generated from a segmentor and or an auto segmenting windowing technique preferably a two pass auto segmenting windowing technique.

In a second embodiment a system for exporting image metadata from an image capture device is provided comprising an image capture device for generating electronic image data comprising a plurality of pixels representative of an image a processor configured to generate metadata associated with the image data the metadata representing a characteristic of an associated division of the image and an interface coupled to the processor for exporting the data image and the metadata from the image capture device.

Other objects features and advantages of one or more embodiments of the present invention will seem apparent from the following detailed description and accompanying drawings and the appended claims.

An embodiment of the invention proposes to export metadata TAG data from an image capture device. In a preferred embodiment the metadata is pixel by pixel tags. However it is understood that the TAG data may also be object by object metadata or page by page metadata or a combination thereof. The TAG data could be used by an application for example to improve the quality of the image when printed or to facilitate the conversion from a single layer of image information to multi mask mixed raster content MRC .

The disclosed embodiment is part software and part in the imaging device s hardware and software. It uses mechanisms allowed via a standard application programming interface API to enable setup of the imaging device s hardware firmware for exportation of image segmentation TAG data which are normally not exported from the scanner.

The electronic image capture device includes a control panel a document platen on which an original document can be placed to generate corresponding electronic image data and a document handler . In particular the document handler includes a feed tray on which the original document can be placed and a document feeder which moves each document in turn from the feed tray and feeds the removed document to the document platen . Each document is then returned to an output tray after electronic image data is generated from that original document. This is just one example of a construction for the device and is not intended to be limiting.

Typical scanning produces image data file for example using the TIFF file format for productivity reasons. The TAG data may be embedded and or linked to the image data in the image file similar to how the International Color Consortium ICC profile mechanism is used for color management of scanned images.

By providing TAG data in addition to the image data the image quality may be advantageously improved. For example the TAG data may enable more than just color fidelity and may impact many other image quality metrics such as text and line quality moire background content etc. Further the TAG data allows extraction of hardware generated image segmentation data normally not available to the DFE for future post scan use.

TAG data is preferably generated inside the image capture device. For example the Xerox FreeFlow Scanner 665 scanner produces TAG data for its own internal use when processing images inside the scanner s hardware firmware image processing path e.g. in Automatic Mode . Various aspects of the Xerox FreeFlow Scanner 665 scanner are disclosed for example in U.S. Pat. Nos. 6 496 277 and 5 765 029 herein incorporated by reference. It is understood however that other image capture devices could be modified to perform a similar function.

In one embodiment an imaging device is connected to a digital front end DFE of a color printer. The DFE is a device used to manage print devices especially in high volume environments e.g. color laser printers production printers and digital presses. The DFE increases productivity by efficiently automating digital workflow. Typically the DFE is an external device such as a computer or server that interfaces to a network and typically will accept image data and process the image data for a copier or printer devices. However the DFE could be a part of the printing device itself. For example the Xerox iGen3 digital printing press incorporates a DFE. By having knowledge of each pixel individually the DFE can process each pixel of the image data more intelligently.

In a preferred embodiment the TWAIN TWAIN standard application programming interface is utilized to export TAG data from the image capture device. TWAIN is an open public scanning interface for Microsoft Windows and Apple Macintosh operating systems developed by a coalition of imaging hardware and software manufacturers. TWAIN is defined by the TWAIN Specification the latest version 1.9 was ratified by the TWAIN Working Group Committee as of Jan. 20 2001 and is available at http www.twain.org docs TWAIN2d.pdf herein incorporated by reference. Since the TWAIN architecture is known it will only be briefly discussed herein. The three key elements in TWAIN are the application software the data source manager software and the data source software. The application software are applications which are specifically modified for using TWAIN. The Data Source Manager software manages the interactions between the application and the Source. This code is provided in the TWAIN Developer s Toolkit and is shipped with each TWAIN application and Source. The Source software controls the image acquisition device and is written by the device developer to comply with TWAIN specifications.

It is also understood that other proprietary application programming interfaces could similarly be used for example Scanner Access Now Easy SANE for UNIX including GNU Linux Image and Scanner Interface Specification ISIS from EMC Captive formerly Pixel Translations and Windows Image Acquisition WIA from Microsoft.

The protocol layer includes a TWAIN code portion of the TWAIN driver or data source a source manager and a TWAIN code portion of a TWAIN compliant application . The application layer includes the application portion of the application .

As shown in control and data signals are provided from the electronic image data capture device to the TWAIN driver or data source through the device interface portion of the TWAIN data source . Similarly control and data signals are provided between the TWAIN data source and the source manager through the TWAIN code portion of the TWAIN data source . The control and or data signals are also provided between the source manager and the application through the TWAIN code portion . In various exemplary embodiments the TWAIN data source controls the electronic image data capture device . In various ones of these exemplary embodiments the TWAIN data source is developed by the manufacturer of the electronic image data capture device .

The source manager manages and facilitates the interactions between the application and the TWAIN data source . In various exemplary embodiments one or more of two distinct source managers have been implemented. Both are compiled as dynamic loading library modules. In general dynamic load library modules are provided as part of the TWAIN developers tool kit and are shipped with each TWAIN compliant application and at each TWAIN compliant electronic image data generating device. Further reference is made to U.S. Pat. No. 6 850 259 regarding the TWAIN interface for an image capture device herein incorporated by reference.

A calling application instructs the TWAIN Data Source of the image capture device to enable TAG data. The TWAIN Data Source instructs the image capture device to enable external access to TAG data. For example the ICAP EXTIMAGEINFO capability of TWAIN may be used to return the tag raster image to the application. An exemplary TWAIN call is as follows 

The tag raster image will be stored in a TW EXTIMAGE structure. The NumInfos member is set to 1 and TWAIN will allocate memory for the tag image copy the tag image into that memory and store the memory handle in the Info member.

TWAIN allows the use of custom capabilities for controlling an image acquisition device. Using the custom TWAIN capability enables and manages exportation of TAGS from the scanner. Since preferably images are scanned to TIFF files for productivity reasons the TAG data may be embedded and or linked to the image data similar to the ICC profile mechanism used for color management of scanned images.

There are two modes that TWAIN transfers images to the application File and Memory. In file transfer mode TWAIN creates a file for each image. Preferably TIFF files are used because TIFF files allow information to be embedded and or linked to the image data. However other image file types capable of accepting metadata may also be used. In memory transfer mode TWAIN allocates memory for the image and copies the image data into the memory. A handle or link to the memory is passed to the application.

The TAG data for each raster image would be stored in a separate raster image that consists of tag values instead of pixel values. Each pixel in the tag image describes a characteristic of the corresponding pixel in the actual image. The number of bits per pixel needed for each TAG depends on the amount of information encoded in each tag. Each pixel s tag information may be stored in memory for example in eight bits one byte . Some of the TAG data classifications may include but are not necessarily limited to Neutral pixel Text Line Art Low Frequency Halftone High Frequency Halftone Background pixel and Window ID. This TAG image for example may have the same size and structure as a 8 bit per pixel grayscale image. The bits of each byte may be used like this 

The same tag image may be transferred in either file or memory transfer mode. In file transfer mode preferably using a TIFF file the tag image may be included in the TIFF file as a sub image. A TIFF sub image is an alternate representation of the primary image. Alternately TWAIN may create a separate tag image file. The separate file could also be linked to the primary image file by file name that is stored in the primary TIFF file in a private tag.

Next the TWAIN Data Source embeds and or links the TAG data to image data. The TWAIN Data Source hands off the image data and the associated TAG data to the DFE .

The DFE may processes the TAG data file for printing. In an exemplary embodiment if the DFE knows that a part of the image is neutral text i.e. black text from the TAG data it could render that part of the image using Thresholding and black toner rather then using halftone screening and color toner as are conventionally performed.

In other embodiments not shown the TAG data may be passed through the DFE directly to the print engine or it may be sent to the print engine directly if no DFE is involved as in a networked office device . All of this depends on the architecture of the printer and or DFE.

The TWAIN Data Source instructs image capture device to scan the document and return the electronic representation of the image to the DFE . In addition the TWAIN Data Source instructs image capture device to return the TAG data to the DFE . Lastly the printer prints the image.

Each video pixel s class is a function of several local features. TAG data may be originally generated by the segmentor . The segmentor looks at several scanlines of data and determines the content of a specific pixel based on surrounding pixels. This is significant because it means that pixels are classified on an individual basis. Thus segmentation will not create rectangular artifacts which are common in algorithms where pixels are classified on a block basis.

A problem however is that some pixels may be misclassified. For example some pixels within an image may be misclassified as text. To correct this situation a segmentation tag cleanup process may be advantageously employed. See also U.S. Pat. No. 6 240 205 herein incorporated by reference. The clean up identifies windows within the image and reclassifies all pixels within that region to the predominate tags microclassifiers .

This two pass auto segmentation detects irregularly shaped windows of any size so that every pixel in the detected window can be uniformly classified based on the predominate segmentation tags in that window and rendered appropriately. This is useful because not every pixel in a halftone for example will be classified identically by the segmentor . The resulting halftone will look much better if every pixel in it is rendered the same.

During the first pass the Window Detection Module analyses the video and tag stream generated by the segmentor and detects Raw Windows as minimum low level window requirements are met. Most of these Raw Windows are discarded leaving only high probability Candidate Windows. Tag statistics are collected for pixels within those Candidate Windows.

The video and tags flow into a full page buffer during the first pass enabling start of the second pass to be delayed until the first pass has completed and the Window Analysis Module has completed development of the Final Windows.

After the first pass has completed but before the second pass can begin the Window Analysis software analyzes the Window Candidate data to develop the Final Windows. The statistics for these windows are then analyzed to determine the appropriate final classification for each window.

During the second pass the Re Tagging module is driven on a pixel by pixel basis by the same Raw Window IDs that were generated within the first pass Window Detection module.

The Inter Pass process develops a Final Window ID Equivalence Table which the Re Tag module uses to tag each pixel according to three possible cases 

1. Re Tag with the Final Window ID if the pixel s containing Candidate Window is part of a Final Window 

2. Leave the pixel s first pass pixel level classification tag if it was not part of a Final Window even though it may have been part of a Raw or Candidate Window or

3. Leave the pixel s first pass pixel level classification tag if the pixel is not part of any window.

This Re Tagging takes place as the video is streamed out of the page buffer through Re Tagging and downstream through the second pass image processing and rendering pipelines.

Some of the possible pixel classifications for TAG data might include 1. Neutral pixel 2 Text and Line Art 3 Low Frequency Halftone 4 High Frequency Halftone 5 Background pixel and 6 Window ID.

During image processing external to the image capture device the TAG data may be utilized to adjust an image processing operation for example by the DFE in the following manner 

2 for Text and Line Art improving text and line quality by rendering the image via Thresholding instead of conventional half toning 

5 for Background pixel eliminating background i.e. due to colored paper originals effect in prints and

In other embodiments the TAG data may also be or may further be augmented by object by object and or page by page metadata. For example the TAG data may be used to facilitate the conversion from a single layer of image information to multi mask mixed raster content MRC . In a MRC type export a mask is used to determine one region or object or window type from another photo text and halftone . This mask could be on a pixel by pixel basis or use region or object window coordinates. Only one tag or Hint is then needed to describe each individual region or object window type within the mask window is text window is photo etc. .

The following advantages have been recognized over the conventional production printing and publishing. For example exporting TAG data from the imaging device allows preservation of device independence for scanned images while enabling the ability to improve the image quality for any intended device. Further it allows extraction of hardware generated image segmentation data normally not available external to the scanner for future post scan use.

While the specific embodiments of the present invention have been described above it will be appreciated that the invention may be practiced otherwise than described. The description is not intended to limit the invention.

