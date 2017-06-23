---

title: Automatic target recognition system for detection and classification of objects in water
abstract: A method of detecting objects in water, comprises the steps of capturing a plurality of images of a region of interest, extracting voxel data from the images, and processing the voxel data to detect items of interest in the region of interest. An apparatus that performs the method is also included.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07916933&OS=07916933&RS=07916933
owner: Northrop Grumman Systems Corporation
number: 07916933
owner_city: Los Angeles
owner_country: US
publication_date: 20070118
---
This invention was made under Contract No. N61331 00 C 0022. The United States Government has rights in this invention under the contract.

Various systems have been proposed for locating and identifying water mines. One system for detecting mines is the Northrop Grumman Airborne Laser Mine Detection System ALMDS developed and built for the U.S. Navy. The ALMDS system is a laser detection and ranging system LADAR system that captures information in the form of a set of images. Each image represents a nearly vertical slice through a volume of water of interest.

The ALMDS system includes a pulsed fan beam laser transmitter four streak tube receivers and a data processing unit. Each receiver is composed of a streak tube imager intensifier and camera to capture the images and data processing equipment to determine if the volume of water contains a mine. Each receiver records reflected light from approximately one fourth of the transmitted fan beam. All of this hardware is contained in a pod that is typically attached to a helicopter.

This invention seeks to provide an improved data processing algorithm for detecting objects in the ladar images of a volume of water.

This invention provides a method of detecting objects of a user selected size in partially transparent material typically seawater. The method comprises the steps of capturing a plurality of images of a volume of interest extracting voxel data from the images and processing the voxel data to detect objects in the volume or floating on the surface of the material in the volume. When the material in the volume is seawater these detected objects are known to the U.S. Navy as contacts . The invention further classifies the contacts as being either mine like objects or non mine like objects.

Referring to the drawings is a schematic representation of an apparatus that can be constructed and operated in accordance with an embodiment of the invention. The apparatus includes a laser radar ladar system mounted on an aircraft . A laser in the ladar system emits signals in the form of temporal pulses in a spatial fan beam that are directed towards a region of interest . In a particular example the region of interest can include a body of water.

As used herein the raw data are the data that leave the camera electronics . The raw data represent information relating to a volume of the region of interest. Raw data are collected as follows. In the ALMDS example the lidar transmits a pulse in the shape of a 60 degree fan beam that is perpendicular to the direction of travel of the lidar platform. The sensor is known as a pushbroom sensor. The volume of water is imaged one slice at a time. The data representing the water volume is an ordered set of slices. These slices are also called frames. Except for a small overlap each camera records the reflections from a particular angular sector of reflections from the transmitted fan beam. Typically the fan beam is about 648 feet across and each camera records the reflections resulting from about 15 degrees or about 162 feet of the fan beam. In the data processor these frames will later be summed into groups of eight known as superframes see .

The native data produced by ALMDS are collected in cylindrical coordinates in which columns correspond to cone angles rows correspond to slant range corresponding to a time of flight and frames correspond to along track views or in the language of cylindrical coordinates angle theta radius r and axis z respectively.

The transmitted pulse is referred to as the transmitted signal and the received pulse is the received signal. A single transmitted pulse gives rise to many received pulses because the volume elements of the water itself each reflect a small but detectable portion of the transmitted pulse back to the ladar and these may be resolved in time increments. Oftentimes bright flashes from the surface of the water are added to this volumetric return as well as reflections from objects in the water. The transmitted signal passes through a channel that includes optics the air a haze over water in the region of interest the water s surface and the water and then reflects off of a target if there is one .

As used herein a contact means a detection of something that is neither water sea bottom nor wave. A contact may be for example a fish a mine or floating debris. A classification is a declaration that the contact is either a mine like object MLO or a non mine like object NMLO . This terminology is utilized because the primary motivation of the invention is to find mines. However by changing the shape of the kernel the invention could be utilized to find objects that have other shapes i.e. fish like objects. An identification means the determination of the type of mine which is possible using variants of the existing algorithms to determine shape in more detail.

If a detection is made the raw data cube of voxels containing the detection along with some additional information such as its geolocation and the water attenuation constant are saved along with the data cube in the database . Another database which is referred to as a raw data recorder RDR is capable of recording streaming raw images from one or more cameras simultaneously.

