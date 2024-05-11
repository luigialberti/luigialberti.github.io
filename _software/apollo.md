---
title: "apollo"
collection: software
excerpt: "apollo: a tool to evaluate self-sensing capability of a synchronous machine."
---
<p>
apollo is a package to elaborate flux-linkage maps of a synchronous machine.
A full description of the underlying algorithm can be found in
<a href='/publication/self-sensing'>this paper</a>.</p>
<p>As an example, the following code evaluate the self-sensing capability
trjectories starting from the flux maps of a motor.</p>

```python
# import apollo
from dolomites import apollo  

# load the data from a file
file_name = 'SynRM_data.txt'  
data = pd.read_csv(file_name, sep='\s+', comment='#', names=["theta_m", "i_d", "i_q", "lambda_d", "lambda_q", "torque"])
mot = apollo.fm(data)
mot.create_maps()

# compute the apparent inductances mot.Ld and mot.Lq
mot.calc_apparent_inductances()

# compute the incremental inductances mot.ldd, mot.ldq, mot.lqd, mot.lqd, mot.lqq, mot.lsigma, mot.ldelta
mot.calc_incremental_inductances(method = 'gradient')

# Compute the mtpa trajectory
# method: choose between "gradient" and "analytical"
mot.calc_MTPA(method = "analytical")

# compute saliency mot.xi and estimation error mot.epsilon
mot.calc_saliency()
mot.calc_sensored_error()

# set the MTPA as reference trajectory
mot.i_d_REF = mot.i_d_MTPA
mot.i_q_REF = mot.i_q_MTPA

# compute sensored trajectory t1
mot.calc_sensored_trajectory()

# compute convergence region t2
Uh = 40
fh = 1000
mot.calc_convergence_region(Uh, fh)
```

<p>
    <image src='/images/dolomites/apollo_2.jpg'/>
</p>
