---

title: Method for real time matched field processing
abstract: A method for utilizing a matched field-processing algorithm employing a number of sensors wherein the sensor output is the measured acoustic data as the first input and is translated to a frequency by applying a Fourier transform to a set of time samples as a data vector output. A replica vector is the second data input as a predicted quantity which is computed by an acoustic model with an assumed acoustic location. The output is an ambiguity surface ranging between zero and one with the highest values indicating the likely position of an acoustic location. The matched field response is generalized by averaging the response over multiple frequencies. A response for an array may be computed by forming beams and then combining them by multiplying each by an eigenray factor before summing. The computation of the response may be further defined by voxel interpolation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07800978&OS=07800978&RS=07800978
owner: The United States of America as represented by the Secretary of the Navy
number: 07800978
owner_city: Washington
owner_country: US
publication_date: 20070130
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

This application is co pending with related application application Ser. No. 11 767 787 filed 25 Jun. 2007 entitled Point Source Localization Sonar System and Method by co inventors W. Robert Bernecky and Matthew J. Krzych.

The present invention relates to a method for computing a real time matched field response using sensor outputs of a passive sonar array.

Matched field processing MFP is a sonar signal processing technique that incorporates acoustic propagation modeling into signal processing algorithms. MFP provides for localization of an acoustic point source in three dimensions.

In operation the MFP beamformer matches the sound pressure field measured by an array of hydrophone sensors with a replica. The replica is derived from an acoustic propagation model and presumes a specific location for the acoustic source. That is each hypothetical location of the presumed sound source determines in conjunction with oceanic acoustic propagation parameters a particular replica.

Each replica is matched with the measured field and the maximum values computed by the MFP represent the replicas that most closely represent the received measured signal. This information enables the MFP to estimate the location of a sound source in range distance bearing and depth.

Previous methods for computing a broadband matched field surface have various shortcomings. In a first shortcoming the methods are computationally expensive. The methods are also not suitable for producing results in real time because the methods do not compute results at a rate equal to the rate of the incoming sensor data. Furthermore the methods use stationary vertically oriented arrays and cannot be used on mobile horizontally towed sensor arrays. Also no previous method efficiently compensates for the changing shape of a towed array of sensors.

As such a need exists for computing a broadband matched field surface in real time as an improved method of determining the distance angular bearing and depth of an acoustic source relative to a sonar sensor array. Preferably the method would be flexible and mobile as well as comparatively inexpensive to existing methods.

Accordingly it is a general purpose and primary object of the present invention to provide a method for determining real time matched field responses.

It is a further object of the present invention to provide a cost effective method for determining real time matched field responses.

It is a still further object of the present invention to provide a mobile method for determining real time matched field responses.

In order to attain the objects of the present invention a method is provided for computing real time matched field responses. The method utilizes an algorithm and requires two data inputs. The first data input is measured acoustic data from a sonar set of hydrophones. The second data input is a replica data set against which the measured data is compared. Multiple replicas are compared to the measured data and the closest match is retained. The closest match of the replica is presumed to characterize the data in some important way e.g. a source location .

More specifically the output of a sensor of the towed array is translated to the frequency domain by applying a discrete Fourier transform DFT or a fast Fourier transform FFT to a set of contiguous time samples x n t Tto T . A replica vector d is the frequency domain N 1 vector representing the predicted or expected values at each sensor of the sensor array for a specific frequency.

The corresponding output of the method is an ambiguity surface. The ambiguity surface is a set of numbers ranging between zero and one with each number corresponding to a specific location in the ocean. The highest values on the ambiguity surface indicate the most likely position of an acoustic source.

A more complete understanding of the invention and many of the attendant advantages thereto will be readily appreciated as the same becomes better understood by reference to the following detailed description when considered in conjunction with the accompanying drawings wherein like reference numerals and symbols designate identical and corresponding parts through the view and wherein 

The method of the present invention for real time matched field processing primarily utilizes a matched field processing algorithm and requires two data inputs.

The first data input is measured acoustic data from at least one sensor of a sonar array of hydrophones. The second data input is a predicted data set or a replica data set against which the measured data is compared. Multiple replicas are compared to the measured data and the closest match is retained. The closest match of the replica is presumed to characterize the data in some important way e.g. a source location .

Referring now to the drawings in detail wherein like numerals indicate like elements throughout the several views 

The output of the sensor n is translated to the frequency domain by applying a discrete Fourier transform DFT or a fast Fourier transform FFT to a set of contiguous time samples x n t Tto T . This frequency domain output is denoted by X n where n again is the sensor number and is the frequency index. The frequency domain sensor output for a fixed frequency defines the N 1 data vector x X Na X Na 1 . . . X Na 1 X Na . Here Na is N 1 2 assuming N is odd and T represents the vector transpose operator.

