---

title: Dynamic crest factor reduction system
abstract: A system and method for performing digital crest factor reduction. In one embodiment, the method is devised to suppress the signal amplitude to maintain a low signal peak to average ratio (PAR), while maintaining a desirable Error Vector Magnitude (EVM). This technique may be designed to operate in highly dynamic signal conditions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07839951&OS=07839951&RS=07839951
owner: Microelectronics Technology Inc.
number: 07839951
owner_city: 
owner_country: TW
publication_date: 20070405
---
This application contains subject matter that is related to U.S. patent application Ser. No. 11 246 027 filed Oct. 7 2005 entitled SYSTEM AND METHOD FOR CREST FACTOR REDUCTION. The entire content of the above referenced application is incorporated herein by reference.

The present invention relates to electrical and electronic circuits and systems. More specifically the present invention relates to systems and methods for reducing crest factor in electrical and electronic circuits and systems.

In Multi Carrier Power Amplifier MCPA communication transmission applications multiple carriers are typically combined in the baseband intermediate frequency IF or radio frequency RF frequency range and the resulting signal is transmitted using a single power amplifier. An aspect for MCPA transmission is to transmit a signal at a very high efficiency while maintaining a low Adjacent Channel Power Ratio ACPR to meet spectral mask requirements. ACPR is defined as the ratio of power in a bandwidth away from the main signal the distortion product to the power in a bandwidth within the main signal. The bandwidths and locations are functions of the standards being employed.

To achieve high efficiency power amplifier PA transmission it is desirable to use semi non linear PAs such as Class A B PAs. A challenge for MCPA signal transmission is due to the fact that the combined signal has a high crest factor ratio of peak power to average power where the peak power is significantly higher than the average power. A small portion of the combined signal can have very high peaks and when transmitted at high PA efficiency these high level signals reach into the saturated region of the PA s transfer function and the output of the PA has high intermodulation distortion IMD . The high IMD level raises the ACPR levels.

To maintain low ACPR without any linearization techniques the transmit signal level must be decreased sufficiently so that the peak amplitudes are not in the saturated zone of the PA but this reduces the amplifier efficiency. For example a four carrier W CDMA wideband code division multiple access signal can have a crest factor exceeding 13 dB. If the crest factor is reduced by about 6 dB the average power can be increased by 6 dB thus increasing the power efficiency by a factor of 4.

One approach to this problem is to limit the amplitude of either the baseband signal or the RF signal output of each channel using a look ahead approach. However it is difficult to generate signals with low crest factor and low ACPR inasmuch as limiting the amplitude increases out of band emissions e.g. sidelobes and thereby raises the ACPR level. Similarly efforts to reduce the ACPR levels generally increase crest factor.

Another approach involves the use of unused CDMA codes to reduce the crest factor in the output signals. However this approach requires knowledge of what is being transmitted so that the unused codes can be identified. This adds to the complexity storage requirements and cost of the system.

Hence a need remains in the art for an improved system or method for reducing the crest factor in communications systems while maintaining a low ACPR therefor.

Aspects of embodiments of the present invention are directed to systems and methods for reducing crest factor in electrical and electronic circuits and systems.

In one embodiment of the present invention a crest reduction system for gain leveling includes an estimator for estimating a root mean square RMS level of a first signal carrier and an RMS level of a second signal carrier each of the first and second signal carriers having an amplitude a leveling setter for receiving the estimated RMS levels of the first and second signal carriers for producing a first gain leveling factor and a second gain leveling factor for the first signal carrier by using the estimated RMS level of the first signal carrier and for producing a third gain leveling factor and a fourth gain leveling factor for the second signal carrier by using the estimated RMS level of the second signal carrier a first leveler for receiving the first signal carrier and the first gain leveling factor and for changing the amplitude of the first signal carrier by adjusting the first signal carrier according to the first gain leveling factor a second leveler for receiving the second signal carrier and the third gain leveling factor and for changing the amplitude of the second signal carrier by adjusting the second signal carrier according to the third gain leveling factor and a filter configurator for receiving the second and fourth gain leveling factors for producing one or more first filter coefficients to further change the amplitude of the first signal carrier according to the second gain leveling factor and for producing one or more second filter coefficients to further change the amplitude of the second signal carrier according to the fourth gain leveling factor. The second gain leveling factor is substantially equal to the reciprocal of the first gain leveling factor and the fourth gain leveling factor is substantially equal to the reciprocal of the third gain leveling factor.

