
The **sampling theorem**, also known as the **Nyquist-Shannon sampling theorem**, is a fundamental principle in digital signal processing. It states that a continuous signal can be fully reconstructed from its samples if it is sampled at a rate that is at least twice its highest frequency component. This minimum sampling rate is called the **Nyquist rate**.

### Key Concepts of the Sampling Theorem

1. **Signal Bandwidth**:
   - The theorem applies to **band-limited signals**, which means signals with a maximum frequency component \( f_{\text{max}} \). For example, if the highest frequency in a signal is 5 kHz, the signal is band-limited to 5 kHz.

2. **Nyquist Rate**:
   - According to the sampling theorem, the sampling rate \( f_s \) must be at least twice the maximum frequency \( f_{\text{max}} \):
     $$
     f_s \geq 2 \cdot f_{\text{max}}
     $$
   - This minimum rate $$2 \cdot f_{\text{max}}$$ is called the **Nyquist rate**.

3. **Aliasing**:
   - If a signal is sampled below the Nyquist rate, **aliasing** occurs, where higher frequencies in the signal are "folded" into lower frequencies, distorting the reconstructed signal.
   - Aliasing happens because, with a low sampling rate, different frequencies become indistinguishable from each other when sampled.

### How the Sampling Theorem Works

- When sampling a continuous-time signal, each sample captures the signal's value at discrete points in time.
- Provided the sampling rate is sufficient (i.e., at least the Nyquist rate), these discrete points contain enough information to reconstruct the original continuous signal without loss of information.
- Reconstruction typically involves passing the sampled signal through a **low-pass filter**, which removes high-frequency components introduced during sampling and restores the original continuous waveform.

### Example

- Suppose you have a sound signal with frequencies up to 4 kHz. According to the sampling theorem, to sample this sound without aliasing, the sampling rate should be at least:
  $$
  f_s \geq 2 \times 4 \, \text{kHz} = 8 \, \text{kHz}
  $$
- Practically, you might sample slightly above the Nyquist rate (e.g., at 8.8 kHz) to account for any imperfections in filtering.

### Importance

The sampling theorem is crucial in digital audio, telecommunications, and data acquisition systems, where analog signals must be sampled and converted to digital formats. By ensuring the sampling rate meets or exceeds the Nyquist rate, systems can avoid aliasing and accurately represent analog signals in digital form.

Under appropriate "slowness" conditions for $x(t)$ we have:
$$
x(t) = \sum^{\infty}_{n = -\infty}x[n]sinc\left( \frac{t-nT_s}{T_s}\right)
$$

The **sampling theorem** has a direct mathematical relationship with the **sinc function** due to the role the sinc function plays in reconstructing a continuous-time signal from its discrete samples.

### Sampling and the Sinc Function

![[Pasted image 20241110154542.png]]


1. **Ideal Reconstruction of a Signal**:
   - According to the sampling theorem, if a continuous signal is band-limited and sampled at a rate at least twice its highest frequency (the Nyquist rate), it can be perfectly reconstructed from its samples.
   - This reconstruction is achieved by interpolating between the discrete samples to recreate the original signal.

2. **Role of the Sinc Function in Reconstruction**:
   - The **sinc function**, defined as:
     $$
     \text{sinc}(x) = \frac{\sin(\pi x)}{\pi x}
     $$
     is the ideal interpolation function for reconstructing a continuous signal from its samples.
   - When each sample of the signal is multiplied by a shifted sinc function and then summed up, the original continuous signal is perfectly reconstructed. This is known as **sinc interpolation**.

3. **Reconstruction Formula**:
   - The original continuous signal \( x(t) \) can be reconstructed from its samples \( x[n] \) taken at times \( t = nT \) (where \( T \) is the sampling interval, so the sampling rate \( f_s = \frac{1}{T} \)) using the following formula:
     $$
     x(t) = \sum_{n=-\infty}^{\infty} x[n] \, \text{sinc} \left( \frac{t - nT}{T} \right)
     $$
   - Here, $( x[n] )$ represents each sample value, and the **sinc function** provides the smooth interpolation between the sample points.
   - Each sinc function centered at a sample point $( nT )$ has zero crossings at all other sample points, meaning that each sinc function contributes only at its own sample point, preserving the values of the discrete samples.

![[Pasted image 20241110154613.png]]

4. **Frequency Domain Insight**:
   - In the frequency domain, sampling a signal corresponds to repeating its spectrum at intervals of the sampling frequency $( f_s )$.
   - The sinc function is the inverse Fourier transform of an ideal low-pass filter, which means it perfectly passes frequencies up to the Nyquist limit and blocks higher frequencies.
   - This property of the sinc function in the frequency domain aligns with the requirement of the sampling theorem to avoid aliasing by restricting the signal’s frequency content to below the Nyquist rate.
![[Pasted image 20241110154641.png]]


### Why the Sinc Function Is Important

- **Ideal Low-Pass Filter**: The sinc function acts as an ideal low-pass filter in the reconstruction process, ensuring that only the original frequency components of the signal are retained.
- **Smooth Interpolation**: The sinc function provides a smooth transition between samples, avoiding sharp transitions or distortions, and enabling a continuous reconstruction from discrete points.
- **Mathematical Foundation of Sampling**: The sinc-based reconstruction formula is central to digital signal processing theory, establishing a rigorous mathematical foundation for the sampling theorem.

In summary, the sinc function plays a critical role in implementing the sampling theorem’s promise of perfect reconstruction, serving as the ideal interpolation function that allows a continuous band-limited signal to be accurately recreated from its discrete samples.