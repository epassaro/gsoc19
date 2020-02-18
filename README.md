# Ezequiel A. Pássaro

**Project:** ["Expansion of the TARDIS Atomic Database"](https://summerofcode.withgoogle.com/archive/2019/projects/5344591031566336/) <br>
**Organization:** The Python Software Foundation <br>
**Sub-organization:** TARDIS <br>

---

## Summary

TARDIS is a Monte Carlo radiative transfer code for simulating supernovae spectra. The associated package _Carsus_ retrieves atomic data from multiple sources and stores it into an SQL database. It also takes care of making atomic files suitables for TARDIS. 

During the last three months I've been working alongside the TARDIS team. It was an incredible opportunity to learn about open source software development and improving my coding skills.

The work I did on these two packages during this summer can be summarized in the following way:

<br>

## 1. List of merged pull requests

- **Making TARDIS available for the Anaconda distribution.** Ease of installation is always desired, and the _Anaconda_ distribution is a convenient way of distributing scientific software. My first task was to package TARDIS following the `conda-forge` guidelines. This was specially useful because allowed me to know more about the TARDIS dependencies.

    _Pull requests: [#7934](https://github.com/conda-forge/staged-recipes/pull/7934) [#930](https://github.com/tardis-sn/tardis/pull/930)_

- **Porting Carsus to Python 3.** _Carsus_ was written in Python legacy before GSoC 2019. Migrating to _Python 3_ was an important and time consuming task. It was specially difficult because updating dependencies introduced small bugs hard to trace ("the devil is in the details"). Also was extremely useful because I got familar with the entire _Carsus_ codebase.
    
    _Pull requests: [#118](https://github.com/tardis-sn/carsus/pull/118) [#131](https://github.com/tardis-sn/carsus/pull/131) [#132](https://github.com/tardis-sn/carsus/pull/132) [#137](https://github.com/tardis-sn/carsus/pull/137)_

- **Continuous Integration.** Set up a pipeline in Travis CI for _Carsus_. It was my first approach to the CI/CD technologies.

    _Pull requests: [#120](https://github.com/tardis-sn/carsus/pull/120) [#123](https://github.com/tardis-sn/carsus/pull/123)_

- **Parsers for the CMFGEN atomic database.** The CMFGEN database consists of thousands of text files with atomic measurements. I focused on parsing three different file types: _energy levels & oscillator strengths_, _collisional strengths_ and _photoionization cross-sections_. Also, the first two types have ~5 slighty different formats. This code was mostly written using the _Pandas_ library. Includes unit tests and integration with the CI pipeline.

    _Pull requests: [#124](https://github.com/tardis-sn/carsus/pull/124) [#142](https://github.com/tardis-sn/carsus/pull/142) [#143](https://github.com/tardis-sn/carsus/pull/143) [#1](https://github.com/tardis-sn/carsus-refdata/pull/1)_
  
- **New parsers for NIST and Knox's Long zeta.** At this point the idea was to allow _Carsus_ to create TARDIS atomic files without storing data in a SQL database. These new parsers can read and dump data straight to HDF5.  

    _Pull requests: [#144](https://github.com/tardis-sn/carsus/pull/144) [#145](https://github.com/tardis-sn/carsus/pull/145)_

- **Up-to-date Carsus documentation.**

    _Pull requests: [#125](https://github.com/tardis-sn/carsus/pull/125) [#135](https://github.com/tardis-sn/carsus/pull/135)_
    
- **Other fixes and improvements.**
   
   _Pull requests: [#133](https://github.com/tardis-sn/carsus/pull/133) [#147](https://github.com/tardis-sn/carsus/pull/147) [#149](https://github.com/tardis-sn/carsus/pull/149)_

<br>

## 2. List of open pull requests*

- **New module for creating TARDIS atomic files.** This module retrieves atomic data with the new parsers and creates TARDIS atomic files using only _Pandas_. Files made with this module are consistent with the ones created from an SQL database.

    _Pull requests: [#148](https://github.com/tardis-sn/carsus/pull/148)_

<br>

## 3. What's left to do?

In order to have atomic files identical to the ones obtained with the _Carsus_ SQL database, we need to add the Chianti source.

<br>

## Other links

- Carsus documentation: [https://carsus.readthedocs.io](https://carsus.readthedocs.io)

- Python GSoC 2019 blog: [https://blogs.python-gsoc.org/en/epassaros-blog/](https://blogs.python-gsoc.org/en/epassaros-blog/)

<br>

---

\* Pull requests still open at 26/8/2019. A complete list of PRs made during the entire GSoC 2019 period can be found [here](https://github.com/pulls?q=is%3Apr+created%3A%3E2019-02-01+created%3A%3C2010-09-03+author%3Aepassaro+user%3Atardis-sn+user%3Aconda-forge).
