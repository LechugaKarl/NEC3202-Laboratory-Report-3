## NEC3202-Laboratory-Report-3
Lab Report 3 ( Experiments 15-20 )
________________________________________________________________________________________________________________________________________________________________________________________________________________________
<details>
<summary>EXPERIMENT #15 - Amplitude Shift Keying (ASK) </summary>

INTRODUCTION:

Sharing a transmission medium is a core requirement in telecommunications. Without the ability to multiplex, only one user could occupy a channel at a given time, rendering modern mobile networks and broadcasting impossible. Frequency Division Multiplexing (FDM) solves this by assigning each user a specific portion of the radio frequency spectrum. When digital data is transmitted using FDM through the variation of a carrier wave's power, the process is known as Amplitude Shift Keying (ASK). This scheme represents a digital one by the presence of a carrier and a digital zero by its absence, making it a fundamental building block for optical fiber and simple radio systems.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Implement ASK Generation: To use a digital data stream to switch a high-frequency carrier wave on and off.
- Analyze FDM Principles: To understand how digital information is superimposed onto a specific frequency band to allow for channel sharing.
- Observe Signal Bandwidth: To evaluate the spectral requirements of an ASK signal compared to the baseband digital data.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

In this session, we explored how digital logic can control a high-frequency sine wave to prepare it for transmission over a shared medium. We observed that ASK is essentially a form of digital AM. When the data bit is high, the carrier is allowed to pass to the output; when the bit is low, the carrier is suppressed. This creates a very clear visual distinction on the oscilloscope, often called on-off keying. We learned that while this method is simple to implement, it is still vulnerable to the same amplitude noise that affects analog AM.
The discussion on Time Division Multiplexing (TDM) versus Frequency Division Multiplexing (FDM) highlighted critical engineering trade-offs. While TDM requires high bit-rates that can lead to signal smearing, FDM allows for continuous transmission by occupying a specific frequency slot. By using ASK, we can move digital messages away from baseband frequencies and into higher slots where the antenna or cable can transmit them more efficiently. This experiment clarifies how digital pulses are packaged for real-world environments where many signals must exist simultaneously without interference.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

The experiment proves that Amplitude Shift Keying is an effective method for translating digital data into a frequency-domain format suitable for FDM. While the simplicity of ASK makes it easy to generate and detect, it serves as a gateway to more complex keying schemes. Understanding how to vary a carrier’s amplitude based on binary logic is essential for anyone working with fiber optics or basic wireless links. Ultimately, ASK demonstrates how we can successfully share a physical channel by shifting our data into the radio frequency spectrum.

</details>

<details>
<summary>EXPERIMENT #16 -Frequency Shift Keying (FSK) </summary>

INTRODUCTION:

Frequency Shift Keying is the digital version of FM. Instead of a continuous change in frequency, the carrier jumps between two specific frequencies to represent a logic one and a logic zero. This method is widely used in low-speed data links and early computer modems because it is more resistant to noise than Amplitude Shift Keying. By keeping the amplitude constant, the signal can survive interference that would normally corrupt an ASK transmission.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Generate FSK Signals: Use a binary data stream to switch a VCO between two set frequencies.
- Observe Frequency Deviation: Measure the difference between the mark (logic one) and space (logic zero) frequencies.
- Analyze Noise Resistance: Compare the constant envelope of an FSK signal to the variable amplitude of ASK.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

We observed that FSK is very similar to the FM experiments we did earlier, but with a square wave input that creates sharp jumps in frequency. The result is a signal that never changes in volume but shifts its "pitch" constantly. This is a huge benefit in the real world because a receiver can use a limiter to cut off any noise spikes without losing the frequency-based data. We learned that the wider the gap between the two frequencies, the easier it is for the receiver to tell them apart, though this requires more bandwidth.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

