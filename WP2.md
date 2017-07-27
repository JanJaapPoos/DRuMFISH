# Data-limited methods review

José A. A. De Oliveira, Piera Carpi, Nicola D. Walker, Simon Fischer, Timothy J. Earl, Sarah Davie 

## Executive Summary

A review is provided of a wide-range of data-limited methods and a selection of data moderate methods that could be useful to the DRUMFISH project. Included in the review are papers that have compared some of the methodologies, providing additional simulation-testing and real-world applications of some of these methods. Requirements for DRUMFISH are methods that are easily accessible and available for application, and that can be used for forward projections/forecasting. Two methods in particular are highlighted as meeting these criteria for data-limited and data-moderate cases, namely CMSY for the former and SPiCT for the latter, given their track record of use in the ICES advisory process and the ease of “slotting in” with current simulation tools for DRUMFISH. Nevertheless, there are a range of other methods that also meet the criteria and could be used.

## Introduction and summary

This document provides a review of data-limited approaches, alternatively referred to as “data-poor”, and distinct from both data-moderate approaches, which typically include indices of biomass/abundance in addition to catch data and life-history information, and data-rich approaches, which include full analytical assessments. Data limited approaches (Section 2) cover catch-based approaches (catch-only methods with supplementary information), life-history, per-recruit and length-based approaches, and qualitative and semi-quantitative approaches. There are a number of papers that compared the performance of some of the methods and that conducted additional simulation testing, providing some useful additional insights into the methods presented (Section 3). Real-world applications are covered in Section 4, although sometimes only the abstract is provided for reference: these papers provide useful examples of application of the methods. Some data-moderate methods that may be of interest are covered in Section 5, although this section is not intended to be fully comprehensive. Supplementary and other approaches that may be of interest are covered in Section 6, including mixed fishery, MPA, PSA and other general approaches (sometimes only the abstract is supplied). Section 7 covers simulation-tested data-limited harvest control rules, not directly relevant to the DRUMFISH project, but nevertheless included for interest. Other methods’ reviews, similar to this document, and from which some inspiration was drawn (e.g. Geromont and Butterworth) are covered in Section 8 (again, sometimes only the abstract is supplied for completeness). Within each review the authorship, title and abstract is supplied, and the paper is generally summarised through the topics “data/information requirements”, “assumptions”, “outputs expected”, “method of operation”, “testing”, “caveats” and in some cases “ability to project forward/forecast” (the latter topic was added much later, so is not universally used). Some adjustments to this general structure are made for, e.g. simulation-testing papers that cover several methods.

A summary spreadsheet is available (not included here), which organises the information in a more easily digestible format, and includes links to where the software from some methods may be accessed (websites and/or github repositories). In general, the DRUMFISH project is interested in methods that are able to be used for forward projecting/forecasting, in addition to being readily available to use. These requirements whittle down the methods that would be useful to DRUMFISH. In particular, two methods that have already been used within the ICES advisory system and provide the required tools for DRUMFISH are catch-MSY (CMSY, Martel and Froese 2013) for data-limited cases, and the stochastic surplus production model in continuous time (SPiCT, Pedersen and Berg in press) for data-moderate cases. These methods produce consistent outputs (they are both biomass dynamic models, and the latter can take on a Schaeffer form, which the former is hard-wired to do), and can be straight-forwardly incorporated into the simulation tools currently available for DRUMFISH.

This does not preclude other methods from being used, where appropriate, and there are a number of these that could potentially be useful, particularly for data-limited methods, although attention is drawn to Section 3, where some of these methods have been compared and simulation-tested. These tests have found that quantitative catch-only methods (DCAC, DB-SRA, CMSY, etc.) are generally highly sensitive to assumptions about depletion, and semi-quantitative catch-only methods (e.g. Froese and Kesner-Reyes, and Kleisner and Pauly) are more negatively biased on average than methods that explicitly model population dynamics with the use of additional fishing effort data. Furthermore, only those methods that dynamically account for changes in abundance and/or depletion perform well at low stock sizes. In essence, there is a high value for including additional information regarding stock depletion, historical fishing effort and current abundance when only catch data are available, but this information is often lacking. In the simulation exercise that compared catch-only methods (Rosenberg et al. 2014), CMSY with catch-only data was rated the best performer and was more effective in estimating stock status over short time scales. Furthermore, regarding SPiCT, simulation work conducted for WKLIFE 6 (ICES in prep) found that for over-exploited stocks, SPiCT was able to correctly identify an undesirable state and hence appropriately invoke a precautionary buffer when needed, thus demonstrating good performance of this model.

