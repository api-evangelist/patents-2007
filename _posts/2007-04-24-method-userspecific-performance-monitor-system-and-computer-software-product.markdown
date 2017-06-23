---

title: Method, user-specific performance monitor, system, and computer software product
abstract: The invention relates to a method, equipment implementing the method, and a computer software product, the method generating exercise instructions for a physical exercise. The method comprises determining the standard condition value of a heart rate parameter in a user-specific performance monitor by measuring the user's heart rate wherein the standard condition value of the heart rate parameter is a function of the standard condition value of the heart rate variation; performing comparison between the standard condition value of the heart rate parameter and a standard condition reference value of the heart rate parameter; and generating exercise instruction information for at least one future physical exercise on the basis of the comparison.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08082030&OS=08082030&RS=08082030
owner: Polar Electro Oy
number: 08082030
owner_city: Kempele
owner_country: FI
publication_date: 20070424
---
This application claims priority to Finnish Patent Application Serial No. 20065286 filed on May 3 2006 which is incorporated herein by reference.

The invention relates to a method for generating exercise instructions for a physical exercise a user specific performance monitor a system for generating exercise instructions for a physical exercise and a computer software product.

The aim of exercise instructions for a physical exercise is typically to achieve optimal physical condition for a person doing keep fit exercise or for a competing athlete. The exercise instructions are typically included in a training program prepared by trainers for example. Training programs typically define training parameters aimed at such as the time duration and intensity of the exercise.

Training programs are typically prepared according to the type of sport for a longer period of time in advance based on the advance information on the effects of the particular training program on physical condition. Modification of the training program is typically based on follow up of physical condition taking place infrequently in test exercises monitored by the trainer or by measuring ultimate performance for instance in competitive situations.

It is known that physical exercises that are heavy with respect to their intensity can quickly build up maximum physical condition but heavy exercises repeated too often may result in overexertion instead of build up of physical condition. The optimal amount of heavy exercise may be different with different persons. Studies on physical education have shown that the build up of physical condition with the same exercise program may vary a great deal between different persons. A training program that has built up the physical condition of some people has provided a negative change in the physical condition or no change at all for some test persons.

A long term training program and infrequent follow up according to known methods are not capable of producing real time information on the basis of which the training program could be optimized to achieve user specifically as good physical condition as possible. Thus it is worthwhile to consider expedients with which to generate exercise instructions for a physical exercise.

An object of the invention is to implement a method a user specific performance monitor a system and a computer software product in such a way that user specific generation of exercise instructions is achieved. As a first aspect of the invention the invention provides a method for generating exercise instructions for a physical exercise the method comprising determining the standard condition value of a heart rate parameter in a user specific performance monitor by measuring the user s heart rate performing comparison between the standard condition value of the heart rate parameter and a standard condition reference value of the heart rate parameter and generating exercise instruction information for at least one future physical exercise on the basis of the comparison.

A second aspect of the invention provides a user specific performance monitor comprising a heart rate measurement unit for measuring the user s heart rate a heart rate parameter determination unit for determining the standard condition value of a heart rate parameter on the basis of the user s heart rate a comparison unit for performing comparison between the standard condition value of a heart rate parameter and a standard condition reference value of the heart rate parameter and an instruction determination unit for generating exercise instruction information for at least one future physical exercise on the basis of the comparison.

As a third aspect of the invention the invention provides a system for generating exercise instructions for a physical exercise comprising heart rate parameter value determination means for determining the standard condition value of a heart rate parameter by measuring the user s heart rate in a user specific performance monitor comparison means for performing comparison between the standard condition value of the heart rate parameter and a standard condition reference value of the heart rate parameter and instruction generating means for generating exercise instruction information for at least one future physical exercise on the basis of the comparison.

As another aspect of the invention the invention provides a computer software product comprising coded instructions for executing a computer process in a digital processor which computer process generates exercise instructions for a physical exercise the computer process comprising inputting heart rate information measured in a user specific performance monitor determining the standard condition value of a heart rate parameter on the basis of the heart rate information performing comparison between the standard condition value of the heart rate parameter and a standard condition reference value of the heart rate parameter and generating exercise instruction information for at least one future physical exercise on the basis of the comparison.