In a water penetrating laser radar ladar there are two aspects that complicate the classification of data cubes as being MLO or NMLO for moored mines. The first aspect is the absorption and scattering caused by the water and other factors the second aspect is the low level of reflected light from the targets. Attenuation can be so extreme that combined with the blurring the received reflection from a mine is not discernable in the image data by the unaided eye although it may be detected by this algorithm. Further improvements can be obtained by means of statistical estimation when the statistical characteristics of the blurring and the detector are known.

As shown in in one embodiment the method of this invention includes four steps preprocessing image processing detection and classification . The preprocessing step is used to reduce data flow and to eliminate receiver artifacts. The image processing step determines the region of interest and removes biases in the data that degrade the performance of the detector. The detection step uses a modified likelihood ratio expression to detect contacts. The classification step computes features such as texture and size that are utilized to discriminate mine like objects MLOs or non mine like objects NMLOs .

The automatic target recognition ATR herein may be considered to be an alert confirm sequential detector. A detector makes a decision about each chunk of volume that is is it a contact or not After detection a second stage classifies the contact as a mine like object MLO or a non mine like object NMLO . The signal processing can be performed using software within the data processing unit in an Airborne Laser Mine Detection System ALMDS pod.

The data from each camera are typically displayed as a matrix of pixel values in a matrix view giving the false impression that the data are expressed in a Cartesian coordinate system. For example if the ALMDS were to be used in a terrestrial collection the data is collected in a cylindrical coordinate system. This is also the case when the region of interest is just the ocean surface. Columns correspond directly to cone angle rows correspond to radial distance from the origin the sensor and frames along track motion correspond to movement along the z axis the direction of aircraft flight . This is also true for underwater data except that Snell ray bending at the air water interface must be taken into account and the time of flight for photons must be interpreted to take into account the velocity of light in water. Thus although the matrix of angle radius pixels is often presented in a Cartesian arrangement of rows and columns it isn t really Cartesian at all and because of Snell s Law bending it s not exactly a straightforward cylindrical coordinate system either. To present the data in this way as a matrix in a Cartesian frame is to distort the image captured by the ladar. In particular the ocean surface which everyone knows is locally flat on average appears in the ALMDS data to be curved on average. If the sensor is unpitched mathematically the surface curve follows a secant relationship with roll angle or column . Changing the data from its native coordinate system to a Cartesian system is referred to as ortho rectification. This is not done with underwater data because the distortion is small for objects the size of a mine and ortho rectification is computationally expensive. If this kind of process were needed the target templates would be modified to match the distortion of the data rather than processing all the data.

The preprocessing step has two functions 1 to eliminate receiver artifacts and 2 to reduce data flow. For example if there is a vertical column in a camera image that contains only receiver artifacts rather than data this column can be replaced by an average of the data to the left and right of it. The ladar data are binned by averaging each group of eight consecutive frames into a single superframe . Thus each pixel in a superframe is the average of eight pixels that have identical row column indices in the raw frames. Each superframe is a two dimensional object that is sent for image processing and then to a detector. Binning is performed with a stride of two. In other words each superframe shares six frames in its construction with the previous and next superframes.

As the lidar system flies frames are collected at a rate of a given number of frames per second. The example of shows that each superframe is the average of eight raw frames that have been collected sequentially in time. The next superframe shares six frames with the previous superframe. This is similar to constructing a moving average of each pixel. Mathematically the effect of binning is similar to that of non coherent integration and similar to convolution with a pulse matched filter in the along track dimension.

An ALMDS camera frame data is arranged in 512 columns numbered from 0 to 511. The ALMDS receiver has artifacts at the quadrant boundaries and column of the previous frame is duplicated at column of the current frame. The quadrant boundaries are located at columns and . The quadrant boundaries are columns in which there is missing data. Without preprocessing they can affect the performance of the detector. The data in the quadrant boundary columns are replaced by the average of data in columns to either side. The duplication of column the far right hand column into column the far left hand column is addressed by copying column into column . If a different LIDAR were used that had different artifacts or a different data rate or if the data processor had a different computational capacity in FLOPS then appropriate changes to this procedure must be made.