The estimator may include a low pass filter configured by one or more scale factors the low pass filter being for estimating at least one of the RMS level of the first signal carrier or the RMS level of the second signal carrier.

The first signal carrier may have a first signal to distortion ratio SDR and the second signal carrier may have a second SDR different from the first SDR.

The first leveler may be adapted to adjust the first signal carrier according to the first gain leveling factor by multiplying the amplitude of the first signal carrier by the first gain leveling factor.

The second leveler may be adapted to adjust the second signal carrier according to the third gain leveling factor by multiplying the amplitude of the second signal carrier by the third gain leveling factor.

The second gain leveling factor may be a multiplicative factor of at least one of the one or more first filter coefficients produced by the filter configurator.

The fourth gain leveling factor may be a multiplicative factor of at least one of the one or more second filter coefficients produced by the filter configurator.

The crest reduction system may further include a leveled carrier combiner for receiving the adjusted first signal carrier from the first leveler for receiving the adjusted second signal carrier from the second leveler and for producing a multi carrier signal from the adjusted first signal carrier and the adjusted second signal carrier.

The leveled carrier combiner may be adapted to produce the multi carrier signal by coherently combining the adjusted first signal carrier and the adjusted second signal carrier.

In another embodiment of the present invention a method for gain leveling in a crest reduction system may include estimating a root mean square RMS level of a first signal carrier and an RMS level of a second signal carrier each of the first and second signal carriers having an amplitude determining a first gain leveling factor and a second gain leveling factor for the first signal carrier by using the estimated RMS level of the first signal carrier determining a third gain leveling factor and a fourth gain leveling factor for the second signal carrier by using the estimated RMS level of the second signal carrier changing the amplitude of the first signal carrier by adjusting the first signal carrier according to the first gain leveling factor changing the amplitude of the second signal carrier by adjusting the second signal carrier according to the third gain leveling factor and determining one or more first filter coefficients to further change the amplitude of the first signal carrier according to the second gain leveling factor and determining one or more second filter coefficients to further change the amplitude of the second signal carrier according to the fourth gain leveling factor. The second gain leveling factor is substantially equal to the reciprocal of the first gain leveling factor and the fourth gain leveling factor is substantially equal to the reciprocal of the third gain leveling factor.

In another embodiment of the present invention a crest reduction system for amplitude limiting includes a controller for receiving a first signal including one or more signal carriers for determining a signal to distortion ratio SDR of the first signal and for producing a correction value by using the determined SDR and a threshold SDR and a dynamic amplitude clipper for receiving the correction value and a second signal corresponding to the first signal and for producing a clipped signal by limiting an amplitude of the second signal according to a value corresponding to the correction value such that a peak to average ratio PAR of the clipped signal is not greater than a PAR of the second signal. The clipped signal has phase characteristics substantially equal to phase characteristics of the second signal.

The crest reduction system may further include a second dynamic amplitude clipper coupled with the dynamic amplitude clipper the second dynamic amplitude clipper being for receiving the correction value and a third signal corresponding to the clipped signal and for producing a second clipped signal by limiting an amplitude of the third signal according to a second value corresponding to the correction value such that a PAR of the second clipped signal is not greater than a PAR of the third signal. The second clipped signal has phase characteristics substantially equal to phase characteristics of the third signal.

The phase characteristics of the second clipped signal may be substantially equal to phase characteristics of the clipped signal.

The dynamic amplitude clipper may include an estimator for estimating a root mean square RMS level of the second signal. The value corresponding to the correction value may further correspond to the estimated RMS level of the second signal such that the PAR of the clipped signal is substantially constant over time. The second dynamic amplitude clipper may include an estimator for estimating an RMS level of the third signal. The second value corresponding to the correction value may further correspond to the estimated RMS level of the third signal such that the PAR of the second clipped signal is substantially constant over time.

The estimator for estimating the power of the second signal may include an infinite impulse response filter.

The crest reduction system may further include a gain corrector for receiving a third signal corresponding to the clipped signal and for reducing an energy loss of the third signal resulting from the limiting of the amplitude of the second signal by the dynamic amplitude clipper.

The dynamic amplitude clipper may be adapted to be controlled to produce an unclipped signal from the second signal and a PAR of the unclipped signal may be substantially equal to the PAR of the second signal.

The crest reduction system may further include a timing and control unit for controlling the dynamic amplitude clipper to produce the unclipped signal.

