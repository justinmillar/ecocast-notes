# Ecological Forecasting - Day 1

## Introductions

Presenter: Michael Dietze

https://www.dropbox.com/s/g4bjhed4k5s48fv/NEFI_Welcome.pdf?dl=0

## Why Forecast?

Presenter: Michael Dietze

Lecture notes: https://www.dropbox.com/s/mwwusp4aqbecn20/EcoForecast2018_Lecture01.pdf?dl=0

Decision are focused on what is going to happen in the future, and forecasting is explicitly about what will happen in the future. Forecasting also provides a framework for real-world application of ecological models. Iterative forecasting fits into the scientific method, and can improve and accelerate the scientific process.

#### Forecasts are a priori

 This innately improves the reproducibility of our models.
 Without receiving feedback to evaluate our models, we are prone to being over-confident in our predictions This process accelerate the accuracy of weather predictions.

#### Can we forecast ecology like we forecast the weather?

### How do we measure the predictability of ecological systems?

One rule of hand, the uncertainty should increase with time. Difference between fitting the model as a **function** versus as a **process**.

### Endogenous Stability

Forecast uncertainty is a function of the sources of uncertainties, and each of there sensitivity to change through time. Unstable uncertainty with grow through time (i.e. chaotic), which is why weather forecasting quickly become less accurate. In these cases, initial conditions dominate outcomes. This may be the case for some ecological applications, like emerging epidemics, however many ecological questions are likely to be less sensitive to initial conditions.

Note that this is the difference between forecasting the weather, and forecasting the climate.

Since weather forecasters identified the importance of initial conditions in driving uncertainty, the majority of resources have been focused on describing initial conditions.

### Exogenous Stability

Also described as driver uncertainty. The importance here is not so much "does X effect Y", but "how **much** does X effect Y". It also means that it is imperative that parameter uncertainty is expressed in regression-based models, and also the variance in individual parameters. Relative importance will increase with time.

#### Endogenous (DD) and Exogenous (ID) as a continuum

### Parameter error

As sample size increases, our parameter uncertainty will decreases and fallout out as a importance source of uncertainty. However, there as some ecological contexts, such as emerging infectious disease, that are inherently data-limited.

### Process error

Inherent stochasticity (randomness) may be irreducible. This is due to the fact that all models are simplistic approximately of real-world events. Still, we must accommodate these uncertainties as they will have important consequences for our forecasts.

The result of all this is that in forecasting we typically spend more time thinking about sources of uncertainty than the models themselves.

#### Think Distributions

### Covariance and scaling

Scaling is vary dependent on spatial and temporal auto- and cross-correlation.

### The nature of the prediction problem

We need to able to define the types of problems, determine how predictable are different types of problems, and how and what we need to measure to characterize uncertainty.

### Forecast cycle

Forecasts should be updated when new data become available. This lends ecoforecasting inherently to a Bayesian framework. Failing to report uncertainties gives that parameter too much weight.

Ecological forecasting is more than just running a model into the future, requires the fusion of models and data, must address multiple sources of uncertainty and variability, and requires probabilistic thinking.

## Decision structuring and indicators

Presenter: Melissa Keeney

Lecture notes: https://www.dropbox.com/s/e5evrxssz2s3q3y/DecisionStructuringAndIndicators.pdf?dl=0

### Book recommendations
Smart Choices - Hammond, Keeney,
Structured Decision Making

### How are decisions made

Decisions are formed as a function of uncertain scientific information, values, and constraints.

Decision support systems need to include values, science, and risk. In additional to tools, systems must also support **processes**, which can have different outcomes then tools. Processes can include developing frameworks, co-production of knowledge, assessing impact and vulnerabilities, and linking scientists to decisions makers. Tools often focus on scenarios and planning, data management and visualizations, tradeoffs, and developing integrated assessment models.

#### Descriptive Science >> Experimental Science >> Prescriptive Science >> Normative Science

