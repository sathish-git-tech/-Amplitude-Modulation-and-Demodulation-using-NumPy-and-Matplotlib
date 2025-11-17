# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

# __Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

# __Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

# __Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


# __Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

# __program__:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

A_c = 1.0
f_c = 100
f_m = 5
A_m = 0.5
sampling_frequency = 1000
duration = 1

t = np.linspace(0, duration, int(sampling_frequency * duration))

m_t = A_m * np.cos(2 * np.pi * f_m * t)
c_t = A_c * np.cos(2 * np.pi * f_c * t)

s_t = (1 + m_t) * c_t
analytic_signal = hilbert(s_t)
envelope = np.abs(analytic_signal)
demodulated_message = (envelope - A_c) / A_m
plt.figure(figsize=(12, 10))
plt.subplot(4, 1, 1)
plt.plot(t, m_t)
plt.title('Original Message Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

plt.subplot(4, 1, 2)
plt.plot(t, c_t)
plt.title('Carrier Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

plt.subplot(4, 1, 3)
plt.plot(t, s_t)
plt.title('Amplitude Modulated (AM) Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

plt.subplot(4, 1, 4)
plt.plot(t, demodulated_message)
plt.title('Demodulated Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.tight_layout()
plt.show()
```
 # __Output__:

<img width="1091" height="866" alt="Screenshot 2025-11-17 202721" src="https://github.com/user-attachments/assets/5c609d90-e3c8-4434-a329-5eb278fafea9" />

# __Result__:

Thus the AM demodulation and modulation is verified using python successfully.
