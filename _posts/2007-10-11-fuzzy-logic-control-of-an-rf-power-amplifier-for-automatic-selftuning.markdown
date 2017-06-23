---

title: Fuzzy logic control of an RF power amplifier for automatic self-tuning
abstract: Fuzzy logic is utilized to control an RF amplifier and associated tuner for continuous self-optimization and automatic load matching to at least double the battery life of a battery-powered transmitter.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08280323&OS=08280323&RS=08280323
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 08280323
owner_city: Nashua
owner_country: US
publication_date: 20071011
---
This Application claims rights under 35 USC 119 e from U.S. application Ser. No. 60 850 769 filed Oct. 11 2006 the contents of which are incorporated herein by reference.

This invention was made with United States Government support under Contract No. DAAB07 02 C P 632 awarded by the Department of the Army. The United States Government has certain rights in the application.

This invention relates to conservation of battery power and battery powered RF transmitters and more particularly to the utilization of fuzzy logic control of an RF power amplifier and associated tuner for continuous self optimization and automatic load matching thereby to double the battery life of the battery powered device.

Portable transceivers that include both commercial transceivers such as cell phones and military radios have been battery powered presently utilizing lithium battery technology to increase the time in which the battery powered RF device can operate.

Cell phones two way radios Bluetooth devices and any number of wireless communications units having power amplifiers draw battery power based on the function of the device.

Heretofore there has been no self adaptive configuration of the RF amplifiers as to for instance sense the environment and adapt the tuning associated with the final RF amplifier so that the amplifier is operating as efficiently as possible. It is of course desirable that the amplifier operate in a very linear operating region in terms of temperature and to minimize the standing wave ratio SWR . Thus for instance when an individual using a handheld wireless device stands in a doorway that has a metal frame the metal frame can detune the antenna or cause a significant mismatch in the impedance between the antenna input and the output of the RF amplifier.

Typically these wireless units are engineered without consideration of the changing environmental conditions in which they will operate and as a result do not operate as efficiently as possible. The result is undue battery drain when the environmental conditions change at the portable device.

As to cell phones power management capability is typically managed by the base station in which the power output is determined from the base station. In these cases there is no local tuning or other control of the cell phone RF amplifiers which is handled externally and not intelligently by the device itself. As will be appreciated the base station does not take into account any environmental factors such as temperature and changing SWR. Thus it is not the function of the base station to make any adjustments that would limit current drain so that the portable unit does not to run out of power.

While in the past RF transmitters have been provided with automatic antenna tuners they are large and expensive and while they can measure standing wave ratios they are not utilized in small handheld low cost systems. Also the response time of the commercially available automatic antenna tuners oftentimes exceeds several seconds which is not particularly effective in instantaneously optimizing the power amplifier antenna portion of the transceiver.

Moreover the algorithms utilized in automatic antenna tuners can take as many as 100 000 instructions. These sophisticated algorithms require large processors with the attendant latency and massive current consumption. Thus there is always a requirement that one conserve battery power to extend missions and one cannot conserve battery power utilizing large processors.

There is therefore a need to optimize the RF transmitting section of a transceiver or wireless device so as not to unnecessarily impact battery resources.

What is desirable is to be able to sense the operating conditions at the amplifier and to have a feedback path by which the amplifier and its tuning circuits can be adjusted so as to optimize the RF amplifier as its operation is altered or degraded by the environmental conditions in which it finds itself. Additionally it would be useful to be able to optimize the RF amplifier and its attendant circuitry in terms of any degradation due to circuit aging so that the RF amplifier portion of the portable device self adjusts to minimize current drain thus to extend battery life.

In short there is a requirement to automatically match an RF power amplifier to a load and to ensure that optimized power is delivered to a load whilst the RF amplifier or connection to the antenna degrades due to environmental conditions.

In order to optimize RF power amplifiers for use in battery powered devices in accordance with the subject invention fuzzy logic algorithms are used in a closed loop feedback circuit to apply continuous monitoring and self correction fine tuning for the RF power amplifier. This maintains the amplifier in a linear region. If substantial impedance mismatches occur between the amplifier and the antenna the amplifier operation goes non linear and can even oscillate drawing excessive power from the battery and severely limiting battery life. The subject system is useful not only for narrow band cellular systems but also for WiFi 802.11 transceivers spread spectrum systems and ultra wideband communications where the frequency rapidly shifts and the antenna tuning must follow.

