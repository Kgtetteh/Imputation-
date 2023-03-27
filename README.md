# Imputation-
Dealing with missing values

import numpy as np 
import scipy as sc 
import matplotlib.pyplot as plt
import math 
fs = 200
t = np.arange(0, 5, 1/fs)
a1 = 1
a2 = 0.5
a3 = 0.2
f1 = 1.333
f2 = 1.667
f3 = 2.500

W1 = a1 * np.sin(2 * np.pi * f1 * t)
W2 = a2 * np.sin(2 * np.pi * f2 * t + np.pi/2)
W3 = a3 * np.sin(2 * np.pi * f3 * t + np.pi)
y = W1 + W2 + W3
fig, axs = plt.subplots(5, 5, figsize=(15, 15), sharex=True, sharey=True)
a_values = np.linspace(0.5,1.0, 25)
for i, a in enumerate(a_values):

    W1 = a1 * np.sin(2 * np.pi * f1 * t)
    W2 = a2 * np.sin(2 * np.pi * f2 * t + np.pi/2)
    W3 = a3 * np.sin(2 * np.pi * f3 * t + np.pi)
    y = W1 + W2 + W3

    row_idx = i // 5
    col_idx = i % 5
    axs[row_idx, col_idx].plot(t, y)
fig.supxlabel('Time (s)')
fig.supylabel('Amplitude')
fig.tight_layout(rect=[0, 0.03, 1, 0.95])
plt.show() 
