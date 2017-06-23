---

title: Portable electronic device, method, and computer-readable medium for determining user's activity level
abstract: The invention relates to a portable electronic device, a method, and a computer software product. The portable electronic device comprises an active time unit for determining a user activity level during a predetermined period of time; and a processing unit for determining a user inactivity level during a predetermined period of time on the basis of the determined activity level.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08159353&OS=08159353&RS=08159353
owner: Polar Electro Oy
number: 08159353
owner_city: Kempele
owner_country: FI
publication_date: 20071218
---
This application claims priority based on Finnish patent application No. 20065828 filed Dec. 20 2006 which is incorporated herein by reference.

A day may be divided into three main parts rest sleep work and leisure time. The periods of time spent for leisure and work are mainly determined by external factors. The way each one of us spends his or her leisure time may be determined individually and this may also be influenced e.g. in an activating manner. Various environmental factors such as television DVD the Internet and games greatly add to an inactive manner of spending one s leisure time.

It is a well known fact that too much physical inactivity such as sitting and immobility increase health problems. Inactivity results in poor condition increased body weight and metabolic problems which in turn increase risks of several different diseases such as obesity coronary artery disease type 2 diabetes hypertension as well as disorders relating to muscles and bones. In physical inactivity sitting equals lying since both requires minimum muscular activity and both thus consume very little energy and present a metabolic need. According to recent research the most significant difference between slim persons and obese persons is that overweight persons sit on average two hours longer than slim ones. For example Levine et al. Interindividual Variation in Posture Allocation Possible Role in Human Obesity Science January 2005 Vol. 307 p. 584 to 586 discloses that controlling the amount of time spent by an individual sitting may have a considerable effect on weight and health management as well as on the individual s desire to achieve a more active lifestyle.

For instance the work of a typical office worker contains hardly any physical activity and further such a person daily spends sitting 6 to 7 hours in the office a total of 1 hour in the car commuting and 3 hours while watching television. The only activity of a typical workday is e.g. a forty minute walk before dinner. Thus a total of time spent sitting per workday is no less than 11 to 12 hours which considerably exceeds the recommended healthy amount.

An inactive non workday e.g. reading working on a computer minor domestic chores watching television contains 8 to 9 hours of sitting and only 3 hours of activity. Hence the time spent inactively exceeds the recommended amounts. An active non workday e.g. golfing shopping may contain 5 to 6 hours of sitting as well as an equal amount of activity. Consequently the time spent inactively remains at a recommended level i.e. below 7 hours.

The time spent inactively by a typical user may be e.g. 74 hours per week. This amount is well above the recommended weekly maximum inactivity values. All in all it may be stated that more often than not the amount of time spent inactively such as sitting on workdays should be diminished in order to maintain a slim build and health.

People do not easily notice the amount of inactivity in their daily life. Therefore increasing the awareness of the amount of inactivity in an individual s daily life may be even more significant for health than monitoring the activity of the individual. Various devices for monitoring physical condition do not meet these needs.

An object of the invention is to provide a method and an apparatus implementing the method so as to enable the amount of inactivity to be estimated. As a first feature of the invention there is presented a portable electronic device comprising an active time unit for determining a user activity level during a predetermined period of time and a processing unit for determining a user inactivity level during a predetermined period of time on the basis of the determined activity level.

As a second feature of the invention there is presented a method comprising determining a user activity level during a predetermined period of time on the basis of a portable electronic device used by the user and determining a user inactivity level on the basis of the determined activity level.

As a third feature of the invention there is presented a computer software product comprising encoded instructions for executing a computer process in a digital processor. The computer process comprises determining a user activity level during a predetermined period of time on the basis of data produced by a portable electronic device used by the user and determining a user inactivity level during a predetermined period of time on the basis of the determined activity level.

The invention is based on the invention comprising determining an inactivity level during a predetermined period of time on the basis of the determined activity level.

Several advantages are achieved by the method and system according to the invention. As an advantage the invention produces an objective estimation of user inactivity. It becomes possible to monitor a person s inactivity level e.g. on a daily weekly and or monthly basis. Furthermore it becomes easier to maintain the amount of personal activity within limits advantageous to health.

Referring to the example of a portable electronic device PED comprises a processing unit PU and a memory unit MEM . The processing unit comprises a digital processor and executes a computer process in accordance with encoded instructions stored in the memory unit .