The dynamic amplitude clipper may include a first multiplier for multiplying the second signal and an inverse of the value corresponding to the correction value and a second multiplier for producing the clipped signal by multiplying a third signal corresponding to the second signal and the value corresponding to the correction value.

In another embodiment of the present invention a method for amplitude limiting in a crest reduction system includes receiving a first signal including one or more signal carriers determining a signal to distortion ratio SDR of the first signal producing a correction value by using the determined SDR and a threshold SDR and producing a second signal corresponding to the first signal producing a clipped signal by limiting an amplitude of the second signal according to a value corresponding to the correction value such that a peak to average ratio PAR of the clipped signal is not greater than a PAR of the second signal. The clipped signal has phase characteristics substantially equal to phase characteristics of the second signal.

In another embodiment of the present invention a crest reduction system for composite filtering includes a timing and control unit for receiving a first signal including a plurality of signal carriers and for processing a detected absence of one or more of the signal carriers a filter configurator for producing a plurality of composite coefficients for filtering of the signal each of the composite coefficients being formed from a plurality of coefficients and for zeroing one or more of the coefficients corresponding to the one or more signal carriers in response to the detected absence of the one or more signal carriers and a filter generator for receiving the composite coefficients and for implementing a filter for a second signal corresponding to the first signal the filter being configured to output a third signal by filtering the second signal according to the composite coefficients.

The filter may be further configured to output the third signal by substantially filtering out one or more frequency components of the second signal corresponding to the zeroed one or more of the coefficients.

The filter configurator may include a plurality of multiplexer units each of the multiplexer units being adapted to receive one or more of the coefficients corresponding to one of the signal carriers and to output either the one or more of the coefficients or one or more zero value coefficients in response to the detected absence of the one of the signal carriers.

The filter configurator may further include a combiner for receiving the respective outputs of the multiplexer units and for producing the composite coefficients by linearly combining the respective outputs.

The crest reduction system may further include a second filter generator for receiving the composite coefficients and for implementing a second filter for a fourth signal corresponding to the third signal the second filter being configured to output a fifth signal by filtering the fourth signal according to the composite coefficients.

The second filter may be further configured to output the fifth signal by substantially filtering out one or more frequency components of the fourth signal corresponding to the zeroed one or more of the coefficients.

A first one of the signal carriers may have a first passband and a second one of the signal carriers may have a second passband the first passband and the second passband forming a frequency well therebetween. The filter configurator may further be for producing a plurality of nibble coefficients for the filtering of the signal the nibble coefficients being configured to substantially fill the frequency well.

The filter configurator may include a multiplexer unit adapted to receive one or more of the nibble coefficients corresponding to the first one of the signal carriers and the second one of the signal carriers and to output either the one or more of the nibble coefficients or one or more zero value coefficients in response to the detected absence of at least one of the first one of the signal carriers or the second one of the signal carriers.

In another embodiment of the present invention a method for composite filtering in a crest reduction system includes receiving a first signal including a plurality of signal carriers processing a detected absence of one or more of the signal carriers producing a plurality of composite coefficients for filtering of the signal each of the composite coefficients being formed from a plurality of coefficients zeroing one or more of the coefficients corresponding to the one or more signal carriers in response to the detected absence of the one or more signal carriers and implementing a filter for a second signal corresponding to the first signal the filter being configured to output a third signal by filtering the second signal according to the composite coefficients.

In another embodiment of the present invention a crest reduction system includes a controller for receiving a first frequency and a first bandwidth of a first baseband symbol stream and for receiving a second frequency and a second bandwidth of a second baseband symbol stream a first carrier processor for receiving the first baseband symbol stream and for converting the first baseband symbol stream to a first signal having the first bandwidth centered about the first frequency a second carrier processor for receiving the second baseband symbol stream and for converting the second baseband symbol stream to a second signal having the second bandwidth centered about the second frequency and one or more signals processors for receiving the first and second signals and for adjusting a respective signal to distortion ratio SDR of each of the first and second signals while a peak to average ratio PAR of a composite signal produced from the first and second signals is reduced.

The first bandwidth may have a frequency range different from a frequency range of the second bandwidth.

The first bandwidth may have a frequency range substantially equal to a frequency range of the second bandwidth.

The first baseband symbol stream may correspond to a WCDMA signal and the second baseband symbol stream may correspond to a cdma2000 signal.