It has been found that by utilizing fuzzy logic no more than 1 000 instructions and oftentimes as few as 100 instructions need be used which minimizes controller power requirements and also limits the optimizing cycle to microseconds.

In one embodiment the fuzzy logic algorithms are programmed on a single integrated circuit due to their simplicity such that standard low cost EPROM technology may be utilized. This eliminates the utilization of sophisticated digital signal processors often entailing Pentium processors as well as the massive amount of memory that is required.

In one embodiment output power and input frequency are sensed and a digital tuner is re tuned with the fuzzy logic algorithms controlling the amplifier and the tuner to maintain an impedance match between the amplifier and the antenna and to adjust amplifier gain. By monitoring output power and comparing it to an idealized output power when the output power changes adjustments can be quickly made.

It is noted that with respect to cell phones there is nothing at the cellular telephone that monitors environmental conditions much less any feedback network to optimize the cellular phone handset operation.

As part of the subject invention not only is the tuning of the amplifier monitored by monitoring output power one also can adjust the bias of the amplifier which changes the gain of the amplifier. If there is a substantial mismatch between the output impedance of the amplifier and the input impedance of the antenna then by adjusting down the gain of the amplifier the standing wave ratio mismatch can be minimized.

As mentioned above the use of fuzzy logic is critical to the rapid and low current drain operation of the subject system. It is noted that due to the limited number of instructions necessary in a fuzzy logic algorithm one can place the algorithm on a single chip without the use of external components. If one has 100 instructions to tune the associated RF amplifier and the clock rate of the microcontroller executing the instruction is 1 MHz even with a slow processor one can use the 100 instructions to do an overall tuning operation in the millisecond range. Thus one can use an extremely slow computer chip embedded controller running at 1 MHz. In summary with only 100 to 1 000 instructions even with a 1 MHz clock one achieves millisecond cycle times.

The primary motivation for using fuzzy logic is that it does not have to have an absolute deterministic value. For instance a rule table can be set up by an expert that specifies that if certain sensed parameters are in a certain range change the tuner state to a predetermined state that results in a better match. Fuzzy logic thus deals in ranges as opposed to absolute values. Moreover fuzzy logic because it groups data into ranges operates on a much reduced data set with the fuzzy logic making a decision when the result using this reduced data set is good enough or close enough. Thus if the result is between 90 and 95 close to the ideal then this type of operation is sufficient at least in the subject case to save as much as five times on the battery drain by optimizing the RF amplifier antenna circuit.

While military radios have been designed for optimized battery life up to the present time there has been no attention to optimizing the RF section of the transceiver or transmitter on the fly. While at the design phase of these wireless devices optimization techniques are used environmental degradation can cause a significant mismatch and degradation of the operation of the amplifier so that it operates outside of its linear region. If one were able to re tune the amplifier and or set its gain parameters appropriately one could multiply the battery life by at least two times and as much as five times.

The external factors affecting the transmit scenario relate in part to the problem of an antenna being placed next to a metal structure inside of a building or even out in the open. Environmentally induced detuning can result in antenna gain changes. For instance if an antenna is optimized for a 3 dB gain in an ideal environment if suddenly a soldier stands under a metal door frame and is talking on the wireless device the antenna now for instance may be one inch away from the metal frame. Thus the antenna gain may go down to 2 dB or may even go to zero. A drop of 1 dB can cost at least half the power. Since portable wireless devices are meant to be moved around non optimal operation if detected can result in the opportunity to optimize of the RF amplification section of the transceiver.

The use of fuzzy logic algorithms provides an architecture that is expandable. For instance while in the subject example one senses output power and input frequency one could provide the fuzzy logic with any number of different sensors. One could be monitoring temperature as well as the lifetime of the device in addition to power and frequency. For instance if one knows the slope of the amplifier changes one could optimize the amplifier to counteract these changes.

In fact fuzzy logic is so simple that by just adding ten lines of code one can monitor an additional sensor and include the result in the feedback network.

The result is that low cost radios can be placed in the hands of soldiers in a platoon where the design goal would be a 24 to 48 hour mission. For instance if the soldiers are going out on a convoy one would like to have the battery outlast the planned mission.

