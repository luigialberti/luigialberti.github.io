---
title: "koil"
collection: software
excerpt: "koil: a tool for the synthesis and the analysis of a winding."
---
<p>
koil allows both the synthesis and the analysis of a winding. In the synthesis, given the main winding parameters, i.e. the number of phases m, the number of slots Q and the number of pole pairs p, a symmetrical and balanced winding is computed. In the analysis, the user can enter any kind of winding coil by coil, setting any number of phases and conductors. A full description of the underlying algorithm can be found in
<a href='/publication/multilayer-windings'>this</a> and
<a href='/publication/koil'>this</a> paper.</p>
<p>As an example, the following code computes a 12-slot 10-pole winding comparing the winding factor for equal and unequal slot distribution.</p>

```python
w = koil.m_phase_winding()
m = 3   # number of phases
Q = 12  # number of slots
p = 5   # number of pole pairs

# create specific angles for the slots
# mechanical radians have to be defined
angles = []
for x in range(0, 6):
    angles.append(math.pi/3*x-math.pi/10)
    angles.append(math.pi/3*x+math.pi/10)

# let's ask koil to compute the symmetrical and balanced winding
w.compute_winding(m,Q,p,single_layer=True)

# compute the winding factors for equally distributed coils
for _w in w.windings:
    print(_w.get_kw(nu=5))
print('----')

# compute the winding factors for unequally distributed slots
for _w in w.windings:
    print(_w.get_kw(nu=5,angles=angles))
```

<p>The code above produces:</p>

```python
0.9659258262890683
0.9659258262890683
0.9659258262890683
----
1.0
1.0
1.0
```
<p>
    <image src='/images/dolomites/koil.jpeg' />
</p>
