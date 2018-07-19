# Ecological Forecasting - Day 4

## Ensemble Data Assimilation

Presenter: Michael Dietze

Lecture:  https://www.dropbox.com/s/eqy3pjxjwxgbnkn/EF_Lesson10_DA2.2018_Summer.pdf?dl=0

Monte Carlo methods for assimilating data.

### Extended Kalman Filter

Addresses the linear assumption for the forecast, update variance using a Taylor Series expansion. Important caveats are due to Jensen's Inequality the mean is biased, and there is a false assumptions

The extended Kalman filter (EKF) can be thought of as the exactly analytical answer to an approximate problem. The Ensemble Kalman Filter (EnKF) is the approximate answer to the exact problem.

### Ensemble Kalman filter

Uses ensemble samples to approximate Forecast distribution by drawing samples from the Analysis posterior.

### EnKF Pros and cons

Most commonly used approach in ecological forecasting.

EnKF can fully handle nonlinearity, can operate on existing code (no Jacobian matrices required). Sample size is chosen based on power analysis, however this will be less efficient than the analytical methods. It is also simple add other sources of uncertainty. This would be much trickier for the analytical methods since you would need those derivative matrices. Moments are OK. EnKF does violate Normality, but so does EKF. Analysis is generalizable.

##### Side-note: The Hop test
Start model at some initial condition, run it from time $0$ to  time $t$. Then re-run from the beginning, stop it at some midpoint, then run it forward to confirm that it gets to the same place as the first run. This ensures that the model doesn't give different results when the model is restarted.  

### Ensemble Adjustment

An alternative to resampling from the analysis posterior, we can re-direct the current ensemble back towards the mean. Singular value decomposition (SVD). This would be useful if there are latent states that were not restarted, also when propagating other uncertainties and you want to keep them associated through the transformation to maintain covariance.

### Localization

The computational cost often comes from matrix inversion (specifically the covariance matrix). This is cheaper if the matrix is sparse (has a lot of 0s). This can be done by assuming that correlations depreciation with distance, even becoming zero at a certain distance. This avoids spurious correlations that arise by chance. Note that the "distance" doesn't just have to be physical distance.

### Filter Divergence

Happens when you become false over-confident in the model, which causes the uncertainty in new observation gets masked by the low process error.

###### No KF variants can estimate process and observation errors

#### What if we forecast with a large Monte Carlo Sample

### The Particle Filter