The crest reduction system may further include a combiner for receiving the first and second signals and for producing a multi carrier signal from the first and second signals.

The combiner may be adapted to produce the multi carrier signal by coherently combining the first and second signals.

The first carrier processor may be adapted to increase a sample rate of the first baseband symbol stream according to a first rate to produce a first intermediate signal and the second carrier processor may be adapted to increase a sample rate of the second baseband symbol stream according to a second rate to produce a second intermediate signal. The first rate may have a value different from a value of the second rate. The first carrier processor may include a first resampler for resampling the first intermediate signal according to a third rate to produce the first signal and the second carrier processor may include a second resampler for resampling the second intermediate signal according to a fourth rate substantially equal to the third rate to produce the second signal.

In another embodiment of the present invention a method of signal converting in a crest reduction system includes receiving a first frequency and a first bandwidth corresponding to a first baseband symbol stream receiving a second frequency and a second bandwidth corresponding to a second baseband symbol stream converting the first baseband symbol stream to a first signal having the first bandwidth centered about the first frequency converting the second baseband symbol stream to a second signal having the second bandwidth centered about the second frequency and adjusting a respective signal to distortion ratio SDR of each of the first and second signals while a peak to average ratio PAR of a composite signal produced from the first and second signals is reduced.

In the following detailed description only certain exemplary embodiments of the present invention are shown and described by way of illustration. As those skilled in the art would recognize the described exemplary embodiments may be modified in various ways all without departing from the spirit or scope of the present invention. Accordingly the drawings and description are to be regarded as illustrative in nature and not restrictive.

One aspect of the present invention is directed towards reducing the crest factor of a signal in a manner that delivers low ACPR and low EVM for dynamic signals.

The Carrier Processors support N channels. Each Carrier Processor has a different center frequency but can have the same or different filter types to shape similar or different signal modulations. For example Carrier Processor for Channel can be for WCDMA having 3.84 MHz bandwidth Carrier Processor for Channel can be for cdma2000 having 1.2288 MHz bandwidth Carrier Processor for Channel can be bypassed to accommodate signals that are already shaped and Carrier Processor for Channel can be for OFDM having 5 MHz bandwidth. Likewise each channel processor can have identical bandshapes.

Each channel carrier processor converts the baseband symbol stream x m to an intermediate frequency IF signal y m center at the frequency fwith reference to . The carriers are then combined by the Carrier Combiner to produce a composite signal s m that contains multi carriers. This signal may then be used to control the composite Signal to Distortion Ratio SDR and thus the EVM of each carrier.

Carrier Leveling Mode is controlled by the Carrier Leveling Setter Carrier Levelers and the Leveled Carrier Combiner . Carrier Leveling Mode provides a mechanism for setting and maintaining possibly different signal to distortion ratios for each individual carrier. In the main path the carriers y m are adjusted by gains 1 gin the Carrier Levelers to force the carrier amplitudes to the desired levels. The outputs of the N Carrier Levelers gained carriers z z . . . zare combined using the Leveled Carrier Combiner to produce the signal u m . This signal is fed to the Dynamic Amplitude Clippers and CFR Filters for peak amplitude suppression and to the Signal to Distortion Controller to control the peak amplitude suppression to maintain the desired SDR and thus the carriers EVM.

An aspect of the Carrier Leveling Setter is to control the amplitude of each carrier channel signal to establish the desired channel distortion or EVM. The power of each carrier is estimated using the Carrier RMS Estimator . Based on the carrier powers the Carrier Leveling Setter determines gain gand 1 gthat will be applied at the CFR Filter Configurator and the Carrier Levelers . The Carrier Levelers can be bypassed when adjustments to control SDR for individual carriers are not required.

Occasionally a first Dynamic Amplitude Clipper or a second Dynamic Amplitude Clipper or both contained in Dynamic Amplitude Clippers and CFR Filters see for example can be disabled momentarily to produce a high PAR signal if the digital predistortion processor DPD needs a high peak signal to characterize the PA. Upon instruction the amplitude clipper or clippers occasionally halt the clipping process for a very short period of time to produce a non clipped signal. This high PAR signal allows the DPD system to characterize the PA at high power for effective linearization. Because the duration of this high PAR signal is short it does not degrade the power amplifier performance significantly.

