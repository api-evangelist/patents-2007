---

title: Wide bandwidth microwave balun
abstract: A wide bandwidth microwave balun utilizes frequency band splitting and two conventional baluns operating in a high frequency band and a low frequency band, which when combined offer a full bandwidth output, thus to offer wide bandwidth impedance matching and second-harmonic rejection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07557673&OS=07557673&RS=07557673
owner: BAE Systems Information and Electronics Systems Integration Inc.
number: 07557673
owner_city: Nashua
owner_country: US
publication_date: 20070308
---
This Application claims rights under 35 USC 119 e from U.S. Application Ser. No. 60 780 640 filed Mar. 9 2006 the contents of which are incorporated herein by reference.

This invention was made with United States Government support under a classified contract. The United States Government has certain rights in this invention.

This invention relates to microwave and RF circuits and more particularly to baluns used in such circuits.

An essential component in many microwave and RF circuits is the balanced to unbalanced transformer or balun. Balun applications include balanced mixers multipliers and amplifiers for cancellation of even order intermodulation products power amplifiers for push pull power combining and for the connection of naturally balanced antenna structures to unbalanced microwave components.

Low frequency baluns leverage ferrite and air coil transformer technology to achieve high performance and very broad bandwidth. However at microwave frequencies it becomes increasingly difficult to fabricate this class of balun and other techniques become necessary. Miniaturization of the balun to a size and planar form compatible with monolithic microwave integrated circuit MMIC fabrication further complicates the design and implementation of the balun.

Due to the unavailability of ferrite technology to provide for ultrawide bandwidth baluns there is a need to provide other types of technology to achieve a 10 1 frequency bandwidth such as between 2 Gigahertz and 20 Gigahertz. Uses for such wide bandwidth baluns include microwave surveillance applications where wideband frequency coverage is required to be able to detect the large variety of signals that pop up as well as to provide interface circuitry for wideband digital signals and wideband antenna structures.

In general in the basic operation of a balun balanced signals that come out of the balun from an unbalanced line input are equal in amplitude and 180 degrees opposite in phase. Thus for instance signals that come in on an unbalanced 50 Ohm line may be converted to signals applied to a balanced 300 Ohm line.

One of the main purposes of baluns other than for impedance matching is for the cancellation of second order distortion of which second harmonics is a part. As such such baluns can be used for balanced mixers so that when a signal comes into the single ended input of the mixer it comes out split into a different kind of signal.

The balun can be used with differential amplifiers or pairs of amplifiers that connect to an antenna with the balun being used for combining the output of the differential amplifier so that it does not lose half of its power into a termination.

While it is known to cancel second order distortion in the front ends of amplifiers and to do so in the microwave region of the electromagnetic spectrum the problem is that in an amplifier to cancel second harmonics the balun has to be operating from the lowest input frequency to twice the highest output frequency. Thus if one has an amplifier that operates for instance between 1 and 5 Gigahertz the balun would have to operate between 1 to 10 Gigahertz to cancel the second harmonics.

Note that harmonics and other non linearities in an amplifier create distortion in which harmonics constitute one form of distortion. Other forms of distortion can be intermodulation products and the mixing of two signals that creates spurious tones at the sum and difference frequencies. These are all second order products that need to be canceled. The cancellation of spurious tones using second harmonic cancellation is the operating province of balanced mixers that help to cancel these tones.

Moreover it is noted that in a receiver a receiver would have to be able to deal with every single spurious tone that would appear at the output of its pre amplifier. It is noted that in an amplifier of bandwidth greater than an octave the highest power distortion tones are usually the second order tones

The effect of such distortion can be seen as follows. If one is operating near a radio station and one happens to be listening to a weaker station further away the presence of the large signal from the nearby radio station can create spurious tones due to the above mentioned non linearities in an amplifier. This makes it virtually impossible or very difficult to receive the signal that one is interested in with good fidelity.