The processing unit may be implemented using analog circuits ASICs Application Specific Integrated Circuit digital processor memory and computer software. The processing unit may constitute a part of the computer of the device . The processing unit may execute a computer process in accordance with encoded instructions stored in the memory unit .

The portable electronic device is e.g. a mobile telephone or a pedometer. In an embodiment the portable electronic device is a wrist device which may be e.g. a wrist device shown in . In addition to the wrist device the device may comprise one or more auxiliary devices such as a motion sensor to be attached to a limb of the user of the portable electronic device and or a heart rate transmitter indicating electric pulses induced by the heart. Such an auxiliary device may communicate wiredly or wirelessly with the wrist device . In this connection a user of the portable electronic device is called a user .

In an embodiment the portable electronic device comprises a wrist device and at least one auxiliary device . Instead of the wrist the portable electronic device may be freely placed also in other parts of the body and e.g. in a pocket on a piece of clothing footwear or accessories.

Still referring to the portable electronic device further comprises an active time unit A for determining a user activity level during a predetermined period of time. In an embodiment the active time unit comprises one or more motion detectors to generate motion data characterizing a local movement of the portable electronic device for determining an activity level.

Typically a local movement of the portable electronic device comprises movements of a limb or another part of the body of the user which includes a motion component associated with the user s stepping. The amplitude of such local movements is typically of the order of magnitude of the amplitude of movements of the user s limbs.

In an embodiment the active time unit comprises an acceleration sensor which measures acceleration associated with the user s movement. The acceleration sensor converts acceleration induced by motion or a gravitational force into an electric signal.

In an embodiment the acceleration sensor is based on piezo resistor technology using a material whose resistance changes when a piezo resistor is compressed as a result of acceleration of mass. When a constant current is applied through the piezo resistor a voltage acting over the piezo resistor changes according to the compression induced by the acceleration.

In an embodiment the acceleration sensor is based on piezo electric technology wherein a piezo electric sensor generates a charge upon accelerating the acceleration sensor. In silicon bridge technology a silicon chip is etched such that a silicon mass is left on the silicon chip at an end of a silicon beam. When the silicon chip is subjected to acceleration the silicon mass directs a force to the silicon beam whereby the resistance of the silicon beam changes.

The acceleration sensor may also be based on micro machined silicon technology which is based on using a differential capacitor. The acceleration sensor may also be based on voice coil technology which is based on the same principle as a microphone. Some examples of suitable motion sensors include Analog Devices ADXL105 Pewatron HW or VTI Technologies SCA series.

The acceleration sensor may also be based on other appropriate technologies e.g. a gyroscope integrated in a silicon chip a micro vibration switch arranged in a surface mountable component or a mechanical pendulum.

Motion data generated by the acceleration sensor may be conveyed to a central processing unit or a memory unit . The motion data may comprise e.g. acceleration data and or motion pulse data associated with the user s movements.

The active time unit may also be implemented by other appropriate technologies e.g. a gyroscope integrated in a silicon chip or a micro vibration switch arranged in a surface mountable component.

The active time unit may comprise a pre processing unit for processing primary motion data such as acceleration data and or vibration data. The processing may comprise converting the primary motion data into secondary motion data such as changing acceleration data associated with the movements generated by the user into motion pulse data. The processing may also comprise filtering the primary and or secondary motion data.

The portable electronic device may further comprise a user interface UI which typically includes a display unit DISP and a display controller. The display unit may include e.g. LCD Liquid Crystal Display components. The display unit may graphically and or digitally display to the user e.g. an instantaneous activity level and inactivity level during a predetermined period of time.

The user interface may also comprise a keypad KP to enable the user to enter commands into the device . The user interface may also include an indicator to enable the device to impart voice signals vibration based signals and or light based signals.

In an embodiment the wrist device is a heart rate monitor in which case the heart rate monitor may comprise a receiver for receiving a signal transmitted from a heart rate measurement unit. The heart rate measurement unit may be a belt like construction to be mounted on the user s chest comprising means for carrying out electrocardiography ECG and transmitting ECG data to the wrist device .

In an embodiment the active time unit determines a user activity level during a predetermined period of time and the processing unit determines a user inactivity level during a predetermined period of time on the basis of the activity level determined in the active time unit .