The invention is based on the idea that the user s response to preceding exercises is determined by measuring a standard condition heart rate parameter the heart rate parameter being compared with a reference value of the heart rate parameter. On the basis of the comparison an exercise instruction concerning a future exercise is determined.

The method user specific performance monitor system and computer software product according to the invention provide several advantages. One advantage is obtaining a user specific optimized or nearly optimized exercise instruction that takes into account the exertion caused by previous exercises.

The electrodes A B detect the electric potential difference generated by the electric activity of the heart muscle and generate an ECG signal characterizing the electric activity of the heart muscle. The ECG signal is fed to the ECG preamplifier from the electrodes A B.

The ECG preamplifier preamplifies the ECG signal and feeds the preamplified ECG signal to the first communication unit . The first communication unit may comprise several successive amplifier stages such as AGC Automatic Gain Control amplifier and a power amplifier.

The first communication unit generates a signal transferring ECG information. The ECG information may for example use the ECG as such part of the ECG and or timing information of the heart rate. The timing information may contain a timing pulse that predicts the timing of a predetermined part of the ECG.

The signal transferring ECG information is an electromagnetic wave propagating in the air or in a conductor for instance.

The second communication unit receives the signal transferring ECG information and feeds the ECG information to the processing unit which executes a computer process according to the coded instructions stored in the memory unit .

The processing unit may be implemented by using analogue circuits ASIC circuits Application Specific Integrated Circuit a digital processor memory and computer software. The processing unit may form part of the computer of the measuring unit .

The user interface typically comprises a display unit DISP and a display controller. The display unit may contain LCD components Liquid Crystal Display for instance. The display unit may display the exercise instructions to the user graphically and or numerically.

The user interface may further comprise a keypad KP by means of which the user may feed commands to the performance monitor .

The performance monitor shown in may be divided into a heart rate transmitter HRTX and a central processing unit CEU . The heart rate transmitter typically comprises device parts A to and performs ECG measurement and transmission of ECG information to the central processing unit . In some embodiments the heart rate transmitter may comprise a heart rate detector which detects a predetermined part of the ECG generates the transmitter burst representing timing of a predetermined part of the ECG and or bit stream and transmits the transmitter burst to the central processing unit or for example to the second communication unit positioned in the server.

The central processing unit typically comprises device parts to which process the signal transmitting ECG information and implement the user interface. Further the central processing unit may comprise a measurement module that may carry out measurements such as acceleration measurements temperature measurements pressure measurements and or positioning measurements.

Referring to the embodiment of the heart rate transmitter is positioned in a transmitter belt around a user s chest. The ECG information may be transmitted telemetrically optically or galvanically from the heart rate transmitter to a central processing unit that may be a wrist device positioned around the user s wrist. However the presented solution is not restricted to a wrist device.

Referring to again in one embodiment the heart rate transmitter and the central processing unit are integrated into the same performance monitor which forms a performance monitor held around the user s wrist or around the handlebars of a bicycle. In such a case it may be that some device parts shown in such as the first communication unit and the second communication unit are not needed. In one embodiment the heart rate transmitter and part of the central processing unit are integrated into the transmitter belt whereby the transmitter belt may collect ECG data process ECG data and determine values of variables characterizing the heart rate. In this case the signal transferring ECG information transmits processed information such as values of variables characterizing the heart rate and commands given by the user between the heart rate transmitter and the central processing unit .

Referring to the example of a system may comprise a performance monitor PM and a calculation system CS . The performance monitor may exchange exercise information such as primary heart rate information standard condition heart rate parameters and standard condition reference values of a heart rate parameter with the calculation system via an exercise information signal . Primary heart rate information comprises for example part of an ECG signal or timing information of the ECG.

The calculation unit typically comprises a communication interface CI a central processing unit CPU a memory unit MEM and a user interface.

The communication interface implements the reception and possibly transmission of an exercise information signal . The communication interface is for instance a wireless interface such as a radio interface optical interface or audio interface. In one embodiment the communication interface is a cable interface.

The central processing unit executes a computer process according to the coded instructions stored in a memory unit to generate exercise instructions for a physical exercise. The central processing unit may feed the results of the processing such as exercise instruction information to an interface .