In one embodiment of the subject invention sensed parameters are used by the fuzzy logic to control an antenna tuner with an initial setup resulting in a set of ideal impedance points on the Smith Chart describing an acceptable 1 1 SWR antenna match. Thereafter new sensed parameters result in different impedance points on the Smith Chart. The distance between the new Smith Chart points and those in the ideal set is ascertained. The fuzzy logic through its rules and based on this error signal generates a digital tuner control signal to reconfigure the tuner to reduce the error. In a next iteration new sensed parameters result in a new error signal used to control the amplifier tuner. This results in a new Smith Chart position. If this new Smith Chart position is sufficiently close to the ideal position the process is stopped. If not a fine tuning algorithm is invoked.

When the resulting Smith Chart position is close enough to an idealized set of Smith Chart positions the amplifier operates in a linear region. If the SWR becomes too high the amplifier can operate in a non linear and even oscillating region which draws excessive power.

If the transceiver is a frequency or band hopping radio keeping the SWR under control is a problem especially for spread spectrum military radios or ultra wideband devices. While cell phones are narrow band devices WiFi transmitters can also operate in wideband. In all of these cases maintaining the RF final amplifiers in a linear range is problematic.

Thus in the subject system after initialization a Smith Chart position is detected based on measured data. The fuzzy logic algorithm then establishes what actions are necessary to drive the Smith chart position to the area or region of the Smith chart that is close to the desired 1 1 SWR.

For instance if the antenna is designed to have a 50 Ohm input impedance and the output of the amplifier is designed to have an output impedance of 50 Ohms then there is a position or area on the Smith chart that corresponds to this.

When environmental factors change the antenna input impedance or the RF amplifier output impedance then these conditions are sensed and the position on the resulting Smith Chart position is detected. The distance between the point determined by these conditions and the optimal 1 1 SWR point on the Smith chart is detected and feedback signals are applied to either the tuning apparatus for the amplifier or to control the gain of the amplifier to drive this point towards the desired 1 1 SWR point on the Smith chart.

It has been found that only three such tuning cycles are needed in order to place the RF amplifier antenna circuit at a relatively optimal point which can be done with as few as 100 lines of code and in milliseconds.

In order to do so the fuzzy logic sets are set up using a series of definitions called membership functions to which variables are assigned. The membership functions are then put in the fuzzy logic sets which are stored in memory.

When the radio is turned on these sets are pulled out of memory and are loaded to set up the tuner. Thereafter the fuzzy logic algorithm is run to initialize the system which means selecting initial tuner states.

Thereafter power and frequency measurements are made to ascertain output power error the magnitude of which forms an error signal.

As a result of the three iterations in the above example one has tuned the amplifier tuner circuit to its optimum point assuring amplifier linearity.

If after the first three iterations as mentioned above there is no satisfactory movement of the Smith chart point then one drops into a fine tune mode. In order to prevent oscillation or non convergence in the fine tune mode the number of tuning steps in the fine tune mode is limited to a maximum number of iterations.

Put another way given a particular tuner the tuner can take on many different tuning states that result in various points on the Smith Chart. Taking for instance ten tuning states this means the tuner can take on ten different configurations. It is the purpose of the fuzzy logic algorithm to pick the tuning state that makes the amplifier operate in a linear region. How the algorithm does this is as follows 

Initially one establishes an initial tuning state that is the ideal or benchmark that provides linear amplifier performance i.e. corresponds to a 1 1 SWR. One then has in the above example nine other tuning states which gives nine different Smith Chart points or results. The distance from each of these points to the ideal point is described by a weight that is assigned to the corresponding tuning state.

In one embodiment the microprocessor is pre loaded with the ten tuning states and their corresponding weights.

The initial ideal tuning state corresponds to a 1 1 SWR for a given frequency input to the RF power amplifier.

Then one turns on the transceiver and measures the output power and input frequency. From the absolute magnitudes of these two measurements the distance of the corresponding Smith Chart tuning state point to the ideal point is determined in terms of a weight. The fuzzy logic using weights then computes a tuning state that will result in a Smith Chart point closer to the ideal point and the tuner is set accordingly.

After selecting this new tuning state the transceiver potentially outputs a different output power and or different frequency. The different power and different frequency are compared against the initialized values to derive another error signal corresponding to a weight which is used to pick a new tuning state.

The magnitude of the error signal is used to pick a tuning state that will result in a decrease in the distance between the point on the Smith Chart previously obtained and the ideal point.

In essence the fuzzy logic is utilized to pick the tuning state that results in a Smith Chart point that is closer to the ideal Smith Chart tuning state point.