In one embodiment with reference to the Dynamic Amplitude Clippers are processes that suppress the peak amplitude of the composite transmit signal without phase distortion. The Dynamic Amplitude Clippers can operate in either Static Mode or Dynamic Mode. In Static Mode clipping is performed at a fixed level regardless of the RMS level of the signal being clipped. Thus as the signal s RMS level increases more of the signal is clipped and as it decreases less of the signal is clipped. In Static Mode the peak to average ratio of the signal will fluctuate with the RMS level of the signal. In Dynamic Mode the ratio of the clipping level to the signal s RMS level is held constant which leads to a constant peak to average ratio of the output signal regardless of the RMS level of the clipped signal.

Whether in Static or Dynamic Mode this amplitude clipping function may produce both in band and out of band distortion. The in band distortion should be maintained to a desired SDR level and the out of band distortion should be suppressed to below the spectrum emission mask SEM requirements. The Signal to Distortion Controller maintains the SDR level by setting the amplitude clipping level. The CFR Filter Configurator together with the CFR filters suppress the out of band distortion.

The CFR filters can be programmable filters which perform filtering to remove the out of band noise. To support changing signal characteristics the filter coefficients are generated using the CFR Filter Configurator .

In one embodiment the CFR Filter Configurator implements filter coefficient combiner processes that determine the filters based on the amplitude of the carriers carrier frequencies carrier bandwidths filter shapes and which carriers are on or off.

The Signal to Distortion Controller monitors the signal to distortion ratio by comparing the input signal with the output signal. The SDR is computed and a correction factor is determined and is used to adjust the clipping thresholds in the Dynamic Amplitude Clippers . If the SDR is too low then the amplitude clippers thresholds are increased to improve the SDR to the required level. For example if the measured SDR is lower than a desired level then a correction factor larger than 1 is applied. This would increase the clipping threshold to improve the SDR to the correct level otherwise a factor smaller than 1 is applied and this would reduce the clipping threshold. In this fashion the SDR can be maintained at the desired level. The Signal to Distortion Controller can also be programmed to adjust the factor if the SDR is below the desired level and not adjust the clipping threshold if SDR is higher than the level. Thus the SDR Controller can prevent a small SDR while allowing fluctuations of SDR provided they remain above the desired level.

In one embodiment the Dynamic Amplitude Clippers and CFR Filters contains back to back clipper filter pairs. For example with reference to Clipper Filter Pair i.e. clipper and filter performs the majority of the crest factor reduction and noise filtering. As the highly clipped signal from the first Dynamic Amplitude Clipper passes through the first CFR Filter the signal experiences some PAR regrowth. Clipper Filter Pair i.e. clipper and filter removes some of this regrowth. Accordingly the second Dynamic Amplitude Clipper may be programmed with a slightly higher clipping level than that used in the first Dynamic Amplitude Clipper . The out of band noise introduced by the second clipper is removed with the second CFR Filter coefficients which are designed to minimize PAR regrowth due to the second filter.

Optionally included at the interfaces of each block are rate changing interpolators or decimators with the purpose of maximizing implementation efficiency.

As the result the Carrier Processor and Crest Factor Reducer produce the multi carrier signal and provide the following features 

 4 Maintains performance despite signal fluctuations power transitions varying statistics and carrier blanking.

The Transmit Modem Interface provides the interface between the Communication Modem System with the Crest Factor Reduction Processor . This interface may be specifically designed to support the desired interface.

In one embodiment the Carrier Processor provides the functions of digital upsampling filtering and frequency translation. The upsampling is used to increase the sample rate of the incoming signal. The filtering is used to remove the aliases caused by upsampling and to provide spectral shaping of the carrier.

Upsampling and filtering is performed first. With reference to the signal x m I m jQ m is processed with zero padding at processor to produce the signal x m I m jQ m that has a sampling rate of R KR where I m is the in phase component Q m is the quadrature component and Ris the sampling rate of x m . The resulting in phase and quadrature phase components of the output are then separately filtered with a shaped low pass filter Shaped FIR to produce the signal x m 

After the signals I m and Q m are sufficiently upsampled and filtered they are then frequency shifted with the Frequency Shifter to the desired carrier IF frequency as follows cos 2 sin 2 2 where fis the carrier IF frequency T is the sample period cos 2 fm T j sin 2 fm T are the outputs of the numerically controlled oscillator NCO and are phase offsets of each channel.