The calculation system may be implemented by means of a computer and software for example. The communication interface may be integrated into the calculation system or it may be a peripheral device to be connected to the calculation system.

Further the calculation system may be implemented by means of a portable communication device such a mobile phone or a PDA device Personal Digital Assistant .

Referring to a system is examined which comprises a heart rate measurement unit HRMU a heart rate parameter determination unit HRPDU a comparison unit CU and an instruction determination unit IDU .

The heart rate measurement unit measures the user s heart rate for example on the basis of the detection of the ECG signal described in connection with and generates a heart rate information signal . The heart rate information signal contains heart rate information on the user s heart rate. Heart rate information may be for instance timing information of heart rates or information on the heart rate frequency heart rate interval or heart rate variation.

The heart rate measurement unit feeds the heart rate information signal to the heart rate parameter determination unit which determines the standard condition value of a heart rate parameter on the basis of the heart rate information signal .

A standard condition heart rate parameter characterizes the heart rate of the person being the object of the heart rate measurement in standard conditions. Standard conditions refer to the physiological state of the person being the object of the heart rate measurement in such a way that the state remains the same or nearly the same in repetitions. Thus standard condition heart rate parameters determined under the same standard conditions are mutually comparable and may form a series of measurements representing the development of the heart rate parameter.

Standard conditions may be based on the user s passive action. Thus heart rate information of the period of several hours for example is fed to the heart rate parameter determination unit of which information the heart rate parameter determination unit determines the part corresponding to standard conditions and uses this part for determining a standard condition heart rate parameter. Let us take an example where the period of time includes an exercise and the following rest period such as night. Thus the heart rate parameter determination unit may deduce the prevailing standard conditions on the basis of the characteristics of the heart rate or the time measured and use the corresponding part of the heart rate information for determining a standard condition heart rate parameter. In one embodiment a standard condition heart rate parameter is determined when the person being the object of the heart rate measurement has just woken up. Standard conditions may also comprise a predetermined position of the person such as standing position.

Standard conditions may also be based on the user s active action. Thus the person being the object of the heart rate measurement may in a desired state start the heart rate measurement and the determination of a standard condition heart rate parameter. In one embodiment the system comprises reminder means RM that remind the user about the prevailing standard conditions and starting of the measurement. The reminder means may also remind the person to prepare for the standard conditions and to start the measurement.

Standard conditions may also be recognized on the basis of the user s activity the direction of the gravitation field or the direction of the magnetic field of the earth for example. The user s activity and or the direction of the gravitation field may be assessed by means of for instance an acceleration sensor positioned in connection with the performance monitor .

A standard condition heart rate parameter characterizes the response of the person being the object of the heart rate measurement to an exercise.

An exercise is typically a physical action by the user aiming at maintaining or affecting the user s physical performance. An exercise is a physical exercise such as a walking swimming or cycling exercise the invention not being restricted to these exercises.

In one embodiment the standard condition value is the function of the standard condition value of the heart rate variation. The standard condition heart rate variation characterizes the variability between successive heart rate intervals. Heart rate variation is also called heart rate variability HRV. The standard condition heart rate variation may be determined with a method according to prior art by using a Fourier and or autoregressive analysis for instance.

The standard condition value of a heart rate parameter is fed to the comparison unit which performs comparison between the standard condition value of the heart rate parameter and a standard condition reference value of the heart rate parameter.

The comparison unit feeds a comparison result characterizing the comparison to the instruction determination unit that generates exercise instruction information for at least one future exercise on the basis of the comparison.

Exercise instruction information comprises instructions for carrying out a future exercise intended for the person being the object of the heart rate measurement. Exercise instruction information comprises for example a recommendation on the time duration and intensity of the future exercise the type of the exercise the range of the heart rate or the energy consumption. Exercise instruction information may be presented with for example a weighted exertion index in which different ranges of the heart rate are weighted with coefficients specific to particular ranges of the heart rate.

The type of the exercise may be for instance an anaerobic exercise aerobic exercise or strength exercise.