In an embodiment the active time unit is configured to add up periods of time during which an instantaneous motion intensity value meets predetermined activity conditions.

In an embodiment the active time unit comprises at least one activity sensor for measuring a user activity level and the processing unit is configured to use the measured activity level in determining an inactivity level.

In an embodiment at least one activity sensor is configured to measure muscular activity of a user in which case the processing unit may determine an inactivity level during a particular period of time on the basis of the measured muscular activity.

In an embodiment at least one activity sensor is configured to measure heart rate of a user in which case the processing unit may determine an inactivity level during a particular period of time on the basis of the measured heart rate pulses. For instance an inactivity level during a particular period of time may be determined on the basis of variations in a personal heart rate.

In an embodiment the active time unit comprises at least one acceleration sensor for measuring acceleration from movement of the device when the user is moving and the processing unit is configured to use the measured acceleration in determining an inactivity level.

Thus measurement results describing the movement muscular activity and or heart rate of the user or combinations thereof may be used in determining the inactivity level.

In an embodiment the processing unit is configured to detect reaching at least one predetermined threshold value in the determined inactivity level. In an embodiment the predetermined threshold value is an optimal inactivity level during a predetermined period of time. In an embodiment the determined threshold value is a maximum inactivity level during a predetermined period of time. The optimal inactivity level is e.g. an optimal level of inactivity allowed during a day which is not advisable to be exceeded. The maximum inactivity level is e.g. a maximum level of inactivity allowed during some hours or during a day exceeding which is to be avoided.

In an embodiment the indicator indicates the determined inactivity level. In an embodiment the indicator is configured to indicate reaching at least one predetermined threshold level in the inactivity level. The indicator may indicate e.g. reaching exceeding the optimal inactivity level and or reaching exceeding the maximum inactivity level.

Referring to the example of let us examine a motion intensity curve showing a time dependency of an instantaneous motion intensity value of the user . A horizontal axis shows time expressed in a time unit such as minute while a vertical axis shows a motion intensity value expressed in a motion intensity unit such as pulse minute p min .

The motion intensity value characterizes the amount of movement of the user in a time unit. In an embodiment the motion intensity value characterizes the number of motion pulses per minute or another appropriate time unit. The activity level may be determined e.g. on the basis of the number of motion pulses.

An instantaneous motion intensity value is a motion intensity value calculated for a point of time. An instantaneous motion intensity value at a point of time may be determined e.g. by calculating motion pulses accumulated during a measurement time period such as a minute and dividing the number of motion pulses by the measurement time period. A point of time to be associated with the determined instantaneous motion intensity value may be e.g. a starting time or an end time of a measurement time period or a point of time halfway the measurement time period.

An active time accumulation is an accumulating time accumulation which includes added up periods of time during which the instantaneous motion intensity value meets predetermined activity criteria. In the example of a predetermined activity criterion is e.g. a motion intensity level designated in dotted line time periods meeting the activity criteria then being T T T T T and T. Thus in determining the activity level the user s very slight movement for example is not necessarily counted as activity.

In an embodiment the activity level is determined on the basis of an active time accumulation calculated for a previously known period of time which in the example of the figure may be a period of time between a starting time and an end time . In such a case the active time accumulation for the particular period of time is T T T T T T when the pre determined activity criterion is the motion intensity level . The periods or time may be implemented such that the periods overlap with one another. For instance let us examine 60 second time periods at intervals of e.g. ten seconds. Then to the 60 second time period are added at intervals of ten seconds instantaneous motion intensity values for the most recent ten seconds while simultaneously omitting motion intensity values for the least recent ten seconds.

The starting time may be 12 o clock at night or a point of time 24 hours preceding real time. The end time may be 12 o clock at night without however limiting the disclosed solution to the presented embodiment.

When the active time determination is in operation the end time may be a point of time in real time. In such a case the active time accumulation indicates an active time accumulation accumulated from the starting time to the point of time in real time.

In an embodiment the inactivity level is determined from an inactive time accumulation which includes added up periods of time during which the instantaneous motion intensity value meets predetermined inactivity criteria. A predetermined inactivity criterion is e.g. a predetermined motion intensity level which determines an upper limit of the instantaneous motion intensity value. The inactive time accumulation may be shown to the user by means of the display unit .