If all carriers have the same modulation then all the Carrier Processors would be the same in structure but if the carriers are different then the Carrier Processors would have different up sampling and filter coefficients and a Resampler may be required to provide the N carriers with the same sampling rate prior to combining the individual carriers into a single signal. Each carrier processor s Resampler resamples at the rate appropriate for the input signal y m to produce r m such that all r m across all Carrier Processors are at the same sample rate.

With reference to in one embodiment the Carrier RMS Estimator estimates the carrier powers of the individual carriers C C C . . . C to produce the RMS amplitude of the carriers A A A . . . A. The equation 

With reference to the LPF can be implemented using an integrate and dump filtering over L samples or an infinite impulse response filter IIR having a transfer function

The time constant for the IIR filter is 1 R. If is set small then the IIR converges slowly but has good accuracy and if is large then the IIR converges rapidly but has low accuracy due to the variation of the signal. If is conveniently set to 2 where k is some integer then the IIR multipliers can be replaced by bit shifters.

An aspect of the Carrier Leveling Setter is to determine the gains 1 g 1 g . . . 1 gthat are applied at the Carrier Levelers for N carriers and the gains g g . . . gthat are applied at the CFR Filter Configurator .

When the Dynamic Amplitude Clippers are applied the distortion is distributed over all carriers and the distortion s spectral density is approximately a constant over the carriers. Therefore if a carrier is strong the signal to distortion SDR for this carrier is high and if the carrier is weak the SDR for this carrier is low. In practice each carrier type has a specific SDR and the SDR for different signals can be different.

Table 1 shows the case where Carrier Leveling is disabled and no gain is applied to the individual carriers.

According to this example the cdma2000 has 4.8 dB SDR margin WCDMA meets the required margin and the OFDM has 10.2 dB margin. The different signal powers and the constant distortion power produces a SDR imbalanced design.

Table 2 shows the case where Carrier Leveling mode is enabled and desirable gains are applied to the individual carriers.

According to this example the cdma2000 has 0.07 dB SDR margin WCDMA has 0.01 dB SDR margin and the OFDM has 0.05 dB margin. This is clearly an SDR balanced design where all carriers meet the SDR requirements.

As shown in the above example the individual carriers may have to be adjusted in amplitude so that the Crest Factor Reduction has lowest PAR while meeting all carriers SDR requirements.

 4 If the value for D is not known scale all gfound in the previous step such that the desired signal to distortion ratio for all carriers meets the desired level.

In one embodiment the Carrier Levelers multiply the gain values 1 g m 1 g m . . . 1 g m from Block with the signals r m r m . . . r m to produce the signals z m z m . . . z m .

The Leveled Carrier Combiner coherently combines the carriers separately in phase and quadrature phase as follows

The Carrier Combiner coherently combines the carriers separately in phase and quadrature phase as follows

An aspect of the Dynamic Amplitude Clippers is to limit the amplitude without distorting the phase of the signal u m in a fashion that maintains the desired signal to distortion ratio even when the signal s statistics are changing.

With reference to in one embodiment the processing steps for the Dynamic Amplitude Clippers are as follows 

 2 Perform low pass filtering LPF Block of the amplitude of signal u m to estimate the signal envelope a m . This filter can be implemented with an IIR e.g. recursive filter

The filter coefficient determines the time response of the signal envelope in dynamic signal conditions.

 3 Instruct the Dynamic Amplitude Clippers to operate in static or dynamic clipping mode. For static clipping mode Timing and Control Block selects the Mux to pass value to the multiplier . For dynamic clipping mode Timing and Control Block selects the Mux to pass the signal envelope a m to the multiplier .

 4 Adjust gain or gain value gto maintain the desired SDR or to otherwise control the SDR. This is achieved without requiring the Gain look up table LUT regeneration by effectively adjusting the clipping threshold described in step below.

Based on the gain correction value g m as produced by the Signal to Distortion SDR Controller the processor determines the gain value g. This geffectively is the amount of adjustment on the threshold of the clipper. If g 1 then the threshold is effectively increased to relax the clipping. If g

To prevent the situation of excessive clipping the gain value gproduced at the output of determining unit may be the larger of g with reference to and a preset threshold g. A method to compute g m is as follows

 6 Compute the signal 1 b m at computing unit and multiply it with signal u m to produce signal u m at multiplier .

 8 Bypass the clipper if necessary. When the Timing and Control unit sends a command to employ the Clipper Bypass mode the Clipper Bypass Processor replaces the amplitude with zero over a specified duration.

 10 Delay the signal u m at delay unit to produce the signal u m u m that is aligned in time with gain G. The signal u m is multiplied at multiplier with the gain G to produce signal u m . This effectively processes the clipping of the signal amplitude.

 11 Delay at delay unit signal b m to produce signal b m to compensate for the signal delay in the main path.

 12 Multiply at multiplier the signal u m with signal b m to produce signal v m . Signal v m is the amplitude clipped version of signal u m .