Despite the fact that CMSY with catch-only data can take the form of, and behave like, a Schaeffer model, a general guideline is that, if some index of biomass or abundance is available (from commercial CPUE or fishery-independent data), one should always move to a full biomass dynamic model (e.g. SPiCT, ASPIC, etc.). There is also now available (not reviewed here, since it was only published after the review was completed) a Bayesian version of CMSY that can also incorporate an index of abundance.

A final consideration is that the Robin Hood approach is commonly used in many applications. The idea has a relatively long history, but has been formally described in Punt et al. (2011 - not reviewed here, but available in the sharepoint). The Robin-Hood approach refers to the practice of borrowing information from data-rich stock assessments, e.g. trends in fishing mortality and values for parameters of selectivity functions, to assess data-poor stock, which leads to stock assessments for the most data-poor stocks being informed by those for the most data-rich stocks. Bentley (2015) argues a similar approach where prior probability distributions are used to transfer knowledge from data-rich to data-poor fisheries. This practice has been widely recognized as effective whenever the lack of data prevents an assessment, and as such relevant for the DRUMFISH project.

## Data-limited approaches

### Catch-only methods with supplementary information

Vasconcellos, M. and K. Cochrane (2005).
Overview of world status of data-limited fisheries: inferences from landing statistics. In G.H. Kruse, V.F. Gallucci, D.E. Hay, R.I. Perry, R.M. Peterman, T.C. Shirley, P.D. Spencer, B. Wilson & D. Woodby, eds. Fisheries assessment and management in data-limited situations, pp. 1–20. Fairbanks, USA, Alaska Sea Grant College Program AK-SG-05-02.

Abstract: Data-limited fisheries are here considered to be fisheries lacking sufficient reliable biological information to infer the exploitation status of the targeted stocks. Considering species-specific catch data as the common minimum available data for assessing the status of a stock, in this paper we use the taxonomic breakdown of the reported landings statistics to FAO to make an approximate inference of data limitation of fisheries by region, country, and taxonomic groups. The paper also explores the possibility of extracting meaningful biological information from fisheries landings by applying a Bayesian approach to two selected fisheries. The contribution of data-poor fisheries to the world landings from marine capture fisheries is relatively low, but increasing (from 20 to 30% of world landings in the last 50 years). However, data limitation can be a substantial problem at the regional and country level, especially in areas with high species diversity, small stock sizes, and where fisheries play an important role for food security. Preliminary modeling results indicate that catch data, when combined with prior information about the dynamics of similar species/stocks and fisheries, could be useful for informing fisheries management in data-limited situations

Data / information requirements:

•	Time series of catch
•	Priors for:
o	Intrinsic growth rate, r
o	Carrying capacity, K
o	Bioeconomic equilibrium as a proportion of K, a
o	Increase of harvest rate over time, x
•	Process error variability

Assumptions:

•	Fisheries follow a pattern where the relative rate of increase in catch increases rapidly during a development stage, drops to zero when a mature stage has been reached and becomes negative during a senescent phase.
•	Time series of catch data contain information on both fishing effort and stock biomass dynamics.
•	Initial catch is equal to the first observed catch in the time series and is assumed to be measured without error.
•	Initial biomass is equal to the carrying capacity.
•	Either no harvest control regulations are in place or any existing regulations have only negligible effects so that the harvest rate dynamics respond only to the economic / market stimulus.
•	Observed catches follow a lognormal likelihood function.
•	The variability parameter is assumed known and equal to 0.4.

Outputs expected:

•	Stock status
•	Production
•	Exploitation rate

Method of operation:

