---

title: Echo reduction system
abstract: A system for reducing an echo and/or a residual echo in a microphone output signal includes an echo compensation filter configured to receive audio input signals and generate an estimated echo signal. A speech activity detector is configured to detect speech of a local speaker, and a combining circuit is configured to generate an echo compensated signal by subtracting the estimated echo signal from the microphone output signal. A residual echo reduction circuit is configured to suppress the residual echo in the echo compensated signal based on the detected speech activity, and output an echo suppressed output signal. The echo reduction system may reduce local background noise and residual echoes in a microphone output signal so that local speech may be transmitted free from undesirable signals.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08111840&OS=08111840&RS=08111840
owner: Nuance Communications, Inc.
number: 08111840
owner_city: Burlington
owner_country: US
publication_date: 20070418
---
This application claims the benefit of priority from European Patent Application No. 06 009468.7 filed May 8 2006 which is incorporated by reference.

This disclosure relates to echo reduction. In particular this disclosure relates to echo reduction and suppression of residual echo signals in communication systems.

Echo reduction or suppression may be needed in communication systems such as hands free sets and speech recognition systems. Communication systems may include a microphone that detects a desired signal such as a speech signal from a user. However the microphone may also detect undesirable signals such as echoes produced by a loudspeaker in the audio environment.

Echoes may occur when signals transmitted by a remote party and received by a near end are output by loudspeakers at the near end. Such signals may be detected by the near end microphone and re transmitted back to the remote party. Echoes may be annoying to the user and may result in a communication failure.

Echo suppression may be particularly difficult if the speaker is moving such as when a driver is using a hands free set and also steers a vehicle. In this situation an impulse response of the loudspeaker room microphone LRM environment may be time variant. Existing echo suppression systems may be unreliable and may not be particularly effective in a time varying LRM environment. After application of echo suppression techniques residual echoes may be present. The severity of the residual echoes may be increased by the large delay paths associated with mobile phone services. Accordingly a need exists for an echo reduction system capable of reducing echoes and residual echoes.

A filter bank may separate a microphone output signal into sub band microphone signals. An audio input filter bank may separate audio input signals into of sub band audio signals. An echo compensation filter receives the audio input signals from each sub band range and may generate a corresponding estimated echo signal. A speech activity detector may detect the speech of a local speaker by analyzing the power spectrum. The estimated echo signal may be subtracted from the microphone output signal to compensate for echoes. A residual echo reduction circuit may remove any residual echoes in the echo compensated signal based on speech activity.

Other systems methods features and advantages will be or will become apparent to one with skill in the art upon examination of the following figures and detailed description. It is intended that all such additional systems methods features and advantages be included within this description be within the scope of the invention and be protected by the following claims.

The microphone may detect undesirable signals such as echo signals produced by the loudspeaker . Echoes may occur when signals transmitted by the remote communication party are output by loudspeakers at the near end and retransmitted via the microphone back to the remote communication party . Such echoes may occur in various speech recognition systems or speech dialog systems.

The microphone may detect speech signals s n of the local speaker as well as background noise signals b n . The microphone may further detect a loudspeaker room microphone LRM transfer signal d n based on an impulse response h n of a LRM environment or system . A microphone output signal y n may include contributions from the speech signal s n the background noise signal b n and the LRM transfer signal d n . The term n may denote a discrete time index.

The echo reduction system may provide echo compensation and residual echo suppression. Echo compensation may be performed by an adaptive echo compensation filtering system that may model the loudspeaker room microphone system transfer function using an impulse response. Such processing may be performed by dividing the signal spectrum into sub bands and processing each sub band separately. Alternatively the input signals my be processed in the frequency domain using Fast Fourier Transforms of the respective audio input signal x n and the microphone output signal y n .

An audio input filter bank may generate a plurality of sub band audio signals X e n based on the audio input signal x n . A microphone output filter bank may generate a plurality of microphone sub band signals Y e n based on the microphone output signal y n . The mid frequency of each sub band may be denoted by .

Echo compensation detection of speech activity whether the speaker is silent or is speaking and suppression of residual echo may be performed in the sub band ranges. After suppression of the residual echo in the sub bands a synthesizer may synthesize the desired output signal which may be transmitted to the remote communication party .

The audio sub band signals X e n generated by the audio input filter bank may be filtered by an adaptive echo compensation filter . The filter coefficients of the echo compensation filter may model the impulse response in the sub bands. Adaptation of the filter coefficients may be based on a statistical process such as a recursive least squares process normalized least mean squares process proportional least mean squares process and or least mean squares process. An estimated echo signal circumflex over D e n in each sub band may be obtained by processing the audio input sub band signals X e n with the impulse response e n of the echo compensation filter .

