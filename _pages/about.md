---
permalink: /
title: "Marc's Webpage"
excerpt: "Because it's nice to have one to yourself."
author_profile: true
redirect_from: 
  - /about/
  - /about.html
classes: wide
header:
  image: https://i.imgur.com/yhFZ8TQ.jpg
---


Biography
======
I am a PhD candidate in the School of Physics in UNSW Sydney working with [Dennis Stello](https://research.unsw.edu.au/people/associate-professor-dennis-stello). My work focuses on the **applications of deep learning in asteroseismology**, which combines two very exciting research fields: artificial intelligence and astronomy. With great strides in recent exoplanet-hunting missions from NASA such as [_Kepler_](https://www.nasa.gov/mission_pages/kepler/main/index.html) and the [Transiting Exoplanet Survey Satellite (_TESS_)](https://www.nasa.gov/tess-transiting-exoplanet-survey-satellite), asteroseismology has become a key tool for the characterization of fundamental stellar properties and to investigate stellar interiors. Using deep learning for asteroseismology accelerates this analysis for thousands to millions of stars, thus becoming important methods for Galactic archaeology and the search for exoplanets. 


Research Interests
------
I am interested in understanding more about stellar evolution, as well as demystifying the origins of the Galaxy through modern space surveys! I am especially enthusiastic in learning about powerful 'Big Data'-era pattern recognition/data analysis techniques such as deep learning.

* Red Giant Asteroseismology
* Deep Learning and other approaches to Artificial Intelligence
* Machine Learning
* Galactic Archaeology

### Computer Vision in Asteroseismology

In my [paper](https://arxiv.org/abs/1804.07495) I introduce the Solar-like Oscillations Shape Hunter (SLOSH), which is a 2D convolutional neural network that identifies the presence of red giant oscillations from images of frequency power spectra of stars. Red giant power spectra have very characteristic frequency-power profiles that show rich levels of complexity; this makes it non-trivial for asteroseismic data-fitting pipelines to automatically extract seismic information from a large sample of stars. However, the morphology of these power spectra can be easily recognized visually by a human expert. Since convolutional neural networks are powerful deep learning tools that can mimic human visual recognition, SLOSH acts as a 'machine expert' that can visually identify oscillations within thousands of stars within seconds.   

<figure>
  <img src="/images/AI-Heatmap_Single_LargerFont.png" alt="AI Heatmap" width="200" height="50">
  <figcaption>The deep learning seismic detector determines the presence of red giant oscillations and precisely measures the characteristic oscillation frequency, $\nu_{\mathrm{max}}$, from the grayscale image (right panel) of a power spectrum plot (left panel). The red-purple regions on the right image are parts of the power spectrum that are given high `attention' by the detector -- these correspond to the very same features a human visual expert uses for identifying oscillations.</figcaption>
</figure>

The lack of any explicit fitting of a mathematical model to power spectra makes SLOSH incredibly flexible. It has been used to find [red giants in all _Kepler_ data](https://arxiv.org/abs/1903.00115), and also for asteroseismic target selection in the _K2_ Galactic Archaeology Program. It is now being implemented for stellar classification on a grand scale with _TESS_ through the _TESS_ Asteroseismic Science Consortium. 

What makes SLOSH unique is that it uses a 2D representation - an image - of 1D data (power density) as input. There are a few advantages to such an approach:

* The image representation is analagous to how human experts assess the presence of red giant oscillations - by viewing the plot of the power spectrum in log-log space (see [this paper](https://arxiv.org/abs/1611.09852) as an example).
* It is easy to handle observations of different length. 4 year _Kepler_ observations have high frequency resolution (high number of frequency bins), while 1 month _TESS_ observations have low frequency resolution (fewer frequency bins). If a 1D neural network is used, the power spectrum must be manually binned for different observation lengths (neural networks typically have a fixed size of its input), and extra care must be taken such that the data is not over-smoothed or too sparse. Using an image representation, however, mitigates this requirement, allowing the network to learn on its own how a power spectrum with more/fewer frequency bins would appear.

The use of 2D representations for 1D data is not a new concept, and methods such as Recurrence Plots and Gramian Angular Fields have been used in literature for 1D time series analyses. SLOSH illustrates that a suitable choice of data representation is extremely powerful for machine learning.

Highlighted Publications
------
Check out my [Publications](https://mtyhon.github.io/publications/) page for more details!

* Hon, M.; Stello, D.; Garc ́ıa, R. A.; et al..“A search for red giant solar-like oscillationsin all Kepler data”, 2019, MNRAS, 485, 5616, doi:[10.1093/mnras/stz622](https://doi.org/10.1093/mnras/stz622)
* Hon, M.; Stello, D.; Zinn, J..“Detecting Solar-like Oscillations in Red Giants with Deep Learning”, 2018, ApJ, 859, 64, doi:[10.3847/1538-4357/aabfdb](https://doi.org/10.3847/1538-4357/aabfdb)
* Hon, M.; Stello, D.; Yu, J..“Deep learning classification in asteroseismology using an improved neural network: results on 15000 Kepler red giants and applications to K2 and TESS data”, 2018, MNRAS, 476, 3233, doi:[10.1093/mnras/sty483](10.1093/mnras/sty483)
* Hon, M.; Stello, D.; Yu, J..“Deep learning classification in asteroseismology”, 2017, MNRAS, 469, 4578, doi:[10.1093/mnras/stx1174](10.1093/mnras/stx1174)

Media Highlights
------
How AI Can Determine the Future of Red Giants Like Our Sun, Nvidia Blog, 4 August 2017, [https://blogs.nvidia.com/blog/2017/08/04/red-giants/](https://blogs.nvidia.com/blog/2017/08/04/red-giants/)

Scientists Are Using Artificial Intelligence to Plot the Galaxy, Inverse, 22 May 2017, [https://www.inverse.com/article/31912-machine-learning-ai-classifies-red-giant-age/](https://www.inverse.com/article/31912-machine-learning-ai-classifies-red-giant-age/)


