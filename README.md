![logo](logo.png)

**zeus is a pure-Python implementation of the *Ensemble Slice Sampling* method.**

- Fast & Robust *Bayesian Inference*,
- No hand-tuning,
- Excellent performance in terms of autocorrelation time and convergence rate,
- Scale to multiple CPUs without any extra effort.

[![GitHub](https://img.shields.io/badge/GitHub-minaskar%2Fzeus-blue)](https://github.com/minaskar/zeus)
[![Build Status](https://travis-ci.com/minaskar/zeus.svg?token=xnVWRZ3TFg1zxQYQyLs4&branch=master)](https://travis-ci.com/minaskar/zeus)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://github.com/minaskar/zeus/blob/master/LICENSE)
[![Documentation Status](https://readthedocs.org/projects/zeus-mcmc/badge/?version=latest&token=4455dbf495c5a4eaba52de26ac56628aad85eb3eadc90badfd1703d0a819a0f9)](https://zeus-mcmc.readthedocs.io/en/latest/?badge=latest)


## Example

For instance, if you wanted to draw samples from a 10-dimensional Gaussian, you would do something like:

```python
import numpy as np
import zeus

def logp(x, ivar):
    return - 0.5 * np.sum(ivar * x**2.0)

nsteps, nwalkers, ndim = 1000, 100, 10
ivar = 1.0 / np.random.rand(ndim)
start = np.random.rand(ndim)

sampler = zeus.sampler(logp, nwalkers, ndim, args=[ivar])
sampler.run(start, nsteps)
```

## Documentation

Read the docs at [zeus-mcmc.readthedocs.io](https://zeus-mcmc.readthedocs.io)


## Installation

To install zeus using pip run

```bash
pip install zeus-mcmc
```

## Licence

Copyright 2019-2020 Minas Karamanis and contributors.

zeus is free software made available under the GPL-3.0 License. For details see the `LICENSE` file.