In one embodiment the future exercise is relative to the preceding exercise the one following immediately. Exercise instruction information may comprise an instruction for a rest period so that in this context the exercise may also be a rest exercise.

The storing unit receives several day specific standard condition values of a heart rate parameter and stores the day specific standard condition values of the heart rate parameter. The calculation unit calculates a standard condition reference value of the heart rate parameter by using the standard condition day specific values of the heart rate parameter and feeds the standard condition reference value of the heart rate parameter to the comparison unit .

The day specific values of the standard condition heart rate parameter may be values of standard condition heart rate parameters that are measured on successive mornings in standing position. The calculation unit may calculate an average value for example of the day specific values of the standard condition heart rate parameter. The reference value may be the average value or a modified average value obtained from the average value and for example standard deviation. In one embodiment the reference value is the average value minus standard deviation.

With reference to an example of an exercise information table is examined which explains the example of the operation of an instruction determination unit . The black dots in the exercise information table denote standard condition values of a heart rate parameter. A horizontal axis shows time in a random unit and a vertical axis shows the value of the heart rate parameter in the random unit. Symbols F R L M and H show exercise instruction information FREE REST LIGHT EXERCISE MEDIUM HEAVY EXERCISE and HEAVY EXERCISE in this order.

The exercise information table of the example shows periods 1 to 14 where at the beginning of each there is a vertical broken line denoting the standard condition heart rate variation determined at the beginning of period 1 to 14.

In the example presented the standard condition reference value of the heart rate variation is determined during an initialization period whereby the exercise instruction is REST. Before the exercise of each rest period 1 to 5 such as on the morning of the rest period 1 to 5 the day specific standard condition heart rate variation is measured and stored in the storing unit .

In one embodiment the standard condition reference value of the heart rate variation is calculated during a flexible time period preceding the current moment of time and known in advance. The time period known in advance is for example 10 days whereby the standard condition heart rate variations measured during the last 10 days are used in calculating the standard condition reference value of the heart rate variation. The standard condition reference value of the heart rate variation may be updated every time new standard condition heart rate variation is determined.

With reference to a second example of an exercise information table is examined which is based on measurements on test persons. In the example shown the horizontal axis indicates time as days and the vertical axis indicates the natural logarithm InHF of the heart rate variation. A curve shows the natural logarithm of the measured heart rate variation and a curve shows the reference value of the heart rate variation. The letter codes determining the exercise instruction below the curves are as follows L light exercise H heavy exercise R rest.

The training program has been preceded by a period of eight days when there has been no training. The training instruction for the period preceding the training was rest. During this period and the following training program the test person measures the heart rate variation in standing position for five minutes after waking up in the mornings. The values of the heart rate variation are indicated on the curve . The actual training is started on the ninth day with light training including light jogging for 40 minutes the heart rate average being 65 of the maximum value. This corresponds to 120 to 130 heartbeats min with the test person. The next day training is continued with heavy exercise including 5 minutes of warm up 30 minutes of energetic running the aim of the heart rate average being 85 of the maximum heart rate which corresponds to about 160 to 170 heartbeats min and finally 5 minutes of warm down. The starting point for the training program is that it is implemented from the ninth day onwards with the sequence L H H L H H L H H R but from the eleventh day onwards it is changed to be lighter if the heart rate variation decreases systematically or if the heart rate variation is low. The reference value is the average of the InHF values measured during the preceding ten days minus the standard deviation calculated from the same values. In these situations if the training the day before has been heavy the instruction is light training and if the training the day before has been light the instruction is a rest day. A supplementary condition may be to have a rest day at least every ten days and to have light training as the training instruction after two rest days irrespective of the heart rate variation.

The training instruction has been changed from the original rhythm on five days in total. The changed exercise instructions have been underlined. For example on the 15day the heart rate variation decreases the second time in succession whereby the instruction is an easy day. On the 20day the heart rate variation decreases the second time in succession whereby the instruction is a rest day. On the 28and 29days the heart rate variation is below the reference value whereby the instruction is a rest day. On the 34day the heart rate variation is below the reference value whereby the instruction is light training. On the 42day the heart rate variation decreases the second time in succession whereby the instruction is a rest day.

