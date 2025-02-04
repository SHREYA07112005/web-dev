I.	Signal Generation
Purpose:
Sampling Frequency (Fs): Signals are typically continuous, but in digital signal processing (DSP), we work with discrete signals. To convert a continuous signal to a discrete one, we sample it at regular intervals. Here, we sample the signal 500 times per second. This is known as the sampling frequency (Fs). It controls how detailed the signal is captured. As per the Nyquist theorem , the sampling frequency should be at least twice the highest frequency present in the signal to accurately represent it without distortion.
Noisy Signals (y1, y2, y3):
	y1 is a sine wave with a frequency of 10 Hz, contaminated by noise. The randn() function generates random noise, simulating real-world imperfections.
	y2 is a cosine wave with a frequency of 20 Hz, also with noise.
	y3 is a combination of two components: a sine wave at 30 Hz and a cosine wave at 5 Hz, both mixed with noise.


II.	Butterworth Filter Design
Purpose:
A Butterworth bandpass filter is designed that removes unwanted noise and passes only frequencies between 8 Hz and 35 Hz. The Butterworth filter is often used because of its smooth frequency response without ripples in the passband. The function butter(z, wn, 'bandpass') generates a bandpass filter with the given order and frequency range. Butterworth filters are commonly used in DSP because they have a flat response in the passband (minimal distortion) and a smooth transition to the stopband.
 
III.	Visualizing the Frequency Response of the Filter
Purpose:
Magnitude Response Plot: We plot the magnitude response in decibels (dB) to visualize how well the filter isolates the passband (8–35 Hz).
	Frequencies between 8 Hz and 35 Hz will be passed with minimal attenuation (around 0 dB).
	Frequencies outside this range will be attenuated, with values below 0 dB indicating reduced amplitude.


IV.	FFT (Fast Fourier Transform)
Purpose:
The Fast Fourier Transform converts the time-domain signal into its frequency components. This is essential for understanding which frequencies are present in the signal. Both the noisy and filtered signals are transformed using FFT.
	fft(y_noisy, NFFT) computes the FFT of the noisy signal.
	fft(y_filt, NFFT) computes the FFT of the filtered signal.
Single-Sided Amplitude Spectrum: The output of the FFT is complex, so we take the absolute value (abs()) to get the magnitude of each frequency component. We then plot only the positive frequencies (single-sided spectrum).
 
V.	Plotting Time-Domain and Frequency-Domain Signals
Purpose:
Time-Domain Plots: The first and third subplots show the noisy signal and the filtered signal in the time domain, respectively. The filtered signal is expected to be smoother and cleaner than the noisy one.
The single-sided spectrum makes it easier to identify the frequencies present in the signal and their respective amplitudes.
The primary purpose of filtering is to remove unwanted noise or interference from a signal while preserving the essential features. By plotting the FFT of the filtered signal, we can directly visualize how effectively the filter has worked.After filtering, it’s crucial to ensure that the key characteristics of the original signal have been preserved. The FFT allows us to analyse the frequency components of the filtered signal and compare them to the original noisy signal.