The transmitted signal can be a combination of multiple carriers and thus the spectrum can be asymmetric. In these applications multiple bandpass filters can be designed one for each carrier followed by a filter combination process to realize the combined filter with a single filter as engaged in the CFR Filters . For example let v m I m jQ m be the input signal of the filter. The output of the filter can be expressed as

One embodiment of a CFR filter structure is shown in . The real and imaginary parts of the input signal I m jQ m are passed through tapped delay lines and respectively of length M selected to support the filter h m s spectral requirements. Since the taps of c m are even symmetric and the taps of c m are odd symmetric pre summing of the data in the tapped delay line is possible. Thus the samples at the taps are fed to two summers the adding summer corresponding to c m and the subtracting summer corresponding to c m . The outputs of these summers are passed to two multipliers and that form the products of the pre summed signal and the filter coefficients. Since the signal is processed in this fashion the number of multiplications required is decreased by a factor of two. To reduce the amount of hardware required to realize this filter the pre summing adders and multipliers may be shared across many taps. Thus as the inputs to the adders sweep across the taps the M 2 coefficients are changed and the multipliers outputs are combined with summers and . The Q m signal is processed with identical circuitry. The output from the I m filter side and the Q m filter side are combined with adders Blocks and to produce I m and Q m .

If the desired signal is symmetric over the origin e.g. 0 Hz then the filter is real. In that case c m 0 and only the filtering corresponding to c m is required. In this situation the complexity of the filter is cut in half.

Depending on the spectral shapes of the filters h m the composite filter c m may have spectral regions of excessive attenuation where the edges of the passbands of adjacent filters meet. This attenuation may degrade signal quality and increase the peak to average ratio of the transmitted signal. To improve performance the attenuation may be removed by inserting nibble filters. Nibble filters may be implemented with the same or substantially the same hardware used for the noise suppression filters. Their generation is described below and illustrated in . For a system with Ncarriers there may be as many as N 1 nibble filters.

In one embodiment nibble filter coefficients are determined by computing the difference of an ideal filter response i.e. one without the offending attenuation and the response of the composite filter c m in the vicinity of the attenuation. Separate nibble filters should be created for each area of undesired attenuation. In this way nibble filters may be added or removed as neighboring filters h m are added or removed.

An aspect of the CFR Filter Configurator is to compute the set C of Ncomplex passband coefficients and Ncomplex nibble coefficients that are best used for the CFR Filter . The passband coefficients form the passbands for each carrier. The Ncomplex passband coefficients are mutually orthogonal i.e. an amplitude change on one frequency does not affect other frequencies. The nibble coefficients fill in the gaps in the filter response created when frequency contiguous passband filters are added together.

Because the carriers will be changing quickly these coefficients should be computed rapidly to adapt.

The transmission consists of Ncarriers each carrier requiring a filter centered at frequency f having an amplitude gain g bandwidth B a transition bandwidth of fand rejection attenuation of Rin decibels. The number of filter coefficients could be computed as

The filter design task is simplified if the Ncarriers have M different types of signals where each type has the same signal bandwidth transition bandwidth and rejection attenuation. In that case M basic filters of length L can be configured.

 1 Compute the basic passband filters of the M types of signals. The filter coefficients are stored in the Basic Filter RAM . This process is described in the Basic Filter and Nibble Generation section below.

 2 Compute the basic nibble filters. The filter coefficients are stored in the RAM . This process is described in the Basic Filter and Nibble Generation section below.

 3 With reference to the passband and nibble filter coefficients are frequency shifted at shifter and scaler to the correct frequencies f f . . . . The frequencies are provided from the Carrier Processor Controller .

 5 The coefficients for the filters from the RAM are multiplied at multipliers with the gains g g . . . gto compensate for the carrier leveling process. The gains gare provided by the Carrier Leveling Setter .

 6 Let m be the index of the nibble filter corresponding to neighboring passband filters k and k 1. If the ratio of the gains exceeds a threshold 1 or the gain value g for the corresponding nibble filter is set to zero. Otherwise gmay be set to unity. In a dynamic signal environment these ratio tests should be recomputed when the gains are changed.

 7 A MUX is used to set the filter coefficients of carrier k to zero when Timing and Control unit sends an interrupt to indicate carrier k is not transmitted. When a carrier is not present Timing and Control will also turn off the corresponding nibble filters.

 9 The filter coefficients c c . . . c L are sent to the CFR Filters to remove the out of band distortion.

