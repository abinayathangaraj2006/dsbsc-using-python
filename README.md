Aim

To implement and analyze (DSBSC) using Python's NumPy and Matplotlib libraries.

Apparatus Required 1.Software: Python with NumPy and Matplotlib libraries

2.Hardware: Personal Computer

Theory

DSB-SC (Double Sideband Suppressed Carrier) is a type of amplitude modulation where the carrier wave is suppressed, and only the two sidebands (which contain the actual information) are transmitted. This saves power and reduces bandwidth waste compared to standard AM.

In DSB-SC, the amplitude of the carrier is still varied according to the message signal, but the carrier itself is not transmitted.

Algorithm 1.Initialize Parameters: Set the values for carrier frequency, message frequency and sampling frequency.

2.Generate Time Axis: Create a time vector for the signal duration.

3.Generate Message Signal: Define the message signal as a cosine wave.

4.Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.

5.Generate AM Signal: Apply the DSBSC modulation formula to obtain the modulated signal.

6.Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.
program :
import numpy as np
import matplotlib.pyplot as plt
Am=4.4
Fm=334
Ac=8.8
Fs=3340
Fc=33400

t=np.arange(0,2/Fm,1/Fs)

m=Am*np.cos(2*np.pi*Fm*t)
plt.subplot(3,1,1)
plt.plot(t,m)
c=Ac*np.cos(2*np.pi*Fc*t)
plt.subplot(3,1,2)
plt.plot(t,c)
s1 = (Ac + m) * np.cos(2 * np.pi * Fc * t)
s2=(Ac-m)*np.cos(2*np.pi*Fc*t)
s=s1-s2
plt.subplot(3,1,3)
plt.plot(t,s)

outputwaveform :
<img width="743" height="549" alt="Screenshot 2025-12-04 185204" src="https://github.com/user-attachments/assets/1bdd842b-5406-4aa7-bcdc-2632cc534610" />

tabulation:
![WhatsApp Image 2025-12-04 at 18 54 59_16845ba0](https://github.com/user-attachments/assets/ab55d49e-10dd-44f4-b583-580b462ad126)

Result

The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.