When examining the training program drafted for this person and the one put into practice by him her it can be noted that the number of heavy exercises is slightly smaller than in the original program L H H L H H L H H R and that the time of the heavy exercises has slightly changed from the original plan. The user of the method of the solution according to the invention can gain benefit from the fact that heavy exercises may be done at such a time when his her system withstands a heavy exercise and the exercise thus leads to positive changes in the system with regard to build up of performance and physical condition. On the other hand the invention may encourage the user to do light exercise or to have a rest day when a low or decreased heart rate variation is detected.

Measurements on tests persons indicate that there may be great variations between persons having been training according to a program corresponding to the original instructions with regard to the change in physical condition so that with some people the physical condition gets worse whereas the group having been training according to the program of the invention may achieve a significantly better change in physical condition.

Referring to again the calculation unit calculates the standard condition reference value of the heart rate variation and feeds this reference value to the comparison unit . With this proceeding the user s normal level of heart rate variation is determined.

The initialization period is followed by an exercise period comprising exercise instructions deviating from the exercise instruction REST.

The exercise instruction of the first period 6 of the exercise period may be FREE in which case the user can freely select the level of the exercise according to how he she feels.

In one embodiment the instruction determination unit generates a lightened exercise instruction relative to the preceding exercise and exercise instruction if the standard condition value of the heart rate variation of the period is below the standard condition reference value of the heart rate variation. The low value of the standard condition heart rate variation may be interpreted as resulting from the exertion caused by the preceding period or periods so that a lightened exercise instruction such as REST LIGHT EXERCISE or MEDIUM HEAVY EXERCISE in relation to the exercise or exercise instruction of the preceding period may now be determined as the exercise instruction.

Still referring to period 7 is examined as an example where the standard condition value of the heart rate variation is below the standard condition reference value of the heart rate variation. Thus the exercise instruction LIGHT EXERCISE for example may be generated for period 7.

In one embodiment the instruction determination unit generates an exercise instruction REST if the standard condition value of the heart rate variation is below the standard condition reference value of the heart rate variation for a predetermined period of time. The values of the standard condition heart rate variation of periods 7 and 8 are examined as examples both of these values being below the standard condition reference value of the heart rate variation. Thus the exercise instruction of period 8 is REST.

In one embodiment the exercise instruction represents an exercise toughened up in relation to the preceding exercise instruction or maintenance of the exercise instruction HEAVY EXERCISE if the standard condition value of the heart rate variation is above the standard condition reference value of the heart rate variation. An example of such a case is period 9 at the beginning of which an increased heart rate variation has been measured. Thus the exercise instruction of the period is HEAVY EXERCISE for instance.

In one embodiment the instruction determination unit generates an exercise instruction REST if the standard condition value of the heart rate variation is below the standard condition reference value of the heart rate variation in a period of time after a predetermined exercise instruction. An example of this is period 9 where the exercise instruction is HEAVY EXERCISE whereby a value of the standard condition heart rate variation that is lower than the standard condition reference value of the heart rate variation is measured in period 10 after period 9. Thus REST is generated as the exercise instruction for period 10.

In one embodiment the instruction determination unit generates a lightened exercise instruction in relation to the preceding exercise or exercise instruction if the standard condition value of the heart rate variation has a downward trend even if the standard condition value of the heart rate variation were above the standard condition reference value of the heart rate variation. As an example of this the standard condition values of the heart rate variation in periods 12 and 13 are examined both of the values being above the standard condition reference value of the heart rate variation. Thus the exercise instruction for period 13 is REST.

Each exercise instruction may be associated with a target variable measured with the performance monitor and characterizing the target of the exercise numerically. The target variable may be for example a target average heart rate target energy consumption or target time. The above exercise instructions may be associated with for example the target average heart rate as follows 

The association and the target average heart rates may be preprogrammed to the instruction determination unit .

In one embodiment the system comprises an exercise information storing unit PHISU for storing exercise history information measured with the performance monitor .

The heart rate measurement unit feeds measurement information such as values of a heart rate parameter to the exercise information storing unit which stores the measurement information as exercise history information. The exercise history information comprises measurement information and time information to be associated with the measurement information.