Priorly in order to reduce the second order distortion a brute force approach has been employed. By increasing the power handling capability of the amplifier it becomes more linear for a given signal level. Thus second order distortions were kept to a minimum by increasing the power handling capability of the amplifier and operating it at reduced input signal levels.

However this is not an acceptable approach especially in cases where one wants to use battery powered devices or if one wishes to have a number of these amplifiers located in a small space such as in a phased array.

While the technique of using a balun for second order distortion cancellation is a known technique there has been no ability to apply the balun to the kinds of frequency bandwidths that are required in signal intelligence applications because baluns do not typically have a 10 1 bandwidth ratio in the microwave region of the spectrum.

While it is possible in the HF region of the electromagnetic spectrum to broaden the bandwidth of the balun through the use of ferrites normal ferrites do not work at microwave frequencies. While in the past microwave ferrites have been developed they do not operate with a low enough loss to achieve the required bandwidths.

In order to provide a microwave balun with a 10 1 bandwidth in the subject invention one divides the incoming signal into high frequency and low frequency bands. One then utilizes two different baluns one with a low frequency band output and one with a high frequency band output with the outputs of these two baluns being combined to give a full bandwidth signal.

As a result when the outputs are combined one has retained the balun functionality over effectively twice the geometric bandwidth i.e. over the combined bandwidth of the constituent baluns.

In one embodiment two baluns and three diplexers are utilized. The diplexer functions as a filter device that has one input and two outputs. A signal coming into a diplexer at all the frequencies above the center frequencies will go out one path and all frequencies below the center frequency will go out another path. Thus one is able to split an incoming signal into a high frequency band and a low frequency band utilizing a diplexer.

Having split the incoming signal into two frequency bands one high and one low the low frequency band is fed to a low frequency balun and the high frequency band is coupled to a high frequency balun. Thereafter diplexer filters are used to combine the signals from the two baluns at the output for the full bandwidth response.

Note that the balun is a passive circuit that operates in either direction such that one can go from a balanced input to an unbalanced input and vice versa.

In operation the desired amplified signals at the balanced outputs of the amplifier are equal in amplitude are 180 degrees out of phase. In contrast unwanted or spurious signals such as second order intermodulation distortion signals are approximately in phase at the balanced output ports of the amplifier. Since the intermodulation distortion signals are in phase on both output ports of the amplifier ideally no current flows in the balun responsive to these signals. In this way the balun effectively suppresses or eliminates these signals to thereby provide a high level of rejection of the second order intermodulation distortion signals.

The net result is that by using a wide bandwidth microwave balun at an appropriate point in a circuit second order distortions can be canceled. In the subject invention the second order distortion over a 10 1 frequency range for instance between 2 Gigahertz and 20 Gigahertz can be canceled.

In summary a wide bandwidth microwave balun utilizes frequency band splitting and two conventional baluns operating in a high frequency band and a low frequency band which when combined offer a full bandwidth output thus to offer wide bandwidth impedance matching and second harmonic rejection.

Referring now to the design of the subject bal plex balun begins with the design of the individual upper and lower band baluns. It is noted that the frequency bands must overlap enough to allow a smooth transition and a smooth frequency response but not so much as to lose the frequency response at the highest and lowest frequencies.

Referring now to one type of simple conventional balun uses coupled lines and . The bandwidth for this circuit is approximately one octave centered on the quarter wave frequency of the coupled lines. Note that as will be described later the input to the balun is unbalanced across terminals and with terminal grounded whereas the balanced output is available across terminals and .

Referring to a compensated balun is shown whose architecture is used for the low frequency band balun of the subject invention. This compensated balun is illustrated as having coupled lines and and coupled lines and . Here the unbalanced input is between input terminals and with terminal grounded to lines and . The balanced output is available at terminals and . It is noted that line is coupled to line at with line being open circuit terminated as illustrated at . While line is grounded at terminal line is terminated at .