The image processing stage includes a step that is similar to ortho rectification in that it causes the ocean surface to appear flat. The step is known as unwarping the frame. To unwarp one needs to know the cone angle that corresponds to each column of the image. The cone angle is therefore dependent upon the orientation of the platform for example a helicopter relative to the earth and the orientation of the sensor with respect to the platform as well as the viewing angle within the sensor to which each column in the image corresponds. One may obtain the approximate cone angle of each column from the rule cos cos cos 1 where is the platform pitch and is the sum of the platform roll and the roll angle that corresponds to a particular column 2 

In the sensor coordinate system as opposed to the coordinate system of the aircraft the roll angle that corresponds to a particular column j is given by 

The software takes into account the fact that in one embodiment the cameras have 20.48 columns of overlap and that the edges of their fields of view are located at roll offsets of 14.1 0.3 0.3 and 14.1 degrees.

The problem with using i j directly is that it is the absolute displacement in rows of the ocean surface from nadir so this function of j has a constant bias that is equal to the displacement in rows of the ocean surface from nadir to the highest row of the surface in a particular camera.

An outboard camera usually does not include the nadir column. So an outboard camera may have a large constant bias in rows equal to the net extent in rows of the ocean surface across the adjacent inboard camera. To unwarp an image the column in which the highest row of the ocean surface is found is displaced by zero rows and any other columns in which the ocean surface is lower are pulled up to match the highest row of the ocean surface. The highest row is the one representing lidar reflections that are closest to the LIDAR or a user s point of view when looking at a graphical viewer. Because the standard mathematical convention for matrix indices is utilized 0 0 is located to the upper left that is lower row indices contain reflections that are closer to the LIDAR.

The range of absolute displacements of the ocean surface for a particular camera is found by exhaustive search in the software. Mathematically it is expressed as 5 where

Thus column jin which the ocean surface is highest is not moved at all. All other pixel values are moved according to the rule 9 where is the gray level of the image at row i and column j which must be iterated with values of i increasing in order not to overwrite data . This makes the columns appear to be pulled upward in the image and the ocean surface will appear flattened .

Not all pixels can be moved when the airborne data processor has limited memory hardware. The bottom part of the frame is cut off after the unwarp operation. From this point onward the data processor operates on a much smaller frame.

Because the frame has been unwarped the row containing the ocean surface is easily found as the row of greatest value in a vertical silhouette projection of the unwarped frame 

Equalization is performed by first finding a well behaved column WBC whose index is in the columns within the indices range of 10 501. Columns near the image edges may have artifacts or noisy data. A well behaved column is one that never has a value greater than 4000 or less than some predetermined minimum value. The first constraint guarantees that the column is unsaturated and the second guarantees that it has at least one pixel that has a realistic surface reflection. Thus a well behaved column has a good dynamic range without saturating. Because of these nice properties the well behaved column is also utilized to compute k described later .

The model for equalization is that each column follows the same decay curve except for a constant multiplier. The decay curve does not have to be exponential. In fact it is precisely for this reason that a WBC rather than an exponential curve is utilized. To wit the model for the value of any pixel below the surface is 11 where f i is the decay curve of the WBC and Ais the value of the curve at the ocean surface A . Let j be the index of the WBC. The decay curve is formed as . 12 

Thus the decay curve is a set of numbers with a maximum of unity at the surface and decreasing towards zero as index i increases.

This model is perfect for equalizing the WBC. If this model were perfect for every column j then Af i 13 would always be unity except for pixels containing targets. This presumes that the WBC does not contain a target. This is of course not quite the case in real life but it is close enough. Any disturbance in the water or receiver artifact leads to a problem with the equalization. Thus the streak tube blobs or an MLO pixel will not equalize properly. On the whole it helps the detector.

A slight loss in the overall system probability of detection occurs due to the fact that a target occasionally lies in the WBC. This problem may be overcome by testing the WBC to be sure it is clear of targets. There are a number of ways to do this. If a target is determined to be within the WBC then another column must be chosen to be the WBC.

The above system can be modified as A where the summation is performed in the rows below the surface. Using an average of gray levels in rows below the ocean surface can be more stable than using a single gray level.

