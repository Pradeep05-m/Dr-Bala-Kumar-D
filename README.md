# IDEAL SAMPLING
## AIM
To study and analyze Ideal Sampling. The experiment aims to verify the sampling theorem, analyze spectral characteristics, and understand signal reconstruction.
## TOOLS REQUIRED
Personal computer installed with SCILAB
## PROGRAM
```
clf; // Clear the current figure
t = 0:0.001:1; // Time vector from 0 to 1 with a small step
f = 5; // Frequency of the sine wave (5 Hz)
x = sin(2 * %pi * f * t); // Continuous-time signal (sine wave)
// Plot the continuous-time signal
subplot(5,1,1);
plot(t, x);
title('Continuous-time Signal');
xlabel('Time (s)');
ylabel('Amplitude');
legend('Continuous-time Signal with freq 5Hz');
// Step 2: Sample the signal at different sampling rates10
fs1 = 20; // Sampling frequency (20 Hz)
ts1 = 0:1/fs1:1; // Sampling times
xs1 = sin(2 * %pi * f * ts1); // Sampled signal
fs2 = 10; // Sampling frequency (10 Hz)
ts2 = 0:1/fs2:1; // Sampling times
xs2 = sin(2 * %pi * f * ts2); // Sampled signal
fs3 = 6; // Undersampling frequency (6 Hz, which is less than twice the frequency of the signal)
ts3 = 0:1/fs3:1; // Sampling times
xs3 = sin(2 * %pi * f * ts3); // Sampled signal
// Plot the sampled signals
subplot(5,1,2);
plot(t, x, 'b'); // Original continuous-time signal
plot2d(ts1, xs1, style=-4, rect=[0, -1.5, 1, 1.5]); // Sampled signal at 20 Hz
plot2d(ts2, xs2, style=-5, rect=[0, -1.5, 1, 1.5]); // Sampled signal at 10 Hz
plot2d(ts3, xs3, style=-6, rect=[0, -1.5, 1, 1.5]); // Sampled signal at 6 Hz
title('Sampled Signals');
xlabel('Time (s)');
ylabel('Amplitude');
legend('Continuous-time', 'Sampled at 20 Hz', 'Sampled at 10 Hz', 'Sampled at 6 Hz');
// Step 3: Reconstruct the signal from samples using interpolation
// Plot the reconstructed signals
xr1 = interp1(ts1, xs1, t, 'linear'); // Reconstructed signal from 20 Hz samples
xr2 = interp1(ts2, xs2, t, 'linear'); // Reconstructed signal from 10 Hz samples
xr3 = interp1(ts3, xs3, t, 'linear'); // Reconstructed signal from 6 Hz samples

subplot(5,1,3);
plot(t, x, 'b'); // Original continuous-time signal
plot2d(t, xr1, style=2, rect=[0, -1.5, 1, 1.5]); // Reconstructed signal from 20 Hz samples
subplot(5,1,4);
plot2d(t, xr2, style=3, rect=[0, -1.5, 1, 1.5]); // Reconstructed signal from 10 Hz samples
subplot(5,1,5);
plot2d(t, xr3, style=4, rect=[0, -1.5, 1, 1.5]); // Reconstructed signal from 6 Hz samples
title('Reconstructed Signals');
xlabel('Time (s)');
ylabel('Amplitude');
legend('Continuous-time', 'Reconstructed from 20 Hz samples','Reconstructed from 10 Hz samples','Reconstructed from 6 Hz samples');
```
## OUTPUT WAVEFORM
![WhatsApp Image 2025-03-18 at 11 13 37_51501a32](https://github.com/user-attachments/assets/3e43da16-4181-4c80-99c0-fac285e8a5af)
![WhatsApp Image 2025-03-18 at 11 13 44_34ddc6a5](https://github.com/user-attachments/assets/cfc13ce2-6114-4af7-8e0e-44cf95aca8fb)
![WhatsApp Image 2025-03-18 at 11 14 11_3dc7face](https://github.com/user-attachments/assets/84d8742d-102f-4a74-9de0-7276cc27fc60)




## RESULT
The result of ideal sampling is a discrete-time signal that retains all the information of the original continuous-time signal is obtained and output is verified.