Instead of having only ten tuning states which are not enough to cover the Smith Chart in one embodiment the tuner is designed to have 2 048 tuning states which results in enough points to cover the Smith Chart.

However fuzzy logic cannot efficiently handle 2 048 tuning states. What is required is a reduced data set and this is accomplished by grouping these 2 048 tuning states in one embodiment into five sets to be able to more quickly handle the data.

However fuzzy logic efficiently handles 2 048 tuning states by grouping large amounts of data into sets. This reduced data set is accomplished by grouping these 2 048 tuning states in one embodiment into five sets for the fuzzy logic algorithms to be able to more quickly process the data.

Thus for five sets there are approximately 400 different tuning states in a set each with a different weight.

How the sets are formed will be described hereinafter. Note that each set is designed so that tuning states that have similar characteristics are grouped in a set. In setting up the sets an expert designates five representative tuning states and thus five weights per set. These representative tuning states may be selected to correspond to Smith Chart points at the center up down left and right in the Smith Chart area corresponding to the set.

Thereafter and within each set there is a root mean square average weight for the five selected weights for the set. This root mean square average is compared to the magnitude of the error signal and the tuning state corresponding to the root mean square average that results in a closer Smith Chart point is selected for controlling the tuner.

Thus the root mean square average of five representative weights is used to make a decision as to how to tune the tuner.

By way of example in order to specify the tuning states a technician would take a given tuner and measure the Smith Chart point for each of the tuning states with the results loaded in memory.

How the tuning states are grouped into sets is basically determined by an expert who must know fuzzy logic at least to make a rough good set of data specifying each of the sets so that like tuning states are grouped together in a set.

Assuming a digitally controlled tuner for instance having 8 bit control the technician could designate 0 0 0 0 0 0 0 0 as being Tuning State 1. Tuning State 2 might be 0 0 0 0 0 0 0 1. The technician would then sequence from Tuning State 2 up to Tuning State 400 and designate this as the first set.

While this may sound arbitrary because one is using a particular digitally controlled tuner by selecting sequential numbers one identifies tuner states having closely similar characteristics.

The above process corresponds to coarse tuner control and the result after these iterations may be close enough to let the tuner remain unchanged.

It has been found that in the above example it takes only three iterations to select a tuner state to obtain close to a 1 1 SWR so that the amplifier operates in its linear region. This in turn minimizes battery drain and can extend battery life five fold.

While the above has described the tuner control it is also possible with the above fuzzy logic to control amplifier biasing and thus gain again to minimize SWR. Also a number of parameters other than input frequency and output power such as temperature and circuit aging can be used to maintain linear operation of the amplifier.

In summary fuzzy logic is utilized to control an RF amplifier and associated tuner for continuous self optimization and automatic load matching to at least double the battery life of a battery powered transmitter.

Referring now to an RF power amplifier is coupled to a suitable tuner which in one embodiment for microwave frequencies is a double stub tuner that is digitally controlled. An output power sensor is located adjacent the RF output of tuner to provide a measure of the output power that will be delivered to an antenna .

Also provided as an input to the subject system is a frequency discriminator that measures the frequency of an RF input signal at RF input .

These two measured quantities namely the input frequency and the output power are coupled to a fuzzy logic control circuit which provides for digital control of tuner over line .

Additionally RF input power is measured at and is applied to a gain control algorithm in unit that controls the bias for power amplifier .

While a separate control loop may be provided for gain control of the RF amplifier in a further embodiment of the subject invention amplifier gain may be controlled by fuzzy logic control circuit operating under an appropriate rule set to lower the amplifier gain in the presence of a large SWR mismatch between the amplifier and the antenna. This control is indicated by reference character on a line between the control circuit and the amplifier.

In short one has analog circuits that provide a signal to RF input terminal with the fuzzy logic control algorithm in control circuit providing intelligent control for auto tuning to be able to match the amplifier output impedance to the antenna input impedance.

Referring now to as described in combined Smith Chart the combined amplifier tuner response that experts say will provide the most linear operation of the amplifier is shown at to be positioned for instance slightly above the 50 Ohm impedance and slightly to the right of dead center.

In one embodiment the digitally controlled double stub tuner has 2 048 states with the corresponding impedance points of the tuner states shown in Smith Chart . Thus for each frequency there are 2 048 possible tuner states with the pattern on Smith Chart varying depending on the input frequency.

