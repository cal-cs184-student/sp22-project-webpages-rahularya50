# Progressive Photon Mapping
We will implement progressive photon mapping as described in [^1], and then
experiment with other techniques for building and querying photon maps (possibly
ML/neural-network based).

## Problem Description
The project 3 path tracer is inefficient, especially at rendering caustics. To
improve this, we will implement photon mapping. Moreover, photon mapping on
caustic surfaces tends to have a biased result, which we will need to factor
into our approach.

## Goals and Deliverables
We will produce images similar to those from project 3, but with caustics
rendered using a small number of iterations. For example, we may render a
refractive sphere concentrating rays from an area light onto a small region on
the floor, that can be much more efficiently rendered using photon mapping
compared to ray tracing. Our implementation will use CUDA-based path tracing,
and will be "clean-slate", though we may reuse some input/output handling code
from the 184/284 skeleton.

As metrics for success, we will compare the number of samples needed, as well as
overall compute time, in order to achieve a (qualitatively) similar visual
effect or to achieve convergence of the output image below some noise level.

If time allows, we will experiment with alternative ways of representing a
photon map using fewer samples, such as by using them to train a simple ML model
to predict subsequent measurements. We will compare these results with the
standard techniques in terms of the number of rays needed for noise to drop
below a given threshold, the overall amount of computation needed, and the
visual accuracy.

## Schedule
- Week 1: Implement the basic photon mapping algorithm
- Week 2: Implement the the progressive photon algorithm
- Week 3: Implement a novel photon mapping algorithm with deep learning.
- Week 4: Analysis, Paper, and Presentation.

## Resources
In addition to [^1], we will use GPU compute resources from NERSC and
potentially the RISELab that we have access to.

[^1]: T. Hachisuka, S. Ogaki, and H. W. Jensen. 2008. Progressive photon
    mapping. In ACM SIGGRAPH Asia 2008 papers (SIGGRAPH Asia '08). Association
    for Computing Machinery, New York, NY, USA, Article 130, 1–8.
    DOI:https://doi.org/10.1145/1457515.1409083
