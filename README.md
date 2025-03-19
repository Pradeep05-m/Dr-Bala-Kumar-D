# IDEAL SAMPLING
## AIM
To study and analyze Ideal Sampling. The experiment aims to verify the sampling theorem, analyze spectral characteristics, and understand signal reconstruction.
## TOOLS REQUIRED
Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.
## PROGRAM
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal)
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, reconstructed_signal, 'r--')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```
## OUTPUT WAVEFORM
![image](https://github.com/user-attachments/assets/8e581f12-afa7-4c61-9ea8-f166bb800136)
![image](https://github.com/user-attachments/assets/1ce06990-914b-42ca-8af3-8a0f09ef857d)
![image](https://github.com/user-attachments/assets/d33083ff-9216-4542-b4e7-7ea524ecf1d2)

## RESULT
The result of ideal sampling is a discrete-time signal that retains all the information of the original continuous-time signal is obtained and output is verified.