As mentioned hereinbefore fuzzy logic eschews the utilization of so much data and the 2 048 possible tuner states are divided up into five sets. The ideal set here shown at is that which results in a minimum impedance mismatch between the amplifier and the antenna of . This set is labeled Set in the diagram.

Other tuning sets are as illustrated and contain impedance points that are the result of closely related tuner states.

Referring specifically to Set Number it will be appreciated that each of the impedance points is given a weight depending on how far the point is to Set . This weight is a vector having both a magnitude and a direction.

Referring to impedance point in Set its distance and direction to Set in accordance with its assigned weight will be larger or more bad whereas for impedance point the distance and thus the weight assigned to this point is more good. 

Due to the use of fuzzy logic with impedance points grouped in sets as indicated above the average point in a set is determined by the root mean square average of all the points in the set. It is from this average point that distance to the ideal set is measured.

As will be discussed the measurement of output power and input frequency relative to an initialized set of values allows one to derive a weight vector such that having derived the weight vector one can generate a digital control signal applied to the tuner to tune the tuner to a point that will result in an impedance point on the Smith Chart that is closer to the ideal set.

Rather than processing data for 2 048 possible double stub tuner states one infers from the measured data how to go from a point within an outlying set to the ideal set. The weight for so doing is converted into a tuner state that minimizes the weight.

All of this is accomplished through a fuzzy logic control system impedance matching algorithm. In this algorithm sensor inputs are received by the system and evaluated. The antecedent if x and y blocks test the inputs and produce conclusions. The subsequent then z blocks of some rules are satisfied while others are not. The conclusions are combined to form logical sums. The conclusions are then fed into the inference process where each response output member function s firing strength 0 to 1 is determined.

Prior to discussing the operation of the system described in the way that the fuzzy logic operates is that it works in sets. In the most general sense one set is the universe. It is all of the possibilities that one could have for the tuner.

Then as described above there is an ideal tuning solution in the form of an ideal set. The way that the fuzzy logic works is by making a decision as it tries to solve how far away one is from where one wants to go namely the ideal tuning set.

The way the system works is to make a measurement of how far the sensed data is from the optimum data. In a series of measurements one knows when the weight derived is closer or not so close to the weights associated with the ideal set.

If the algorithm taking the measured data knows that the weight is too great then for the next iteration the tuning must go in a different direction to minimize the magnitude of the error signal.

In the intelligent transmitter two inputs actual power and actual frequency are continuously monitored and compared to the desired power output level and a reference frequency. The evaluation of these two inputs establish error signals. The magnitude of each error signal is based upon the logical rule set established in the algorithm. For example if the amount to tune is small then the magnitude of the error is small. Conversely if the amount to tune is large then a large error signal will be generated. The logical evaluation of the inputs and the generation of the error signal or signals is executed by a Boolean superset called fuzzy logic. Basically the fuzzy logic evaluates all sensor inputs that are received by the system concurrently. The antecedent If X and blocks test the inputs and produce conclusions. The subsequent Then Z blocks of some rules are satisfied while others are not. The conclusions are combined to form logical sums. Therefore the algorithm constantly monitors the system and always makes a decision to tune or not. Implemented in code this results in very fast adaptation times.

The fuzzy logic algorithm uses fuzzy reasoning to model the system characteristics. Lotfi A. Zadeh introduced the concept of fuzzy logic in 1965 as is disclosed in L. Zadeh Fuzzy Sets Informat. Conf. Vol. 8 pp. 338 353 1965 the contents of which are incorporated herein by reference. This work emphasized that humans are better at control than conventional controllers because they make effective decisions on the basis of imprecise linguistic information. His proposition was using a Boolean superset i.e. a degree of possibilities in between a logical true and a logical false that he termed fuzzy logic. Applied to the control of various systems fuzzy logic describes the system behavior based upon our knowledge of the system. Complex or simple relationships between system variables are characterized no matter what their analytical dependence. This is performed by a rule set in the form of IF a set of conditions is satisfied then a set of conclusions is inferred as disclosed in P. Branco J. Dente An experiment in automatic modeling an electrical drive system using fuzzy logic IEEE Transactions on Systems Man and Cybernetics Vol. 28 Part C No. 2 May 1998 the contents of which are incorporated herein by reference. This is depicted in the following equation is and is . . . and is then is

