## An analysis of the affect of metallicity on exoplanets.

The metallicity here refers to the \[Fe/H\] metallicity and is that of the host star.

Planet properties of interest include:
- Mass
- Radius
- Density

### Abstract
Many studies have aimed to identify abundance relationships and correlations between stellar metallicity and planet mass and radius for specific sizes of planets. More recently some work has attempted to compare the strength of these relationships at a discrete number of predetermined ranges, however, no undisputed studies have as yet attempted to discover the limits and turning points of these trends. In this work, the correlations between stellar metallicity and planet mass, radius and density were calculated via an MCMC analysis for a continuum of different radii, masses and densities. In this report data are presented suggesting that the effect of metallicity on a planet's mass and radius depends on the scale of the planet, with massive, large planets exhibiting a negative correlation between stellar metallicity and planet mass and radius whilst low mass, small planets exhibit a positive correlation between stellar metallicity and planet mass and radius. It is proposed that this is a result of the core dominating the mass and radius of small, low mass planets whilst the abundance of hydrogen dominates the mass and radius of larger, massive planets. No strong correlation was found for mid-sized planets.

### Processing time and multiprocessing
Beware that producing the data which calculates the correlation between two parameters for a continuum of different ranges of a 3rd parameter can take **hours** on some personal computing devices. Various efficiency methods were introduced, some of which depend on setting a minimum number of planets for which correlations should be calculated. You may also increase the size of the steps in range, also this may result in some localised peaks not being rsolvable.

The program also makes use of multiprocessing which allows correlations to be calculated asynchronously. Bewarned however that this is hardcoded and currently involves the use of 6 cores. The method to decrease or decrease this is obvious, involving deletion of some lines to decrease the amount of cores used, or a copy-paste action to increase the amount of cores used.

For reference, I personally used 6 out of 8 cores. This allows other PC processes to continue smoothly. It is not recommended to use all available cores.

I also believe that the used of multiprocessing within the code fixed a memory leak that would occur if large amounts of data were computed.

Finally, the sort of numbers we are talking about produce a list of ~1 million correlation parameters. That is 1 million different MCMC analyses.

## Acknowledgements
A part of this code performs a Bayesian correlation analysis technique originally designed by Figueira et al. (2016) [https://link.springer.com/article/10.1007/s11084-016-9490-5] \[Figueira et al., Astrobiology, **46**, pg.385, (2016)\]. This was update by Thomas Wilson to remove the dependency on PyMc.
