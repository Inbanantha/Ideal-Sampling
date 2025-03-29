# Ideal-Sampling
AIM:-
     
     To perform ideal sampling (impulse sampling) of a continuous signal and reconstruct the signal using resampling techniques.

TOOLS REQUIRED:-

    Google Colab

    Python 3

    NumPy

    Matplotlib

    SciPy

PROGRAM:-

    #Impulse Sampling

    import numpy as np

    import matplotlib.pyplot as plt

    from scipy.signal import resample

    fs = 100

    t = np.arange(0, 1, 1/fs) 

    f = 5

    signal = np.sin(2 * np.pi * f * t)

    plt.figure(figsize=(10, 4))

    plt.plot(t, signal, label='Continuous Signal')

    plt.title('Continuous Signal (fs = 100 Hz)')
  
    plt.xlabel('Time [s]')

    plt.ylabel('Amplitude')

    plt.grid(True)

    plt.legend()

    plt.show()

    t_sampled = np.arange(0, 1, 1/fs)

    signal_sampled = np.sin(2 * np.pi * f * t_sampled)

    plt.figure(figsize=(10, 4))

    plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

    plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')

    plt.title('Sampling of Continuous Signal (fs = 100 Hz)')

    plt.xlabel('Time [s]')

    plt.ylabel('Amplitude')

    plt.grid(True)

    plt.legend()

    plt.show()

    reconstructed_signal = resample(signal_sampled, len(t))

    plt.figure(figsize=(10, 4))

    plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

    plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')

    plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')

    plt.xlabel('Time [s]')

    plt.ylabel('Amplitude')

    plt.grid(True)

    plt.legend()

    plt.show()


OUTPUT WAVEFORM:-
    ![image](https://github.com/user-attachments/assets/b648cad2-3d2a-40d4-bf65-a5421eb450a7)



RESULT:-
    
    
    The ideal sampling (impulse sampling) of a continuous signal was successfully performed and visualized. The reconstructed signal closely matches the original continuous-time signal, demonstrating effective resampling.