The symbol R 1 l c corresponds to the lth model rule among a total of c rules xj 1 j m is the m chosen system variable expressing the system condition y is the system output variable and is the inferred value from the fuzzy model.

The conclusions of the fuzzy logic evaluation are fed into the inference process where each response output member function s firing strength or truth level 0 to 1 is determined. This process by which the inference engine computes this uses the error signal magnitude to select a tuning range. In other words the membership functions will contain the optimized tune for the system and it is the job of the inference engine to make the tuning decisions. The equation for the membership function is as follows 1 . . . In each rule A is the fuzzy set linguistic term and is characterized by a membership function Finally the fuzzy set Brepresents the conclusion part of the rule.

A weighting system is applied to the membership functions in order to assign a ratio of true and false association to each decision. For example if the decision is arrived at that is exactly between two tuning ranges then one weight factor assignment could be 50 true or 50 false. However the system is trained such that previous lessons learned indicate that a 70 true and a 30 false weight is more desirable. This inference process is depicted as the following 

This section will describe the application of the algorithm for autonomous control of the amplifier tuner circuit. Referring now to this figure shows the architecture of the amplifier control system called herein the intelligent transmitter.

As described earlier the inputs to the fuzzy controller here shown at are input frequency and output power .

A power input sensor is used to adjust gain to keep the input to the power amp in the optimum range. Furthermore both the power output sensor and the frequency input sensor are monitored and used to adjust the impedance matching network for best power added efficiency PAE .

Referring now to the actual output power is measured as whereas the actual input frequency is measured at .

The desired output power is illustrated at and it is to this desired output power that the actual detected power is compared. These two powers are placed into a summing junction which in accordance with the rules m provides an output power error signal on line .

Likewise the actual input frequency at is compared to a reference frequency with these two signals provided to a summing junction again provided with rules to provide a frequency error signal applied to line . These two error signals are applied to a coarse tune unit comprised of Degree of fuzziness Membership Unit and Input Weight unit the combined outputs of which at determine a weight vector that is converted into a digital tuner tuning signal.

While the subject system in essence utilizes two tuning steps namely a coarse tuning step and a fine tuning step what is described now is the coarse tune in which the tuning states are grouped into sets depending on what the error is. The coarse tuning apparatus goes through a process to see if the error gets better or worse and if the result is within the desired range then that signal from element is used in the tuning process.

It will be appreciated that the coarse tuning section of the subject system is composed of Degree of fuzziness Membership Block and Input Weights Block with process respectively the output power error signal and the input frequency error signal.

With respect to the Degree of fuzziness Membership Block the power error signal and the frequency error signal are coupled to respective blocks and the function of which is to generate a result corresponding to the root mean square of the error signal coupled at its input. The root mean square function s purpose is to ascertain how far one is from the desired power or frequency. Once the Degree of fuzziness Membership calculation is made its output signal is applied to the appropriate P factor block respectively and in Input Weights Block the purpose of which is to generate a weight. The weight is used to define what tuning state the tuner of is to take on.

Thus coarse tune unit using fuzzy logic ascertains how far the sensed values of power and frequency are from the ideal values that would result in a 1 1 SWR and generates a weight having both a magnitude and a direction. The sum of these weights constitutes an output that is used to generate a digital code for the control of the tuner of .

Since the system operates on root mean square average to describe the distance between a set of tuning states to a set corresponding to the ideal tuning state this weight is used to feed back a signal to re tune the tuner.

In short 1 max PE is an error ratio with the magnitude of the ratio determining whether the present setting of the tuner is good or bad. If it is good one proceeds to the final tuning step. If not the system performs another iteration.

With the coarse tuning one wishes to start with an impedance point that is a large distance away from the ideal impedance point. So one purposely picks an impedance point that is further away to start out with.

What is done by the P factor blocks and is as follows. Having determined from blocks and whether or not the ratio is bad or good these blocks calculate weight vectors with these weights being used to derive digital control signals to re tune the tuner.

Note that g is the total number of inputs m is a rule and is the product. Y here shown at is the output weight that is used to define the digital signal to the tuner.

The rules m established at are arbitrary. What one does is to pick a point on the Smith Chart that is far away that is to say at the extreme side of the Smith Chart. The rule m then says to pick a point on the Smith Chart which could be for instance halfway to the ideal Smith Chart value. Thus one rule would be to always pick as a first step a halfway point or halfway weight between the measured point and the ideal point.