In the example of the predetermined inactivity criterion is e.g. a motion intensity level designated in dotted line time periods meeting the inactivity criteria then being T T T T T T and T. The inactive time accumulation for the period of time between the starting time and the end time is thus T T T T T T T.

In an embodiment the portable electronic device divides the instantaneous motion intensity values into at least two activity categories based on predetermined threshold values and the active time accumulation is determined activity category specifically. The example of shows activity categories A B and C. Activity category C comprises motion intensity values residing between the motion intensity levels and activity category B comprises motion intensity values residing between the motion intensity levels and and activity category A comprises motion intensity values residing above the motion intensity level .

Activity category D comprises motion intensity values residing below the motion intensity level and activity category D may also be defined as an inactivity category.

The motion intensity levels and may be 2 p min 30 p min and 50 p min in the given order. Thus activity category D may be defined as rest activity category C may be defined as an extremely light activity category activity category B may be defined as a light activity category and activity category A may be defined as a moderate heavy activity category.

Referring to the example of let us examine a portable electronic device PED comprising a motion detector MD a motion intensity determinator MID and an active time calculator ATC .

The motion detector generates motion data characterizing a local movement of the portable electronic device and feeds the motion data to the motion intensity determinator . The motion intensity determinator determines instantaneous motion intensity values from the motion data .

In an embodiment the motion intensity determinator filters motion data on the basis of predetermined time characteristics. The motion intensity determinator may accept motion pulses meeting the pre determined criteria and use the accepted motion pulses for determining motion intensity values.

In an embodiment in determining a motion intensity value the motion intensity determinator uses motion pulses whose length of time intervals therebetween resides within predetermined limits. In such a case the determination of the motion intensity values concentrates on motion frequencies typical of a human body typically being 1 to 2 pulses per second. The filtering may be implemented by rejecting successive motion pulses whose time interval is below a predetermined lower limit or whose time interval is above a predetermined upper limit.

The predetermined upper and lower limits may depend on the location of the motion detector on the user s body. In the case of a motion detector attached to an upper limb the predetermined lower limit may be e.g. 0.4 seconds. The predetermined upper limit may be e.g. 2.0 seconds.

The motion intensity determinator may be implemented by means of a computer process to be executed in the central processing unit the computer process being encoded in encoded instructions to be stored in the memory unit .

In an embodiment the motion intensity determinator feeds the instantaneous motion intensity values to the active time calculator . The motion intensity determinator may also feed a point of time associated with each instantaneous motion intensity to the active time calculator. The active time calculator compares the motion intensity values with the predetermined motion intensity level and calculates the active time accumulation and possibly the inactive time accumulation on the basis of the comparison. Inactive time accumulation data may be incorporated in active time accumulation data .

In an embodiment the portable electronic device comprises a classifier CL which receives the motion intensity values from the motion intensity determinator and carries out a comparison between the motion intensity values and the motion intensity levels . On account of the comparison the classifier divides the instantaneous motion intensity values into intensity classes.

The active time calculator may be implemented by means of a computer process to be executed in the central processing unit the computer process being encoded in encoded instructions to be stored in the memory unit . The classifier may be implemented by means of a computer process to be executed in the central processing unit the computer process being encoded in encoded instructions to be stored in the memory unit . The inactive time accumulation may be shown to the user by means of the display unit .

In an embodiment the portable electronic device comprises an indicator ATI for indicating the inactive time accumulation and or active time accumulation preceding the period of time between the starting time and the end time to the user. The inactive and active time accumulations of previous e.g. day specific time periods may be stored in the memory unit and shown to the user by means of the display unit graphically or digitally. This enables the user to monitor his or her performance history and compare e.g. the inactive time accumulation of the ongoing time period with previous values.

In an embodiment the portable electric device comprises an intensity indicator II for indicating the point of time of the most recent motion intensity value meeting the activity criteria to the user . Referring to let us assume that the real time moment is a point of time and the activity criterion is determined by the motion intensity level . In such a case the most recent point of time of the motion intensity value meeting the activity criteria with respect to the point of time is a point of time . The central processing unit may feed the most recent point of time of the motion intensity value meeting the activity criteria to the memory unit to be stored therein. The display unit may indicate the memory space of the memory unit such that the contents of the memory are shown on the display unit . By detecting the most recent point of time of the motion intensity value meeting the activity criteria the user may conclude e.g. the length of ongoing inactive time . The display unit may e.g. show the text inactive since T T wherein T T is the point of time at which the activity criterion was met last.