The experiment confirms that FSK is a robust digital modulation scheme, particularly effective in environments where amplitude stability is unreliable. By shifting between two discrete frequencies, we successfully demonstrated a system that is immune to the "flicker" and noise that plagues ASK. While it requires more bandwidth to accommodate two carrier frequencies, the trade-off is a significantly more reliable data link. This makes FSK the ideal choice for legacy hardware and low-speed telemetry where accuracy is prioritized over spectral efficiency.

</details>

<details>
<summary>EXPERIMENT #17 - Binary Phase Shift Keying (PSK) </summary>

INTRODUCTION:

Phase Shift Keying is one of the most efficient ways to send digital data. Instead of changing the frequency or amplitude, we change the phase of the carrier wave. For a logic one, the wave starts at zero degrees; for a logic zero, the wave is flipped 180 degrees. This allows for high-speed transmission because the carrier frequency stays constant, making it easier to fit many users into a crowded frequency spectrum.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Generate BPSK Signals: Use a balanced modulator to create Binary Phase Shift Keying by inverting the carrier phase.
- Identify Phase Reversals: Locate the exact points in the waveform where the phase flips in response to data changes.
- Study Constellation Points: Understand how phase shifts represent binary states in a polar coordinate system.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

In this lab, we saw that a phase shift looks like a sudden "glitch" or reversal in the sine wave. When the digital bit changes, the wave instantly flips upside down. This is technically a form of DSBSC modulation where the message is the digital data. We learned that while PSK is very efficient, the receiver must be perfectly synchronized with the transmitter to know exactly when a phase has shifted. This makes the hardware more complex than ASK or FSK, but the high data rates make it worth the effort.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

This lab demonstrates that phase modulation is a highly efficient way to utilize the frequency spectrum. By flipping the carrier’s phase by 180°, we can represent binary data without changing the frequency or amplitude. We proved that PSK is more "spectrally compact" than FSK, though it demands a much more sophisticated receiver to track the carrier's phase. The experiment confirms that PSK is a foundational technology for high-speed digital links, provided that the transmitter and receiver remain perfectly synchronized.

</details>

<details>
<summary>EXPERIMENT #18 - Quadrature Phase Shift Keying (QPSK) </summary>

INTRODUCTION:

Quadrature Phase Shift Keying (QPSK) takes PSK a step further by shifting the phase into four possible positions instead of two. This allows us to send two bits of information for every single change in the carrier wave. By using both the Sine and Cosine versions of a carrier (which are 90 degrees apart), we can double the data rate without increasing the bandwidth of the channel.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Implement Quadrature Modulation: Combine two separate BPSK signals that are 90 degrees out of phase.
- Analyze Bit Mapping: Observe how pairs of bits (dibits) correspond to specific phase angles.
- Evaluate Spectral Efficiency: Understand why QPSK is preferred for satellite and cable communications.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

QPSK felt like a massive jump in complexity. We learned that by using two carriers that are "orthogonal" (at a right angle to each other), they don't interfere. This allows us to transmit twice as much data in the same amount of space. We saw that the signal now has four distinct phase states: 45, 135, 225, and 315 degrees. This experiment proved that we can manipulate the "shape" of a wave in complex ways to maximize how much information a channel can carry.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

The successful implementation of QPSK proves that we can double the data rate of a communication channel without increasing the required bandwidth. By using "orthogonal" sine and cosine carriers, we verified that four distinct phase states can represent two bits of data simultaneously. This experiment highlights the concept of spectral efficiency a cornerstone of modern satellite and cellular engineering showing that complex mathematical mapping can overcome the physical limits of a narrow channel.

</details>

<details>
<summary>EXPERIMENT #19 - DSSS modulation and demodulation </summary>

INTRODUCTION:

Direct Sequence Spread Spectrum (DSSS) is a sophisticated modulation technique used to improve signal security and resistance to interference. Instead of transmitting a narrow-band signal, DSSS "spreads" the message across a much wider bandwidth. This is achieved by multiplying the digital message with a high-speed pseudo-noise (PN) code. To an unintended receiver, the signal looks like low-level background noise. However, a receiver with the matching PN code can "despread" the signal, recovering the original message while effectively canceling out narrow-band interference.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Generate a DSSS Signal: Use a Multiplier module to combine a low-bitrate message with a high-speed PN sequence.
- Observe Spectral Spreading: Analyze how the multiplication process widens the signal's bandwidth on the frequency spectrum.
- Implement Demodulation: Use a second PN sequence generator at the receiver to despread the signal and recover the original data.
- Evaluate Interference Immunity: Observe how the despreading process rejects narrow-band noise that was added during transmission.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