This approach combines the *push* of producing scientific information and models with the *pull* of that information to inform decisions.

#### Is there a method to make better decisions?
#### Decision Analysis!

### The PrOACT model
**Pr** oblem -  **O** bjective - **A** lternatives - **C** onsequences - **T** radeoffs

### Practical Example: Planning a flight ESA

Factors to consider: cost, perception of cost, time of departure/arrival, layovers, distance, source of funding, airline, materials, time relative to the meeting/presentations/appointments, jet lag, travelling with others, international travel concerns.

Note that all of these (we came up with 17 in the room) go into a simple decision about a flight. Ecological decision problems can be far more complex. Typically in real life decision making we simply these questions into fundamental objectives. For instance, many of these concerns are related to cost, comfort/convenience, time, productivity, etc.

### Decision Opportunity:

| Objectives | Performance Measures | Units/Information | Alt 1 | Alt 2 | Alt 3
|---|---|---|---|---|---
| Minimize cost | $ spent door-to-door | Dollars | $600 | **$300** | *$650*
| Minimize time | total time flying/in transit | Hours | **3 hours** | 6 hours | *10 hours*
| ~~Maximize comfort~~ | disturbance indicator, during flight experience| Rating: 1 to 5 (worst to best) | **4** | **4** | 1-5 (?)
| ~~Minimize social cost~~ | | | | |
| ~~Maximize ethics~~ | | | | |

**best option** *worst option* ~~Non-informative objective~~

This demonstrates that the values play a critical role in making an effective decisions.

The relevant related questions include:
- Is this the right problem / decision framing
- If not, are there other objectives (and associated performance measures) that need to be considered?
- Can the alternatives be expanded?

### Objectives: Why do we care about the decision?

Means >>>>>>>>>>>>>>>>>>>>>>>>> End

"Why is that important?" ---->

<------ "How might we achieve?"

Characteristics of a good objective include complete, concise, controllable, understandable, and preferentially independent

### Performance measures / indicators

Critically important for determining of translating models that is relevant for decisions. Establishing these values can be difficult, particularly when mapping categorical scales to quantitative values. It is important to consider the optimal representative values for each objective criteria, rather than dropping in model outputs with contexts.

### Alternatives

Centered on value-focused thinking.

### Consequences

This is primarily where ecological forecasting comes in, however each of the preceding parameters are important considerations when designing and improving the forecast. It is therefore important to think about who will be using the forecast, how will they value objectives, how will they weight alternatives. Not all forecasting applications necessarily have a decision component, but many will and this directly connects to adaptive management strategies.

## Introduction to Bayes

Presenter: Shannon LaDeau

### Characterizing uncertainty

Classic assumptions of linear models
- Homoskedasticity
- No error in X variables
- Error in the Y is measurement Error- Normally distributed Error
- Observations are independent
- No missing data


$$y_i = \beta_0 + \beta(x_i) + \epsilon_i$$

However, data do don't always fit these assumptions.

$$
y_i \sim Bern(\rho_i)
\\\rho_i = logit (\theta_i)
$$

### Heteroskedasticty

$$
y \sim N(\beta_1 + \beta_2x, (\alpha_1 + \alpha_2x)^2)
$$

We can build that into the process model to more accurately capture the true relationship of the data distribution. Here this is done by allowing variance to increase through time.

### Observation Error

The regression error assumes all error is in Y, which would be fine if the process model is perfect. However, there is likely to be missing error in the covariates themselves. In other words, we didn't perfectly measure our predictor variables. Failing to account for this can make predictions over-confident.

The solution is to have error incorporated into the covariates.

$$
y \sim N(x, s)
\\x \sim N(0, \tau)
$$

### Latent variables

### Missing data

Can include in the process model, with hyper-priors in the parameter model. Update the regression model based on ALLL the rows of data conditioned on the current values of the missing data.

**Assumption:** data missing at random. If it is systematic than missing data can not be modelled.
