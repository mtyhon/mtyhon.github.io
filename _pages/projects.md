---
permalink: /projects/
title: "Marc's Webpage"
author_profile: true
redirect_from: 
  - /projects/
  - /projects.html
classes: wide
header:
  image: https://i.imgur.com/yhFZ8TQ.jpg
---


Research Projects
======

Computer Vision in Asteroseismology (SLOSH)
------

In my [paper](https://arxiv.org/abs/1804.07495) I introduce the Solar-like Oscillations Shape Hunter (SLOSH), which is a 2D convolutional neural network that identifies the presence of red giant oscillations from images of frequency power spectra of stars. Red giant power spectra have very characteristic frequency-power profiles that show rich levels of complexity; this makes it non-trivial for asteroseismic data-fitting pipelines to automatically extract seismic information from a large sample of stars. However, the morphology of these power spectra can be easily recognized visually by a human expert. Since convolutional neural networks are powerful deep learning tools that can mimic human visual recognition, SLOSH acts as a 'machine expert' that can visually identify oscillations within thousands of stars within seconds.   

<figure>
  <img src="/images/AI-Heatmap_Single_LargerFont.png" alt="AI Heatmap" width="200" height="50">
  <figcaption>The deep learning seismic detector determines the presence of red giant oscillations and precisely measures the characteristic oscillation frequency, $\nu_{\mathrm{max}}$, from the grayscale image (right panel) of a power spectrum plot (left panel). The red-purple regions on the right image are parts of the power spectrum that are given high `attention' by the detector -- these correspond to the very same features a human visual expert uses for identifying oscillations.</figcaption>
</figure>

The lack of any explicit fitting of a mathematical model to power spectra makes SLOSH incredibly flexible. It has been used to find [red giants in all _Kepler_ data](https://arxiv.org/abs/1903.00115), and also for asteroseismic target selection in the _K2_ Galactic Archaeology Program. It is now being implemented for stellar classification on a grand scale with _TESS_ through the _TESS_ Asteroseismic Science Consortium, with an integrated version available [here](https://github.com/tasoc/starclass). 

What makes SLOSH unique is that it uses a 2D representation - an image - of 1D data (power density) as input. There are a few advantages to such an approach:

* The image representation is analagous to how human experts assess the presence of red giant oscillations - by viewing the plot of the power spectrum in log-log space (see [this paper](https://arxiv.org/abs/1611.09852) as an example).
* It is easy to handle observations of different length. 4 year _Kepler_ observations have high frequency resolution (high number of frequency bins), while 1 month _TESS_ observations have low frequency resolution (fewer frequency bins). If a 1D neural network is used, the power spectrum must be manually binned for different observation lengths (neural networks typically have a fixed size of its input), and extra care must be taken such that the data is not over-smoothed or too sparse. Using an image representation, however, mitigates this requirement, allowing the network to learn on its own how a power spectrum with more/fewer frequency bins would appear.

The use of 2D representations for 1D data is not a new concept, and methods such as Recurrence Plots and Gramian Angular Fields have been used in literature for 1D time series analyses. SLOSH illustrates that a suitable choice of data representation is extremely powerful for machine learning.