The balun bandwidth for the circuit approaches 4 1 and is a member of the class of compensated baluns described by H. G. Oltman Jr. The Compensated Balun IEEE Transactions In Microwave Theory and Techniques MTT 14 pp. 112 119 1966. One this type of compensated balun is the well known Marchand balun. It is this balun configuration that in a spiral coupled line balun configuration establishes a low frequency band balun and in an ordinary configuration establishes the high frequency band balun.

Referring to it is possible to achieve a full bandwidth unbalanced output that cancels second order distortions from an unbalanced input using the subject balun here called a bal plex balun . In this embodiment the bal plex balun is fed by a balanced input on lines and from a differential amplifier having a balanced input from for instance an antenna . Here the unbalanced output of the bal plex balun is shown at .

Alternatively the balanced input for the bal plex balun can be achieved by coupling the output of a balun supplied with an unbalanced input to the differential amplifier inputs.

Alternatively as illustrated in an unbalanced input may be coupled to the input of the subject bal plex balun to provide a balanced output for connection to the inputs of a balanced amplifier differential circuit or broad band antenna.

Referring now to having a balanced input at the high frequency and low frequency bands are separated using diplexers and each of which divide up the incoming signal into a low frequency band component and a high frequency band component .

As can be seen low frequency band components from diplexers and are applied to a low frequency band balun whereas the high frequency components from each of the diplexers are applied to the inputs of a high frequency band balun .

The output of the low frequency band balun is a single ended low frequency signal whereas the output of the high frequency band balun is a single ended high frequency signal . These single ended low frequency and high frequency signals are applied to a diplexer which combines the outputs of baluns and to supply the full bandwidth unbalanced output. Thus the bal plex balun of in one embodiment is configured as illustrated in A.

Alternatively when operated in the reverse direction to convert an unbalanced input to a balanced output and as illustrated in unbalanced input is applied to diplexer which divides up the unbalanced input signal into a single ended low frequency signal and a single ended high frequency signal . The outputs of the low frequency and high frequency band baluns and have low frequency and high frequency components and coupled to the respective low frequency and high frequency inputs to diplexers and . These diplexers combine the outputs of baluns and into a full bandwidth balanced output signal .

What is accomplished is to divide up an unbalanced input into upper and lower frequency bands provide the balun function for these two bands and combine them in one direction to provide a double bandwidth output or to take a balanced input dividing it up into the low and high frequency bands and apply them to the low frequency band and high frequency band baluns after which the balun outputs are combined into a double bandwidth unbalanced output.

The double bandwidth provides the 10 1 ratio such that for microwave frequencies the bal plex balun can operate from 2 20 GHz. The subject invention in one embodiment is a planar MMIC balun that has excellent performance over this decade bandwidth of 2 to 20 GHz. This very wide performance bandwidth is achieved with the combining of a 2 to 7 GHz spiral coupled line balun and a 6 to 20 GHz coupled line balun. These two compensated baluns are combined with each other using diplexer or other high pass low pass filters to achieve the overall bandwidth. In one embodiment the diplexers are further simplified with the absorption of filter elements into the balun input and output impedances.

Referring now to the pass band for the bal plex balun which incorporates the combined high band balun outputs and low band balun outputs is illustrated in terms of the amplitude or the magnitude transfer function for the balun.

For the high band baluns it is very clear that the pass band from 6 Gigahertz up through 20 Gigahertz is relatively flat. From it is noted that the output terminal for the high and low frequency baluns is labeled whereas their input terminals are respectively and .

For the high frequency band the response is illustrated by curves A and A . This shows a relatively flat response over the 3.5 1 bandwidth.

For the low frequency band the response is illustrated by curves B and B . It will be appreciated from the curves in that what is shown is the main pass band for the low frequency band baluns. However there is an out of band response that is undesirable. Note there is an out of band response peak X due to a peak at 12.5 GHz. These artifacts are illustrated by peaks X peaks Yand Y and peak Z.

