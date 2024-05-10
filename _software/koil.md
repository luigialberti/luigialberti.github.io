---
title: "koil"
collection: software
excerpt: "koil: a tool for the synthesis and the analysis of a winding."
---
<p>
koil allows both the synthesis and the analysis of a winding. In the synthesis, given the main winding parameters, i.e. the number of phase m, the number of slots Q and the number of pole pairs p, a symmetrical and balanced winding is computed. In the analysis, the user can insert coil by coil any kind of winding, setting any number of phases and conductors.</p>
<p>As an example, the following code compute a 12-slot 10-pole winding comparing the winding factor for equal and unequal slot distribution.</p>

<p>
  <pre><code class="language-python">
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

# let ask koil to compute the symmetrical and balanced winding
w.compute_winding(m,Q,p,single_layer=True)

# compute the winding factors for equally distributed coils
for _w in w.windings:
    print(_w.get_kw(nu=5))
print('----')

# compute the winding factors for unequal distributed slots
for _w in w.windings:
    print(_w.get_kw(nu=5,angles=angles))

		0.9659258262890683
		0.9659258262890683
		0.9659258262890683
		----
		1.0
		1.0
		1.0
  </code></pre>
  </p>
  <p>
    <image src='/images/dolomites/koil.jpeg' />
</p>
