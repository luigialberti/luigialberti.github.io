---
title: "fnc"
collection: software
excerpt: "fnc: an utility to visualize space vectors related to 3-phase systems. Based on PySide6 widgets."
---
<p>
fnc is an utility to visualize space vectors related to 3-phase systems.
It is based on PySide6 widgets.</p>
<p>As an example, the following code evaluate two periods of a
three-phase system curents, considering the foundamental and seventh
order harmonics. The corresponding space vector trjectory is computed
and shown in the widget.
The current wavefors versus time are shown as well, the two representations being
synchronized.</p>

```python
from dolomites import fnc
from PySide6.QtWidgets import QApplication
import sys, numpy as np

app = QApplication([])
win = fnc.fnc_widget()


f  = 50  # the frequncy of the current (Hz)
Im = 100 # the peak value (A)
t  = np.linspace(0,2/f,201) # we take 2 periods

# define the 3-phase quantities
# here we consider the main harmonic and a 7th harmonic
a = Im*np.cos(2*np.pi*f*t)             + 0.2*Im*np.sin(7*2*np.pi*f*t)
b = Im*np.cos(2*np.pi*f*t - 2/3*np.pi) + 0.2*Im*np.sin(7*2*np.pi*f*t- 7*2/3*np.pi)
c = Im*np.cos(2*np.pi*f*t - 4/3*np.pi) + 0.2*Im*np.sin(7*2*np.pi*f*t- 7*4/3*np.pi)

win.add_series(t,a,b,c)
win.show()
```

<p>
    <image src='/images/dolomites/fnc.jpg'/>
</p>