The echo compensation filter may include hardware and or software and may include a digital signal processor DSP . The DSP may execute instructions that delay an input signal one or more additional times track frequency components of a signal filter a signal and or attenuate or boost an amplitude of a signal. Alternatively the echo compensation filter or DSP may be implemented as discrete logic or circuitry a mix of discrete logic and a processor or may be distributed over multiple processors or software programs.

The echo compensation filter may generate the estimated echo signal circumflex over D e n which may correspond to an echo received by the remote communication party . A summing circuit may combine subtract the estimated echo signal circumflex over D e n and the microphone sub band signals Y e n to generate echo compensated signals E e n in each sub band range.

A residual echo reduction circuit may process the echo compensated signals E e n to suppress residual echoes. The residual echo reduction circuit may be part of the residual echo processing circuitry . The residual echo reduction circuit may include or may communicate with a noise reduction circuit and may remove the background noise contribution b n of the echo compensated signals E e n . Echo suppressed sub band output signals e n generated by the residual echo reduction circuit may be synthesized to obtain a desired output signal. The output signal may comprise the sub band signals transmitted to the remote communication party .

The residual echo reduction circuit may use a Wiener filter implementation to estimate a power density spectrum of the residual echo n and estimate the power density spectrum of the echo compensated sub band signals n . The Wiener filter may exhibit the following filter response 

A maximum damping value may be determined by the parameter G and the sensitivity of the filter may be controlled by the parameter . If 1 the damping may be greater than desired which may dampen the desired signal below an predetermined level.

The filter characteristic or frequency response of the residual echo reduction filter may be adjusted so that damping is sensitive aggressive when local speaker speech is absent. The echo reduction system may distinguish speech signals produced by the local speaker from signals transmitted by the loudspeaker in the time variant LRM environment . Such local speaker speech signals s n may be detected when the local speaker is moving. Accordingly the filter response of the residual echo reduction circuit may adapt to the speech activity of the local speaker .

The smoothing circuits and may include a first order recursive filter to smooth the magnitudes or the squares of the magnitudes of the signals. Smoothing may be performed in a positive direction to or in a negative direction to with respect to the frequency range. Smoothing may be performed according to the following equations 

For a sampling rate of about 11025 Hz and M 256 sub bands a smoothing parameter may be selected so that 0.2 0.8. Smoothing the microphone sub band signals Y e n may yield a smoothed microphone spectrum S n .

The smoothing circuits and may also receive the output n of the noise estimating circuit which may be based on the estimated power density spectrum of the microphone sub band signals Y e n . The smoothing circuits and may determine the maximum of the smoothed estimated echo spectrum according to the following equations 

Satisfactory echo suppression results may be obtained when 2 K 16. Weighting functions wS n wS n may be chosen to determine a distance measure which may indicate speech activity. The values of wand wmay be selected depending on the value of . Alternatively the values of wand wmay be constants.

A flank detection circuit may detect a strong level increase or decrease of the microphone sub band signals Y e n or the estimated echo signal circumflex over D e n . Strong temporary level changes may cause artifacts when calculating the distance measure for determining the speech activity of the local speaker. If no abrupt level changes are detected i.e. temporarily relatively homogeneous signals are present the smoothed output signals smooth S n and S n generated by the smoothing circuits and respectively may be used by the signal flank detection circuit according the following equations 

A distance detection circuit may determine a spectrum distance measure based on n and the modified spectra S n and S n calculated by the smoothing circuits and according to the following equations 

The detection threshold values may be selected as K 16 K 4 K 4 and K 16. The distances C n may be specified by detection parameters C 0.4 C 0.1 C 0.1 and C 0.6. Large positive values of the spectrum distance measure C n may indicate that the power density of the microphone spectrum dominates the power density of the estimated echo. If the power density of the estimated echo significantly exceeds the power density of the microphone spectrum strong changes in the LRM system may be indicated which may result in a high negative cost parameter C.

The determination of both n and C n may be restricted to sub bands that show a significant power of speech signals. This may indicate that the sub bands may be restricted to where and correspond to a frequency range of about 200 Hz to about 300 Hz. A summing circuit may sum the results C n for the individual sub bands where

Based upon the detected speech activity as measured by n the summed output C n of the distance detection circuit may be used to adapt the filter characteristic of the residual echo reduction circuit . If no speech activity is detected based on the smoothed distance measure n residual echo filtering may be performed based on the square of the magnitude of the estimated echo signal circumflex over D e n or the maximum of circumflex over D e n and the power density of the residual echo n .

Double talk may occur when both the local speaker and the remote communication party speak simultaneously and significant speech activity is detected. When double talk occurs a Wiener filter with a time dependent filter parameter n may be used. The residual echo reduction circuit may process residual echo according to the following equations max where

The parameter n may control the sensitivity of the filter based on the smoothed distance measure according to the following equation 

If the estimated power density of the echo compensated signal greatly exceeds the estimated power density of the residual echo suppression of the residual echo may be minimized so that the microphone output signal is not significantly modified. In contrast if the estimated power density of the residual echo exceeds the estimated power density of the echo compensated signal compensated signal may be filtered aggressively.