One could arbitrarily choose that the first point be in the capacitive region on the Smith Chart or one could also pick a point that is in the inductive region.

Referring now to and the initialization procedure to start and as illustrated at one powers up the transmitter at from which the gain of the amplifier is adjusted at and the tuner is adjusted at . These are adjusted utilizing a knowledge base with all of the information merged at and placed into an initializer which consists of a table or tables with different setup conditions.

After having set up the gain for the amplifier and the tuner state one applies a test tone at to the amplifier and measures the output power from the output power measuring point as illustrated at . The output power is compared to the initialization or ideal output power as illustrated at and if the output power matches the initial output power specified as illustrated at one moves into the Operation Mode as illustrated at .

If not another iteration or fine tune is performed at with a measurement then seeking to ascertain if after the fine tuning the output power matches the initialization output power as illustrated at . If so one enters the Operation Mode . If not one makes a determination at as to whether the initialized value of P out is good enough. If so the system is updated at with the knowledge base likewise being updated to indicate what parameters are considered sufficiently good. A status report is generated at and one again enters the Operation Mode . If the output power after final fine tuning is not good enough then the process is stopped as illustrated at and an error report is generated as illustrated at .

What is accomplished by the aforementioned initialization is to set up initial conditions for the particular amplifier and the particular tuner so that the linearity of the amplifier and or the mismatch between the amplifier and the antenna can be measured and an appropriate error signal generated as described in .

More particularly in order to establish the ability to learn or to adapt to new operating parameters the following premise is established to enable a learning capability. The system must be initialized upon power up and put into known states for starting conditions. In other words how can the system learn if it does not know what to base new information on as a point of comparison Part of the learning experience has to include some sort of memory function to assess changes over time or perhaps to predict a degradation of performance. The determination of these states is adaptable based upon knowledge gained or learned during operation. The system employs a mechanism to merge the knowledge gained in operation to the initialization settings. Therefore the system has memory for future functionality and decision making. The power up initialization uses calibration to verify operational parameters. The frequency in one embodiment is normalized at 12 GHz for the sole purpose of extracting logic rules for the system with maximum output power retained in the knowledge base of the system. The actual maximum power out will be ascertained if any changes occur in the system.

As mentioned above the flow chart begins with power up which means that only system power is applied but no input signal. The starting gain adjustments are fetched from an Initial Settings function and applied to a segmented gate amplifier SGA for the known magnitude and frequency of the test tone. Concurrently the impedance transformer is also tuned to its initial settings from the same function. The test tone is applied and Pis measured. Pis then compared to P initialization setting and if they are equal the system is ready for operational mode. However if P P then the system enters into the fuzzy logic control algorithm to fine tune. At this point again Pis measured. If P Pbased upon this new tune then the system is ready for operational mode and the new tuning parameters are input in to the knowledge file. In one embodiment the new tuning parameters are time stamped in order for the knowledge function to keep track of system changes over time. If however P P then the system could not reach its previous optimized tune and this means that some circuit level parameters have changed drastically. Then the system is at a critical junction. Is Pgood enough will be determined by a preset in the initialization file. If it is deemed that Pis indeed good enough then the system enters operation mode and subsequently the knowledge file is updated and as an option a status report is issued to the system.

As discussed previously the intelligent transmitter uses an expert based knowledge system with a fuzzy logic kernel control algorithm. The control of the transmitter is rule based meaning that the control is based upon an expert s knowledge of how to tune the system. The rules can be quite comprehensive to render expert control of the system to a high degree of accuracy. As a general tenet rule based systems are structured systematic repeatable predictable and code efficient. Therefore if indeed the algorithm were based upon our knowledge of the system then the question is begged how would a human tune the subject transceiver illustrates the tuning issues.

The Smith Chart response in one embodiment is shown for a non uniform distributed power amplifier NDPA which is the power amplifier in the transmitter. The response is slightly inductive. As a point of discussion a look up table could be employed containing the complex conjugate for every point of the power output. However there are several drawbacks with a look up table. First of all for the 11 bit tuner there would be 2048 states. Computation time required to compare all the states would be significant slowing the response down. Further 2048 states imply a one dimensional or a one input system. To evaluate more than one input requires an n dimensional table resulting in n factor more states to evaluate. Perhaps the most compelling argument against a look up table is that there is no provision for a decision making process. And finally if the circuit parameters change over time the look up table does not provide a mechanism for adaptability. In other words the values stored in the look up table become invalid.