The detector operates by computing a statistic in a region that is about the size of an MLO of the data and then comparing the statistic to a threshold. If the statistic is greater than the threshold a target is declared to exist in that region of the data. If not then no target is declared. This procedure is exhaustively applied to every region of the data in the search for targets. Even when a target is declared it must still be classified as an MLO or NMLO.

This invention assumes that the data model for a streak tube CCD camera is reasonably modelled as Poisson. In that case a target of non uniform intensity has as its sufficient statistic the weighted sum 

In order to speed the computations one designs the detector as if the target has uniform intensity. The above expression then reduces to 

Note that this summation is mathematically equivalent to convolution with a rectangular pulse of unity amplitude. In other words multiply by one and add is equivalent to add . The sufficient statistic is simply the sum of the pixel values. Performance estimates may be derived analytically from the sufficient statistic and the Poisson probability model. is a one dimensional example of the two dimensional detector.

The assumption of uniform intensity means that the detector is a correlation receiver. The receiver compares a normalized version of the input data to a stored rectangular template. This is accomplished by summing point by point multiplication of each pixel in a region of the data with the corresponding pixel in the stored template.

The normalized sum is then compared to a threshold. The threshold determines the false alarm rate FAR of the alert part of the sequential detection. The threshold is set so that the false alarm rate is as low as possible without reducing detection performance below the system requirements.

The stored template for the ALMDS detector is a rectangular region of numbers in the row column dimensions in one superframe. One may consider the template to be a vector in a multi dimensional space.

An over simplified view of a template using 1 s and 0 s is shown in . is a simple N N template of a mine. The shaded pixels correspond to the target 1 s and the clear pixels correspond to background 0 s . Each box represents one pixel.

As described earlier the choice of a simple binary template 1 s and 0 s allows the computations to be sped up. This is so for two reasons 1 because the multiply add that must be performed at each template position is now simply an add and 2 because the sum at the next template position may be found by adding one data value and subtracting another as illustrated in one dimension in . is a one dimensional example of computational speed up. After the first summation is completed each subsequent sum may be found by adding one number and subtracting another.

In two dimensions this process is implemented as follows. Given the superframe in a frame of partial sums is computed by summing all pixels whose indices are less than or equal to the indices of the pixel in the frame of partial sums. All the adding is done in advance in order to speed up the computation of the convolutions by the rectangular filters. The reason the frame of partial sums is created is that the partial sums may be combined in a simple way that requires only three additions as shown in wherein the output of a rectangular filter is equal to the sums in rectangle A rectangle D minus rectangle B rectangle C .

In order to make the detector responsive to signal shape not signal strength every region of the image that is sent to the detector is normalized to unit energy. The energy in a region is approximated by the L1 norm in other words the sum of the pixel values. This allows the summation image of partial sums to be re used for computing signal energy rather than a costly computation of sum of squares. Thus the output of the detector is actually a ratio of two sums. The frame of partial sums is utilized to compute each sum. shows that the output of the detector is the ratio of the sum of pixel values in the inner rectangle divided by the sum of pixel values in the outer rectangle. In the inner sum in the small rectangle the matched filter value is divided by the outer sum in the large rectangle the energy in the data .

The threshold has also been generalized in the sense that it is depth dependent. This is accomplished as follows. The outputs of the detector at each depth row are utilized to compute a mean and standard deviation of the detector at that depth. The statistical k of the detector is defined to be the division of the output of the detector xminus its row mean by the standard deviation at that row 

It is actually the statistical k of the detector output that is compared to the threshold. The typical threshold rhas been determined empirically to be as high as 4.5 to reduce the false alarm rate without reducing the probability of detection very much.

The detector may produce multiple hits threshold crossings in the vicinity of each other. Such an event is typical near a target. When that happens the hit with the greatest statistical k is retained. A rule is built into the algorithm so that only one target is allowed in each column. This is called a clustering algorithm. This is because it is physically impossible for the ladar to see through targets and each column corresponds exactly to an angular line of sight.

The classifier uses texture size and aspect ratio to classify targets. The classifiers take as an input a two dimensional region known as the postage stamp that is constructed from a three dimensional 50 frame by 50 column by 10 row tensor known as the contact cube centered on the contact. The full postage stamp is 50 frames by 50 columns. The postage stamp is constructed by averaging 5 rows in the region around the target.