Often the data vector x is replaced by a sample co variance matrix R the heard and measured data . The sample co variance matrix is formed from the time average of successive snapshots of the L data vector 

As indicated above the method of the present invention requires a replica vector for a second data input. In the following description the replica vector is referred to as d . The replica vector d is the frequency domain N 1 vector representing the predicted or expected values at each sensor of the sensor array for a specific frequency .

Conventional matched field processing forms an average of the projections between the data vector and the normalized replica vectors 

The denominator dd tr R in Equation 2 explicitly defines the normalization factors that ensure that the maximum value of the response is less than or equal to one. The tr notation refers to the trace of a matrix which is the sum of the diagonal elements.

Equation 2 defines the response of the method for a single vector d against the average of the L most recently measured data vectors. This response is a number between zero and one and represents the degree to which the measured data vector matches the replica vector.

In matched field processing the replica vector is a predicted quantity which is computed by an acoustic model that begins with an assumed acoustic point source location at a specific position in the water column. The acoustic model which incorporates such parameters as an ocean temperature profile and an ocean bottom depth calculates what the acoustic field would be at the sonar array . That is each replica vector represents a prediction of the acoustic field at the sonar array assuming that an acoustic point source is at a specific location in the water. An entire set of replicas represents some volume of the surrounding water.

The corresponding output of the method is an ambiguity surface. The ambiguity surface is a set of numbers ranging between zero and one with each number corresponding to a specific location in the ocean. The highest values on the ambiguity surface indicate the most likely position of an acoustic source.

The method of the present invention generalizes Equation 2 to a broadband matched field response. This broadband response B is computed by averaging the matched field response over multiple frequencies 

As stated above the replica vector d or predicted measurement across the sonar array is computed using an ocean acoustic model. Acoustic models can be categorized into four broad types ray theory spectral integral methods normal mode theory and parabolic equations. The following derivation of the method of the present invention uses ray theory but the other model types are equally valid for use and may be substituted with by those ordinarily skilled in the art.

To begin let d be an N 1 replica vector that describes the complex pressure at angular frequency sampled at each of N sensors in the array . Each element dof d is a sum of P eigenrays computed by the acoustic model 

Each eigenray indexed by p has an amplitude p n an additive phase shift p n due to reflections and or refraction efforts and phase . The phase term contains the total travel time from the acoustic source to the sensor n along the eigenray p. In the vicinity of the sensor i.e. over the extent of the sonar array it is assumed that the amplitude

 and additive phrase are approximately constant. Also the phase at the sensor n may be approximated as . 6 

Here is the total travel time of the signal from the source to the sensor along the peigenray and is an additional travel time from the sensor to the sensor n. Equation 5 may be approximated as 

In Equation 7 sis a relative phase shift that is applied to dto adjust for the additional travel time from sensor to sensor n. Assembling the individual elements dinto the N 1 replica vector d and forming the N 1 steering vector sfor each eigenray p 

In Equation 8 the eigenray steering vector is introduced as S an N 1 vector of phase shifts exp j . The is the travel time of an acoustic wave along the eigenray p from the array origin to the sensor n. In general an eigenray may be viewed as defining the normal of a spherically spreading wavefront i.e. the direction of propagation . This directionality may be related to an arrival angle at the horizontal sonar array.

where is the sensor spacing n is the sensor index c is the local speed of sound and is the arrival angle of eigenray p. This linear time delay as a function of sensor position corresponds to well known planewave beamforming. This method for estimating can be refined to account for near field effects by using range focusing techniques.

In Equation 10 bis the complex beamformer output resulting from application of the steering vector for eigenray p to the frequency domain sensor data x. That is bis computed by forming a beam steered at the conical angle . This is done for each of the P eigenrays. The advantage to doing this is that there exists an efficient algorithm for rapidly computing a beam i.e. k beamforming for a line array . Effectively this process reduces the computation from N sensors to P directional sensors.

Letting e be the P 1 vector of eigenrays from the source to the array origin Equation 7 and b be the P 1 beamformer outputs Equation 10 may be written as 11 

To account for the normalizing factors in the denominator of Equation 4 the data vector x is divided by the average over time of xx. The eigenray vector e may be normalized by ee. This approximation is generally effective when processing broadband contiguous frequencies so that the individual variation from frequency to frequency averages out. Incorporating the normalizing factors and Equation 11 into Equation 4 the method of the present invention is defined to be 

This result states that a matched field response for a horizontal line array may be computed by first forming P beams and then combining them by multiplying each by a complex eigenray factor before summing. The complex eigenray factor makes up components of the vector e used in Equation 12 . The individual components of vector e are first defined in equation 7 .