In one embodiment the exercise information storing unit feeds exercise history information to the instruction determination unit which generates exercise instruction information for at least one future exercise on the basis of the exercise history information.

The exercise history information may comprise for example average heart rate values obtained with different exercise instructions. Thus the instruction determination unit may set the user specific target average heart rates corresponding to different exercise instructions and change values of the target average heart rates associated with the exercise instructions when the user s performance changes during the exercise program. Thus the exercise instructions are adapted according to the user s physical condition.

In one embodiment the heart rate measurement unit is implemented by means of a heart rate transmitter . The heart rate parameter determination unit comparison unit instruction determination unit storing unit calculation unit and exercise information storing unit may be implemented with computer software executed in the processing unit of the central processing unit of the performance monitor and stored in the memory unit . The reminder means may be implemented with computer software executed in the processing unit of the central processing unit of the performance monitor and stored in the memory unit and with the interface . The reminder means may be based on sound indicator light and or vibration.

In one embodiment the heart rate measurement unit is implemented by means of the performance monitor . In this case the heart rate parameter determination unit comparison unit instruction determination unit storing unit calculation unit and or exercise information storing unit may be implemented with computer software executed in the central processing unit of the calculation system and stored in the memory unit . In this embodiment the exercise information signal transmitted by the performance monitor comprises heart rate information on the user s heart rate as well as other possible information such as time information on the ECG components or heart rate information.

In one embodiment the heart rate measurement unit and the heart rate parameter determination unit are implemented with the performance monitor . In this case the comparison unit and instruction determination unit may be implemented with computer software executed in the central processing unit of the calculation system and stored in the memory unit .

In one embodiment the heart rate measurement unit heart rate parameter determination unit and comparison unit are implemented with the performance monitor . In this case the instruction determination unit may be implemented with computer software executed in the central processing unit of the calculation system and stored in the memory unit .

In one embodiment the storing unit and calculation unit may be implemented with computer software executed in the central processing unit of the calculation system and stored in the memory unit .

In one embodiment the exercise information storing unit may be implemented with computer software executed in the central processing unit of the calculation system and stored in the memory unit .

It is to be noted that the exercise instruction tables and in are only suggestive and that determination of the exercise instructions on the basis of a standard condition heart rate parameter may be defined in a plurality of ways.

At the user is reminded by means of the user specific performance monitor of at least one of the following prevailing standard conditions preparing for standard conditions.

At the value of a standard condition heart rate parameter is determined in the user specific performance monitor by measuring the user s heart rate.

If at no standard condition reference value of the heart rate parameter is available several day specific values of the standard condition heart rate parameter are stored at and a standard condition reference value of the heart rate parameter is calculated at by using several day specific values of standard condition heart rate parameters.

At the standard condition value of the heart rate parameter and the standard condition reference value of the heart rate parameter are compared.

At exercise instruction information is generated for at least one future exercise on the basis of the comparison.

If at exercise history information is used when exercise instruction information is generated at exercise history information on the user s exercise measured with the user specific performance monitor is stored and at exercise instruction information is generated for said at least one future exercise on the basis of the exercise history information.

If at no exercise history information is used when exercise instruction information is generated exercise instruction information is generated at for said at least one future exercise on the basis of the comparison.

With reference to let us examine a computer process according to an embodiment of the invention which process is suitable for generating exercise instructions for a physical exercise.

At the value of a standard condition heart rate parameter is determined on the basis of the heart rate information.

At the value of the standard condition heart rate parameter and a standard condition reference value of the heart rate parameter are compared.

At exercise instruction information is generated for at least one future exercise on the basis of the comparison.

The computer process may be included in the coded instructions executed in the processing unit of the performance monitor and or in the central processing unit of the calculation system . The coded instructions may be stored in the memory unit of the performance monitor and or in the memory unit of the calculation system .

The coded instructions may be included in a computer software product and they may be transferred via a distribution means. The distribution means is for example an electric magnetic or optical distribution means. The distribution means may be a physical distribution means such as a memory unit an optical disc or a telecommunication signal.

Although the invention has been described above with reference to the example according to the attached drawings it will be obvious that it is not restricted thereto but may be modified in a plurality of ways within the scope of the attached claims.