•	The model predicts catches based on a combination of a biomass dynamics model and a harvest rate dynamics model. The biomass dynamics model follows the Schaefer surplus production model and the harvest rate dynamics model follows a logistic model.
•	The Bayesian algorithm sampling importance resampling is used to fit the model to the catch time series by estimating four model parameters: r, K, a and x.

Walters, C.J., Martell, S.J.D. and J. Korman (2006).
A stochastic approach to stock reduction analysis. Can. J. Fish. Aquat. Sci 63: 212-223.
Abstract: Stock reduction analysis (SRA) can complement more detailed assessment methods by using long-term historical catches to estimate recruitment rates needed to have produced those catches, yet still end up with stock sizes near those estimated by the detailed methods. A longer historical perspective can also add information to the estimation of reference points such as unfished biomass (B0) or target biomass (BMSY). Deterministic SRA models provide a single stock size trajectory that is vanishingly unlikely to have actually occurred, while stochastic SRA attempts to provide probability distributions for stock size over time under alternative hypotheses about unfished recruitment rates and about variability around assumed stock–recruitment relationships. These distributions can be generated with age-structured population models by doing large numbers of Monte Carlo simulation trials and retaining those sample trials for which the stock would not have been driven to extinction by historical catches. By resampling from these trials using likelihood weights (sampling – importance resampling method), it is possible to move into fully Bayesian, state–space assessment modeling through a series of straightforward steps and to provide understandable visualization of how much the data help to reduce uncertainty about historical fishing impacts and stock status.

Data / information requirements:
•	Time series of total catch data – ideally going back close to virgin biomass – preferably as numbers, if not, numbers can be estimated from total weight and mean individual weight.
•	Estimate of natural mortality M
•	Estimate of stock-recruit steepness at low stock size (index, cpue, tagging, etc.)
Assumptions:
•	Known constant M. 
•	Known stock recruit steepness at low stock size and a Beverton-Holt recruitment relationship
•	Fishery selection
Outputs expected:
•	Estimates of harvest ratio (catch/vulnerable biomass)
•	Probability distribution of current depletion level relative to Virgin Biomass
Method of operation:
•	In deterministic SRA, stock numbers at age are projected forward from an initial recruitment of R0. Using estimates of M, and historic catch data, divided among the age classes proportional to the total selected weight at each age. If there are years where catch is greater than estimated vulnerable biomass, this is a strong indication that the initial biomass or recruitment steepness are too low. This method places no upper bound on the steepness or initial biomass, but information about relative abundance may be used to inform an upper bound on these parameters.
•	Bayesian fitting of the SRA model uses historic catch data to investigate a range of Virgin Biomass and recruitment assumptions to find feasible parameter space, acknowledging that recruitment is variable between years, by taking a large number of simulations with randomly generated deviations from the stock-recruit relationship. Auto-correlation can be added to these deviations. The authors suggest that the Bayesian SRA can be considered as a stepping-stone to a full assessment as more sources of data become available and are integrated into the method.
Testing:
•	Fraser River white sturgeon is used as an example of fitting in the deterministic case. In this case, as well as the time series of catches, there are individual weight measurements that indicate a roughly 10-fold reduction in mean body weight due to the truncated age structure caused by past exploitation
•	Data from the Fraser River white sturgeon is used for an example of deterministic stock reduction analysis. The parameters were varied to achieve a current vulnerable biomass estimate of 40,000-60,000 fish, and to follow recent trends indicated by mark-recapture analysis. This implied virgin recruitment around 21,600, which has fallen to around 7,500 in recent years. Comparable results are not shown for the Bayesian method, but they show probability distributions of output quantities such as depletion level given the assumptions about input parameters.
•	The fit of the model to the data can either be judged by comparing to some measure of abundance trend, or by evaluating the probability of extinction given the observed catches – if this is high, then the initial parameter estimates should be reviewed.
Caveats:
•	Auto-correlation in estimates of recruitment deviates lead to high uncertainty in stock size – this might be particularly the case if there is a regime shift due to environmental factors, where effectively one stock-recruit relationship is used to model two substantially different ones.
•	Small populations may have high uncertainty if a small number of large fish contribute substantially to the biomass 