The most fascinating part of this experiment is seeing the message signal seemingly disappear into the noise. When we multiplied the data by the high-speed PN code, the resulting bits became so fast that the signal's energy was smeared across a wide range of frequencies. We learned that the "Processing Gain" of the system depends on how much faster the PN code is than the message.
During demodulation, the importance of synchronization became clear. If the receiver's PN code is even slightly out of alignment with the transmitter's code, the message cannot be recovered. However, once synchronized, the system showed an incredible ability to ignore "jamming" signals. While a standard FM or AM signal would be buried by a strong interference tone, the DSSS receiver spread that tone out and squeezed the message back into its original narrow band. This confirms why DSSS is the backbone of GPS and secure military communications.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

This experiment confirms that DSSS is an elite method for secure and robust communication. We successfully demonstrated that spreading a signal makes it difficult to intercept and remarkably resilient to intentional or accidental interference. The lab proves that by using complex coding sequences, we can trade bandwidth for signal to noise performance, a principle that defines modern high-security wireless networks.

</details>

<details>
<summary>EXPERIMENT #20 - Undersampling in SDR (software defined radio) </summary>

INTRODUCTION:

Traditional radio receivers rely on complex analog "mixing" stages to shift high-frequency signals down to a range that can be processed. Software Defined Radio (SDR) simplifies this by using Undersampling. By intentionally violating the standard Nyquist rule (sampling at less than twice the carrier frequency, but more than twice the message bandwidth), we can use aliasing to our advantage. This technique allows a high-frequency signal to be "folded" down directly into the baseband, where it can be demodulated using software algorithms rather than heavy hardware.

![Image Alt]()

________________________________________________________________________________________________________________________________________________________________________________________________________________________

OBJECTIVES:

- Model a Bandwidth-Limited Signal: Setup a high-frequency carrier modulated by a low-frequency message.
- Implement Undersampling: Configure the sampling clock to a specific frequency that intentionally causes the signal alias to appear at baseband.
- Recover the Message: Use a low-pass filter to isolate the down-converted alias from other sampling products.
- Analyze Mismatches: Investigate how slight errors in the sampling frequency affect the pitch and clarity of the recovered message.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

BLOCK DIAGRAM : 
![Image Alt]()

OUTPUT:

![Image Alt]()

LEARNINGS:

This lab turned the concept of "aliasing" from a mistake into a powerful tool. Usually, we are told that aliasing ruins a signal, but here we saw that if you know exactly where the signal is in the spectrum, you can "target" an alias to fall exactly where you want it. By sampling a high-frequency carrier at a lower, calculated rate, we effectively performed down-conversion without using a single analog mixer or local oscillator.
We also learned that the precision of the sampling clock is non-negotiable in SDR. When we intentionally shifted the sampling frequency, the recovered message began to distort or shift in frequency. This taught us that while SDR reduces the amount of analog hardware needed, it places a massive burden of accuracy on the digital clock and the software filters. Seeing a high-frequency signal get "tamed" into a simple audio sinewave using only a sampler and a filter was a perfect demonstration of how modern smartphones and versatile radios function today.
________________________________________________________________________________________________________________________________________________________________________________________________________________________

CONCLUSION:

Experiment 20 proves that Undersampling is a highly efficient bridge between the analog and digital worlds. It allows us to process high-frequency signals using relatively slow, low-cost digital components. By successfully recovering a message through intentional aliasing, we validated the core principle of Software Defined Radio: moving complexity from hardware into software. This experiment confirms that as long as we respect the signal's bandwidth, the carrier frequency itself no longer limits our ability to digitize information.

</details>