Furthermore the eigenray factors need only be computed for the origin of the sensor array and not for each individual sensor in the array. Of course for very long arrays the approximations used in the derivation of the algorithm may no longer apply. In such instances the sensor array must be treated as a set of shorter subarrays. The sensor array of N hydrophones sensors is reduced to some number of effective sensors P

The full computation of the matched field response may be further reduced by applying voxel interpolation. A voxel or volume element is a three dimensional region in space with dimensions of range x axis depth y axis and bearing angular width .

In the figure the angular coordinate is zero degrees in the horizontal direction pointing directly toward the sonar array at ninety degrees pointing directly vertical to the ocean surface and 180 degrees away from the sonar array and 270 degrees toward the ocean bottom.

Voxel interpolation relies on the concept that an acoustic source displaced from the voxel origin at a distance and at an angle may be approximated as a perturbation to the eigenrays departing from the voxel center as computed by an acoustic model.

Specifically the eigenrays generated by an acoustic model for the voxel origin are each defined by travel time attenuation additive phase arrival angle and departure angle. The last two parameters listed predicate that an eigenray departs from a point source at some angle from the horizontal and proceeds up or down through various reflections before finally approaching the arrival point at some other angle also measured relative to the horizontal.

If the source location of an eigenray is offset from an original departure point by a small amount then it may be assumed that the perturbed eigenray has approximately the same attenuation additive phase arrival angle and departure angle and the single significant deviation is in total travel time. That is if an eigenray e is defined by exp 13 

then the perturbed eigenray e displaced from the origin by distance and angle is given by acute over exp 14 where is the delta to the total travel time of the eigenray.

In the operational stages the field processing of the real time matched algorithm requires and presumes certain hardware and software components including a linear array or a set of linear arrays with equispaced hydrophones. The array s may be fixed or towed. Ideally the array provides measurements such as array heading and array depth from devices embedded along the length of the array.

Further components include an ocean acoustic model and digital processing hardware suitable for executing both the ocean acoustic model and the real time matched field processing algorithm.

Using as guidance the input needed for the method of the present invention is sonar sensor data from a line type array that has been transformed to the wavenumber frequency domain. Multiple snapshots moments in time may be passed into the process however there is a practical limit due to the dynamic nature of the sensor array and the changing environment.

Needed input is also the set eigenrays for each voxel to be processed. The real time matched field processing algorithm does not stipulate what voxels should be processed nor in what order. Additionally the number of eigenrays per voxel is not strictly defined by the algorithm. It is recommended that only those eigenrays that contribute a significant fraction of the pressure field be included in the processing.

The method of the present invention is now described for one time step and one frequency. The full output of the process given by Equation 12 requires that this process be repeated and averaged over time and frequency.

The process begins by computing the eigenrays between the source at the origin of a voxel and the destination at the acoustic center of the sonar array . Only the most significant P eigenrays are retained. The most significant eigenrays are chosen by computing the eigenrays that describe the acoustic signal at one spot in the ocean. This set of eigenrays is sorted by the energy of each eigenray large to small. Add the energy of each eigenray in the set strong to weak until the sum of the energies represents ninety percent of the total.

A beam is then formed for each of the P eigenrays. That is using an efficient range focused k beamforming algorithm a beam is computed that is steered exactly at the conical angle coinciding with the arrival angle of the eigenray being considered. The result of this step is a P 1 complex vector b representing the P beams formed along the P possibly non unique conical arrival angles.

The individual beams are then attenuated and phase shifted as indicated by Equations 10 and 11 . Let f be the

P 1 vector resulting from this step i.e. eb ff . Note that the magnitude square of the complex summation of the P result eb is the real time matched algorithm response for the center of the voxel.

For the subvoxel at location compute P phase shifts exp j where of each is defined by Equation 15 to form the P 1 vector g . The real time matched algorithm output for the subvoxel is then gf note that the phase shifts have been conjugated to account for the complex conjugate transpose operator. Repeat for each subvoxel in the voxel.

A significant advantage of the described method of the present invention is the savings in computational cost. The computational advantage supports the feature of processing mobile horizontal towed array sonar data by using digital processing in real time. Specifically the first savings arises from the feature that the acoustic model computes the eigenrays only between the center of the sonar array and the center of the voxel. This is in contrast to computing the eigenrays between every source point for example the 400 subvoxels and every destination point for example 50 individual hydrophones a factor of 20 000 greater computation.

Second the subvoxel response is computed using P inputs rather than N the number of sensors . This reduces the cost of the computation by N P or approximately by a factor of five for many applications.

Third the method of the present invention takes advantage of k beamforming an N log N computation as compared to the Ncomputation which would otherwise be required.

Fourth the range focused k beamforming supports efficient compensation for some shape distortion of the sonar arrays.

The foregoing description of the preferred embodiment of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive nor to limit the invention to the precise form disclosed and obviously many modifications and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

