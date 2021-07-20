# NiTransforms
[![Deps & CI](https://github.com/poldracklab/nitransforms/actions/workflows/travis.yml/badge.svg)](https://github.com/poldracklab/nitransforms/actions/workflows/travis.yml)
[![CircleCI](https://circleci.com/gh/poldracklab/nitransforms.svg?style=svg)](https://circleci.com/gh/poldracklab/nitransforms)
[![codecov](https://codecov.io/gh/poldracklab/nitransforms/branch/master/graph/badge.svg)](https://codecov.io/gh/poldracklab/nitransforms)
[![doi](https://img.shields.io/badge/doi-10.31219%2Fosf.io%2F8aq7b-blue.svg)](https://doi.org/10.31219/osf.io/8aq7b)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/poldracklab/nitransforms/master?filepath=docs%2Fnotebooks%2F)
[![Docs](https://readthedocs.org/projects/nitransforms/badge/?version=latest)](http://nitransforms.readthedocs.io/en/latest/?badge=latest)

A development repo for [nipy/nibabel#656](https://github.com/nipy/nibabel/pull/656)

## About
Spatial transforms formalize mappings between coordinates of objects in biomedical images.
Transforms typically are the outcome of image registration methodologies, which estimate
the alignment between two images.
Image registration is a prominent task present in nearly all standard image processing
and analysis pipelines.
The proliferation of software implementations of image registration methodologies has
resulted in a spread of data structures and file formats used to preserve and communicate
transforms.
This segregation of formats precludes the compatibility between tools and endangers the
reproducibility of results.
We propose a software tool capable of converting between formats and resampling images
to apply transforms generated by the most popular neuroimaging packages and libraries
(AFNI, FSL, FreeSurfer, ITK, and SPM).
The proposed software is subject to continuous integration tests to check the
compatibility with each supported tool after every change to the code base.
Compatibility between software tools and imaging formats is a necessary bridge
to ensure the reproducibility of results and enable the optimization and evaluation
of current image processing and analysis workflows.

## Integration with *NiBabel*
*NiTransforms* started as a feature-repo spun off of *NiBabel*.
Shortly after starting with [nipy/nibabel#656](https://github.com/nipy/nibabel/pull/656), it became apparent that it was going to build up in a humongous PR nobody would be able to review as thoroughly as it would require.
Also, *NiTransforms* has many connections to BIDS/BIDS-Derivatives and its X5 format specification for transforms, which falls outside of the current scope of *NiBabel*.

The plan is to make it an isolated tool, and once it is finished, proceed with the integration into *NiBabel*.
Once this repository is ready for integration, we will define what can go into *NiBabel* (presumably everything, except perhaps some final details of the X5 implementation, although *NiBabel* will support the data structure at least logically).
This is to say that the chances that NiTransforms is integrated into NiBabel are high and scheduled to happen in ~2022 Q2.