Texture is computed using a simplified version of Kruger s spatial gray level dependence matrix. The size and aspect ratio are derived from the parameters of a two dimensional Gaussian intensity surface that is fitted to a two dimensional projection of the target using the Levenberg Marquardt algorithm.

Texture is the main feature utilized to distinguish targets from false alarms. The smoother the contact the more likely the contact is an MLO. In one example texture is measured on an 11 frame by 11 column region within the postage stamp consisting of 121 numbers.

The S function is like a joint probability function of gray levels among neighboring pixels within distance d . From all this a single texture number is created by taking an average in all directions 

If the correlation texture is greater than a depth dependent threshold then the contact is declared to be an MLO.

Surface targets go through an additional stage of processing known as coincidence shadow detection CSD . is a top level block diagram that describes the essence of the CSD algorithm. The algorithm includes the steps of raw detection of the signal shadow detection clustering target detection and discrimination by texture .

For raw detection of the signal let the surface layer be confined between depths nand nin pixel units. For a given azimuth m let n n m nbe the depth at which the signal is the maximum. This defines the surface .

The surface signal is denoted by S m n m k where k is the frame index. For a given threshold T let m p 1 2 3 . . . be the set of azimuths at which signal peaks above the threshold that is . 22 

The output of this processing is the peak detected depth as a function of the peak detected azimuth. 1 2 3 . . . 23 

In the shadow detection part of the processing the existence of shadow is examined at the peak azimuths m p 1 2 3 . . . found in the raw detection stage. For a given m the shadow confirmation is performed at the shadow depth 24 using 3 2 m 1 pixels centered about azimuth pixel m.

This process is repeated at N different depths starting from n. Then M out of N shadow detection criteria is imposed to determine whether the peak signal under interrogation has a shadow or not.

For clustering and coincidence shadow detection the output of the shadow detection processing is a data cube and the set of shadow detected positions in three dimensions is m n k . Since in this example we are dealing strictly with surface targets this data cube is collapsed in the depth dimension and the clustering is done in azimuth only. This procedure is not valid if subsurface target detection is of interest. The result is a data sheet that is a two dimensional array m k of shadow detected locations in azimuth and the along track dimension.

Let mbe the size of the azimuth clustering window . As the precursor to the coincidence shadow detection the data within the window is collapsed in the azimuth dimension. Graphically the cluster processing proceeds as shown in .

In one embodiment the detection criteria is either a minimum of 5 contiguous shadows or a minimum of 6 out of 7 shadows will admit 7 out of 8 8 out of 9 so on . Two detections are considered separate in the along track dimension if there are two or more consecutive missing shadows between them.

For a group of shadow detections that meet this criteria the azimuth and the frame of the detected object is determined by the mean of the azimuths and frame numbers of detections within the group.

Discrimination can be performed using a scintillation count. The temporal variation of the target signal is examined at the center azimuth of the target. If more than a certain number of scintillations occur the contact is not considered to be a MLO. What constitutes a scintillation and threshold number of scintillations for making this declaration is determined empirically.

When the model of exponential decay is assumed the variable k is the extinction coefficient of the lidar echo from water. The derivation of the k estimation algorithm begins with the observation that the volumetric return has an intensity proportional to the round trip attenuation in water.

The measured return f z is 29 where G is a constant including all receiver parameters and water reflectivity. One may form the ratio 

The system effectiveness index SEI is calculated based upon the estimated k value k for the water volume being searched calculated during a mission and a full performance depth product k z input during data initialization.

The SEI is calculated as SEI k z k. The system also calculates a default value for a full performance depth product.

SEI measures distance. The SEIis developed as follows. The ATR Pd and FAR performance at a specified depth z is determined by the product K z where K is the predicted diffuse attenuation.

If the measured value of diffuse attenuation K differs from the prediction the same performance is achieved at a new depth z so long as the attenuation product is held constant that is 39 

Thus the system effectiveness is the actual absolute depth at which identical performance is achieved as was predicted at specified depth z with the predicted diffuse attenuation K .

While the invention has been described in terms of several embodiments it will be apparent to those skilled in the art that various changes can be made to the described embodiments without departing from the scope of the invention as set forth in the following claims.

