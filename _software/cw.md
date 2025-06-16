---
title: "climbing wall"
collection: software
permalink: /software/cw
excerpt: "climbing wall: an open hardware small-scale test bench for electric drives."
---

<p>
climbing-wall is a small-scale test bench designed for teaching and learning
applied control of electrical drives. Its sizes fit in an A4 paper size
(20x28 cm). It has been designed with sustainability in mind, so that
renewable materials have been adopted whenever possible:</p>
<p>
    <image src='/images/dolomites/cw_2.jpeg' />
</p>

<p>
  In the previous picture it is equipped with:
</p>
<ul>
<li>a synchronous PM motor (with both hall sensors and encoder)</li>
<li>a C2000 F28069M LaunchPad microprocessor board</li>
<li>a DRV8305 LaunchXL inverter board</li>
</ul>

<p>It can be programmed using C-code or model base language
(such as plecs/simulink). As an example, the following code run a 3-phase inverter in open loop scalar
control.</p>

<p>
    <image src='/images/dolomites/cw_plecs.jpeg' />
</p>

<p>
Being an open-hardware project, a description of the components to realize it
is available in the dolomites repository.

If you are looking for help in manufacturing it, I can share some options about
companies able to provide turnkey solutions and a ready-to-start bundle.
In such a case, please contact this dedicated e-mail:
<a href='mailto:cw.dolomites@gmail.com'>cw.dolomites@gmail.com</a>
</p>