In the case of a rule based system one of the rules will be if the Frequency is x and the Power is y then tune z. This means that the rules will select the optimum frequency range and adjust the tuner. For the Smith chart shown in this will result in the selection of the optimum result in the maximum P. Since the response of the amplifier is slightly inductive with the real part being close to 50 ohms the tuning solution set is established for that particular frequency set that is slightly capacitive to bring the imaginary part close to zero.

Note the transmitter is in operational mode at the completion of the initialization phase. It is shown in the diagram that a digital feed forward algorithm will be used for gain adjust. Thus stated the remainder of this discussion will illustrate the flow chart of the control algorithm. The system continuously monitors Pand F power output and frequency input and compares those values to those known values in the initialization file even though these values may have been updated from the knowledge function . A rule set allows the monitoring of the entire bandwidth from 6 to 18 GHz. Therefore if the frequency were to change the frequency discriminator will sense the change in frequency and the algorithm will scan all the rules that apply to frequency behavior simultaneously.

In the operational mode of the transmitter as can be seen at the process is started simultaneously monitoring the input power at monitor the output power at monitor and the output frequency at . With respect to the input power control the monitored input power is compared with the input power in the initialization procedure as illustrated at . If these two entities are not equal the amplifier is adjusted at and the result is measured. If the result shows that the input power equals the initialized input power as determined at then there is no further gain adjustment. If they are not equal adjustment is attempted.

With respect to the monitoring of the output power as far as the impedance matching algorithm is concerned the monitored output power is compared at to the initialized output power and if they are the same then the process stops.

If the output power does not equal the initialized output power then for the logical evaluation of all outputs box is called up. It is at this box where the fuzzy logic compares the sensed output power with the initialized output power.

The result of the evaluation or what could be a comparison step is coupled to an inference engine . It is here at the inference engine that the root mean square process is initiated to determine a weight corresponding to the error signals based on how bad the initial measured condition was. The inference engine then causes the tuner to re tune.

The output of the inference engine is applied to a decision engine . Also inputted into the decision engine is an input from knowledge base and a learned function the purpose of which is to derive a smarter tuning scenario.

For instance if one tunes nine times if every time the transceiver is turned on it goes through this process and knows where a good tune is then the process is placed in the memory and the results can be used at the output of the inference engine to effectuate a good tune.

As a result the output of the inference engine is used to generate the digital code that is coupled to the tuner for re tuning.

Note that if the output of the decision engine results in the output power equaling the initial output power as illustrated at then no learning is indicated.

The same processing is true for the monitoring of the input frequency which is monitored at decision block and with knowledge base being updated through a learning process that assists the inference engine. Decision engine is again invoked by decision block to ascertain if the input frequency is the same as the initialized value. If not learning process is updated.

As can be seen from a decision table is used to determine what type of control signal is to be applied back to the tuner of . It is here that the fuzzy logic comes into play.

In the decision table which is an instantiation of a fuzzy logic rule set maps the decisions against the power and frequency errors in the system. The rules follow the fuzzy equations IF x and y Then z format described earlier. The rule Tune Zero will not be satisfied until maximum Pis achieved. The degree of frequency error is based on the initialization of the normalized 12 GHz response. When the frequency error is positive then the system will need to tune negative and conversely if the frequency error is positive then the system will tune negative to achieve the best response. It may seem oversimplified but this logical table covers the entire spectrum of input frequencies output power and possible responses. Even though the output is not exactly clear at this point this does form the basis of a fuzzy logic system. In the vernacular this is termed fuzzification and is the first step in the inference process. The next step in the inference process is computation of the logical values more than one may be valid even though in this example only one rule was legitimate and the application of fuzzy math to derive the membership functions meaning to select a solution set and solve.

Specifically from it can be seen if Fis negative and Pis zero then according to the tuner code one has a very small positive VPS correction. If Fis negative and Pis small then there is a positive small PS tuner code coupled to the tuner. If Fis negative and Pis medium then the tuner code PM indicates a medium positive shift for the tuner. If Fis negative and Pis high then one needs a positive high tuning shift PH.

The above discusses the case where Fis negative. Below on this table is discussed conditions where Fis either zero or positive with the indicated tuner codes indicated to shift the tuner in the presented manner.

How high is high or how low is small is based on rules set up by the expert and offers the type of imprecision afforded by the fuzzy logic.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