Suppressing the residual echo in the echo compensated signal may include filtering the echo compensated signal with a filter having the following frequency response 

The power density spectrum n of the echo compensated sub band microphone signals E e n may be recursively determined according to the following equation 1 1 where a smoothing parameter may be chosen as 0 1.

Further the power density spectrum n of the residual echo may be determined according to the following equation where the estimated echo compensation e n provided by the echo compensation filter may be calculated by methods described in an article entitled Step Size Control in Subband Echo Cancellation Systems G. Schmidt IWANEC 1999 Pocona Manor Pa. USA Conf. Proceed. p. 116 119 1999 which is incorporated by reference.

The estimated power density spectrum n of the audio signal output of the loudspeaker may be calculated according to the following equation 1 1 where the smoothing parameter may be chosen as 0 1.

A parameter circuit may receive input from the local speech activity detector and determine an appropriate value of . The residual reduction circuit may utilize the parameter value.

A local speech activity detector may include the first and second smoothing circuit and shown in . The local speech activity detector may receive the estimated echo signals circumflex over D e n for the sub bands the microphone sub band signals Y e n and the output of the noise estimating circuit . The power density spectrum of the background noise n obtained by the noise estimating circuit may provide input to an artificial noise or comfort noise generator .

The artificial noise generator may generate artificial noise with substantially the same statistical power distribution as the background noise. The artificially generated noise signal or comfort noise signal B e n may be generated when the sub band output signals e n generated by the residual echo reduction circuit has a power density below that of the remaining background noise. A switch may allow the system to select between the comfort noise signal B e n and the sub band output signals e n to avoid an abrupt change of the background noise transmitted to the remote communication party . The residual echo reduction circuit may determine whether to output the comfort noise signal.

The desired signal or sub band output signal e n transmitted to the remote communication party may be synthesized from the sub band signals according to the following equation 

The LRM environment was changed by simulating movement of the local speaker at a time t 5 seconds and again at a time t 15 seconds. Panel D shows the addition of double talk from a time t 20.5 seconds to a time t 27.5 seconds.

Panel C shows the smoothed distance measure n as a result of the speech activity detection circuit . As shown by the waveform the smoothed distance measure n does not respond or responds slightly to the speaker s movements. In particular n may be below the threshold C 1. Panel C may show significant residual echo suppression while the speaker moves. During the period of time when double talk exists the smoothed distance measure n may indicate speech activity of the local speaker . As a result the desired output signal e n may show a correspondence with the simulated speech signal of the local speaker.

The logic circuitry and processing described above may be encoded in a computer readable medium such as a CDROM disk flash memory RAM or ROM an electromagnetic signal or other machine readable medium as instructions for execution by a processor. Alternatively or additionally the logic may be implemented as analog or digital logic using hardware such as one or more integrated circuits including amplifiers adders delays and filters or one or more processors executing amplification adding delaying and filtering instructions or in software in an application programming interface API or in a Dynamic Link Library DLL functions available in a shared memory or defined as local or remote procedure calls or as a combination of hardware and software.

The logic may be represented in e.g. stored on or in a computer readable medium machine readable medium propagated signal medium and or signal bearing medium. The media may comprise any device that contains stores communicates propagates or transports executable instructions for use by or in connection with an instruction executable system apparatus or device. The machine readable medium may selectively be but is not limited to an electronic magnetic optical electromagnetic or infrared signal or a semiconductor system apparatus device or propagation medium. A non exhaustive list of examples of a machine readable medium includes a magnetic or optical disk a volatile memory such as a Random Access Memory RAM a Read Only Memory ROM an Erasable Programmable Read Only Memory i.e. EPROM or Flash memory or an optical fiber. A machine readable medium may also include a tangible medium upon which executable instructions are printed as the logic may be electronically stored as an image or in another format e.g. through an optical scan then compiled and or interpreted or otherwise processed. The processed medium may then be stored in a computer and or machine memory.

The systems may include additional or different logic and may be implemented in many ways. A controller may be implemented as a microprocessor microcontroller application specific integrated circuit ASIC discrete logic or a combination of other types of circuits or logic. Similarly memories may be DRAM SRAM Flash or other types of memory. Parameters e.g. conditions and thresholds and other data structures may be separately stored and managed may be incorporated into a single memory or database or may be logically and physically organized in many different ways. Programs and instruction sets may be parts of a single program separate programs or distributed across several memories and processors. The systems may be included in a wide variety of electronic devices including a cellular or wireless phone a headset a hands free set a speakerphone communication interface or an infotainment system.

While various embodiments of the invention have been described it will be apparent to those of ordinary skill in the art that many more embodiments and implementations are possible within the scope of the invention. Accordingly the invention is not to be restricted except in light of the attached claims and their equivalents.