An aspect for the Basic Filter Generator is to produce a filter with very small in band ripple high out of band rejection and while meeting transition bandwidth requirements. Any valid technique can be used to generate these filter coefficients.

An aspect for the Nibble Filter Generator is to produce a compensating filter to fill in the gaps in the filter response created when frequency contiguous passband filters are added together. illustrates the generation of Nibble Filters in one embodiment of the present invention. First frequency contiguous filter pairs are combined to produce the coefficients s m . Next the desired filter response for this pair is computed to produce the coefficients d m . Finally the difference of these two are computed to produce the nibble filter coefficients n m d m s m 

The clipping of the signal amplitude will introduce loss of signal power. An aspect of the Gain Correction Processor is to correct for the loss of energy due to the clipping and filtering process to maintain the power accuracy of the transmit signal.

 1 Compute the amplitude squared at units and of the input signal s m and perform low pass filtering LPF at filter to produce the signal envelope S m . In the case that gain leveling is disabled the signal s m can be replaced with the signal u m from Leveled Carrier Combiner .

 2 Compute the amplitude squared of the input signal w m and perform low pass filtering LPF to produce the signal envelope W m .

 3 Compute at unit the ratio signal R m S m W m . This represents the power ratio of the input and the output signal.

 6 Optionally delay at delay unit signal w m to compensate for the delay of the gain correction processing.

 7 Multiply at multiplier gain m with the CFR output w m to produce signal q m . This signal has the same power with the source combined signal s m . This signal is sent to the DPD system for linearization.

With reference to in one embodiment the processing steps to compute the correction gain g are as follows 

 1 Delay at delay unit the Carrier Combiner signal s by a delay value to align the signal r and w the output of the second CFR Filter .

 8 Estimate at unit distortion power D by squaring the amplitude d m and passing through a low pass filter .

 10 Because the distortion is proportional to the 3order intermodulation product the correction factor can be established at unit as

 11 Send the correction gain g to the Dynamic Amplitude Clippers to adjust the amplitude clipping threshold.

An aspect of the Carrier Processor Controller is to coordinate operation of the carrier processors and the CFR engine. In one embodiment of the present invention this includes the following tasks.

 1 Determine signal type of each carrier. This information is used to reconfigure the carrier processors for different types of signals that may be present e.g. WCDMA cdma2000 etc. . This information is also sent to the CFR Filter Configuration Processors which determines CFR filter coefficients.

 2 Determine frequency of each carrier. This information is sent to the NCO to frequency shift each carrier and to the CFR Filter Configuration Processors to set the CFR filter center frequencies.

 3 Activate and deactivate carrier processors. This information turns off carrier processors and this information is sent to the CFR Filter Configuration Processor to reconfigure the CFR filter coefficients.

 4 IPDL processing. During Idle Periods in the Downlink IPDL carriers are momentarily turned off by the Communications Modem System by either zeroing the signal for the affected carrier or by sending off on signals to the Transmit Modem Interface . By either detecting the absence of a carrier by the Carrier RMS estimators or by using the off on signals the Carrier Processor Controller triggers filter recomputations in the CFR Filter Configurator . During IPDL periods the CFR Filter Configurator will zero out the appropriate filters and nibbles using the MUXes .

In one embodiment of the present invention the Timing and Control Processor coordinates timing critical tasks within the Dynamic Crest Factor Reduction system. The Timing and Control Processor rapidly detects control information from the Transmit Modem Interface such as Frame sync and control words. This processor may also coordinate with the time structure of the signal and at the correct time interrupt the Dynamic Amplitude Clippers to pause the clipping process. Timing and Control may also coordinate the transmit carrier disable. Based on this information Timing and Control sends interrupts to the CFR Filter Configurator to reconfigure the CFR filter coefficients.

While the present invention has been described in connection with certain exemplary embodiments it is to be understood that the invention is not limited to the disclosed embodiments but on the contrary is intended to cover various modifications and equivalent arrangements included within the spirit and scope of the appended claims and equivalents thereof.