It can be shown that this undesirable result can be eliminated by having a diplexer of sufficient selectivity that the responses shown in are filtered out. Thus if one chooses the diplexers with appropriate frequency responses one can eliminate the out of band artifacts.

Referring now to what is shown is an equivalent circuit for a diplexer for instance diplexer showing ideal inductors and capacitors for the simplest type of diplexer circuit.

It is noted that the diplexer function is to provide both high band and low band signals. Here an input is coupled to a low pass filter comprised of inductors and and capacitor with capacitor coupled between the junction of inductors and to ground. The high pass section of this diplexer is comprised of capacitors and with an inductor coupled between the junction between these capacitors and ground. This high pass filter is shown at .

Referring now to in one implementation of the subject bal plex balun it is possible to eliminate the diplexers and replace them with high and low pass filters as illustrated. The circuit of eliminates the diplexer in by supplying two equivalent high pass and low pass filters while at the same time providing an LC circuit a portion of which includes an inductor which is a part of the low pass filter at the output. Note that the diplexer at the outputs of baluns and is replaced with a low pass filter at the output of balun including inductor whereas the high frequency band comes directly out of balun . As will be seen the high band and low bands are combined at to provide a full bandwidth output .

The elimination of the diplexers is accomplished through a microwave design called parasitic absorption where some of the behavior of the circuit is implicit in the circuit that one wants to match with.

Note that in terms of the output circuit parasitic absorption results in only a single inductor namely inductor . Thus out of the six original components five of them have been eliminated because of pre existing behavior in the low band and high band baluns. Thus for a balanced input the diplexers that would normally be utilized to separate out the signals into a high frequency band and a low frequency band are replaced with circuit elements constituting a low pass filter and a high pass filter here respectively and .

Note that the pair of low pass filters is comprised of inductors and and capacitors and whereas the pair of high pass filters is comprised of capacitors and . Note also that inductors and are series inductors which are part of the low pass filter structure with capacitors and acting as shunt capacitors.

Likewise for the high pass filters capacitors and being series oriented are high pass elements and are part of the high pass filter structure that duplicates the high pass side of the diplexer going into the high frequency band balun .

As a result the two diplexers that are used at the front end of the bal plex balun are simplified with this methodology.

The output of the bal plex balun substitutes for the diplexer associated with the output of a simplified circuit using only one low pass element inductor . This element indicates a simplified equivalent circuit for the low pass behavior.

It is noted that in in which the bal plex magnitude for each of the high frequency band and low frequency band components has an amplitude response that tracks very closely between the two sides of the balun namely over a decade bandwidth extending from about 2 Gigahertz to 20 Gigahertz. Thus what is shown in the graph is a good amplitude pass band response over a decade bandwidth.

With respect to the bal plex phase graph of it will be seen that there is good 180 degree out of phase response for each of the balanced outputs in which for the same signal the phase of the two divided out signals track in phase such that the signals are very close to being exactly 180 degrees out of phase.

Referring now to in one embodiment of a MMIC that performs a bal plex function there is a spiral coupled Marchand type low band balun which functions between 2 and 7 Gigahertz comprised of spiral lines and and spiral lines and with coupling between the lines and corresponding to the corresponding components illustrated in .

The high frequency band balun is comprised of lines and and lines and corresponding to the corresponding components illustrated in to give a coupled line balun with 6 to 20 Gigahertz high frequency bandwidth. Note that like reference characters correspond to like elements between . Note also that spiral lines and correspond to inductor of and likewise to inductors and in . Capacitors and correspond to capacitor in and likewise to capacitors and in . Here capacitors and and inductor correspond to the equivalent capacitors and inductor in . Note that line in is grounded at ground for the high frequency band whereas line is grounded at ground for the other side of the high frequency band balun. Note that capacitor is a large area capacitor that provides RF grounding to all frequencies of interest. If biasing is required for preamplifiers or other amplification stages coupled to the bal plex balun DC coupling is provided from bias point to .

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