In an embodiment the portable electric device may generate a performance instruction on the basis of an inactive time accumulation.

The active time calculator feeds active time accumulation data to a performance instruction generator which may compare the active time accumulation with reference values. The reference values may form ranges which are associated with performance instructions. A performance instruction may include an instruction REST WALK and LIGHT EXERCISE. For instance if the accumulation for the present day or previous 24 hours in activity categories A and B is less than 30 minutes the user may be given a performance instruction to increase his or her activity e.g. by exercising lightly or moderately. If the accumulation in activity category A is less than 30 minutes e.g. during the previous three days or during the previous 72 hours moderate heavy exercise may be determined as a performance instruction. The performance instruction may also be determined on the basis of a plurality of day specific active time accumulations. The performance instruction generator may be implemented by means of a computer process to be executed in the central processing unit the computer process being encoded in encoded instructions to be stored in the memory unit .

In an embodiment the device may comprise a game application GAPPL whose operation depends on one or more parameters proportional to an active time accumulation. In an embodiment the device may comprise a motion detector controller which receives inactive time accumulation data along with the active time accumulation data and compares the inactive time accumulation with a predetermined threshold value. If the threshold value is reached the motion detector controller through a mode shift command shifts the motion detector to a measurement mode wherein motion data is generated discontinuously at predetermined time intervals.

In the example of the user inactivity level is indicated by means of a SitControl function. The inactivity level is determined e.g. on the basis of inactive time spent by the user sitting and in a non active manner. The amount of accumulated inactive time as well as certain predetermined threshold values are indicated to the user visually and digitally to enable the accumulated inactive time to be compared with the threshold values visually. Furthermore the device may indicate reaching each threshold value separately e.g. by means of audible signals vibration or visually.

In ovals located on top of one another each describe an hour s time. Black ovals illustrate one hour time periods accumulated as a result of an activity e.g. sitting within the limits of an inactivity level. The graphic representation may include any symbols figures and graphs or combinations thereof other than those shown in the exemplary representation of . In the example of a SitLean threshold value which in this example is the optimal amount of inactivity per day has been reached. According to some research the SitLean threshold value is approximately seven hours. Remaining below this optimal threshold value supports a slim and healthy build and lifestyle. The example of also shows a SitMax threshold value which is the maximum allowable time to be spent inactively in order to maintain or achieve a slim build. According to research this maximum time is approximately nine hours per day. According to research slim persons do not constantly exceed this amount.

It is also possible to determine other threshold values meeting which triggers various functions. For instance reaching a particular threshold value may cause the device to alert the user to approach of critical threshold values or to the fact that the user has been inactive for a predetermined period of time.

When the user is able to concretely and visually monitor the time he or she has spent inactively the user s awareness of his or her inactivity level and the time spent inactively increases. This may in a practical manner guide the user towards a more active lifestyle and decrease the time spent e.g. sitting.

In an embodiment the following categories may be employed when estimating an inactivity level over 10 hours extremely high inactivity level 7 to 10 hours too high an inactivity level 5 to 7 hours high inactivity level 2 to 5 hours appropriate inactivity level and less than 2 hours inactivity presents no problem .

In an embodiment the inactivity level such as the amount of sitting may also be monitored on a weekly basis by determining e.g. 49 hours as the allowed maximum inactive time.

Referring to let us examine computer processes according to some embodiments of the invention shown by means of process steps. Such process steps may also be interpreted as method steps of a method.

In an inactivity level during a predetermined period of time is determined on the basis of the activity level.

In an inactive time accumulation including added up periods of time during which an instantaneous activity level meets predetermined inactivity criteria is determined.

The computer process shown in may be incorporated in a computer software product as encoded instructions which may be executed in a central processing unit of a portable electronic device . The encoded instructions may be stored in a memory unit of the portable electronic device .

The encoded instructions may be transferred by means of a distribution device. Such a distribution device is e.g. an electric magnetic or optical distribution device. The distribution device may be a physical distribution device such as a memory unit or an optical disk or a communications signal.

Although the invention has been described above with reference to the example according to the accompanying drawings it is apparent that the invention is not restricted thereto but may be modified in many ways within the scope of the appending claims.

