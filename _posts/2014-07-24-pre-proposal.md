---
layout: post
title: "Pre-proposal for a modelling project, etc."
description: ""
category: [notes, proposals]
tags: [simulation, PD, likelihood-free, stats]
---
{% include JB/setup %}

##Morning

* Spent the morning writing up a short pre-proposal for a project I'd like to be involved in. Hoping this will become a full grant proposal in the near future. The prep-proposal follows:

Using multiple phylogenetic and compositional diversity metrics to predict endemism across Australia
====================================================================================================

It is increasingly recognized that phylogenetic diversity metrics
contain important information about communities of organisms above and
beyond that contained in species richness estimates (Cavender-Bares et
al. 2009). The full power of phylogenetic diversity metrics (PD
hereafter), has not been realized, however, because of a reliance on
null model analysis to infer processes. The main issues with this
approach are the following:

1.  Null models hold other diversity metrics, such as species richness,
    constant, even though these may also contain important complementary
    information about processes.

2.  Null model analysis can only reject a null model, it cannot measure
    support for one or another alternate hypotheses. This is
    particularly a problem when a single PD metric is not sufficient to
    distinguish between multiple potential processes underlying a
    pattern. This has been the source of recent criticism of the PD
    approach to inferring processes (e.g. Mayfield and Levine (2010)).

We propose to solve both these problems using an approach that uses
multiple diversity metrics simultaneously, which can greatly reduce the
possible processes responsible for a pattern (Stegen and Hurlbert 2011),
and that measures the relative fit of multiple assembly hypotheses to
occurrence data. We then propose to use this framework to make useful
predictions about Australian Flora and Fauna, in particular the spatial
distribution and phylogenetic placement of potential endemics in areas
which are currently understudied.

Statistical Framework
---------------------

The framework that makes this type of analysis possible is based on an
emerging field of statistical inference known as "likelihood-free"
methods. These methods allow the fitting to data of any model from which
it is possible to generate simulated output (Hartig et al. 2011).
Approximate Bayesian Computation (ABC) and synthetic likelihood (Wood
2010) are two examples of this framework. In short, these methods work
by calculating a set of multiple 'summary' statistics (an example would
be an auto-regressive coefficient at multiple lags for time-series data)
for simulated and observed data-sets, and then finding the simulation
parameters which produce summary statistics that most closely match the
observed summary statistics. There appears to be an intriguing
connection between diversity metrics --- which ecologists routinely use
to summarize the structure of occurrence data and to informally infer
processes --- and summary statistics --- which summarize the structure
of any data, and can be used to infer a model, formally. In other words,
this provides a unifying mathematical formalism with strong theoretical
support to what ecologists already do in a less structured way.

The Data
--------

We propose to use likelihood-free statistical methods to fit
process-based models to occurrence data of Australian organisms, drawn
from the Atlas of Living Australia. At first, we will concentrate on
fitting relatively simple models which contain environmental filtering
by climate variables, as well as species interactions (e.g.
competition), allowing both to be partly determined by the observed
species' phylogeny. We will use a host of different diversity metrics,
including both alpha and beta versions of PD across a large spatial
extent as summary statistics. Besides validating these methods as an
effective way to understand the potential processes underlying complex
patterns of biodiversity, a major impact of this work will be on
deriving predictions from these model once they are fit to data.

Predictions in a likelihood-free framework: Turning a weakness into a strength
------------------------------------------------------------------------------

One potential disadvantage of likelihood-free methods comes when we wish
to make predictions about unknown communities from models fit to known
communities. Because we fit the model using summary statistics rather
than the raw data, predictions can only be made about the summary
statistics. In this case, we could only make predictions directly from
the model about diversity metrics in unknown regions, and not about the
individual species whose occurrence data were used to calculate the
diversity metrics. However, we suggest that this potential weakness
could be turned into a great strength. In traditional Species
Distribution Models (SDMs) that predict species distributions in unknown
areas, it is only possible for them to predict the presence or absence
of species that were observed in the known areas. A major problem with
this is that they cannot predict the presence or absence of any species
which is not currently known in the region under observation. However,
there are likely many potential endemic species across Australia, that
may not yet occur in any useful occurrence database.

This is where likelihood-free method's apparent weakness could be their
strength. Because we are not trying to model specific species data, but
rather are trying to model 'emergent' or 'collective' properties of the
system, our predictions will not be tied to any particular permutation
of species. Besides the interesting insights that can be drawn simply
from making predictions about these types of properties, work at CSIRO
has already shown that it is possible to find configurations of species,
both known and hypothetical, which best match a particular set of
diversity metrics (Mokany et al. 2011). And because our model will
explicitly incorporate phylogeny from the beginning, it will be possibly
to determine the phylogenetic placement of hypothetical unobserved
species, which will best match predicted patterns of phylogenetic
diversity across a landscape. This opens the possibility of predicting
where currently unknown species are most likely to be found, as well as
the most likely parts of a phylogeny they will come from.

References
==========

Cavender-Bares, Jeannine, K.H. Kozak, P.V.A. Fine, and S.W. Kembel.
2009. “The Merging of Community Ecology and Phylogenetic Biology.”
*Ecology Letters* 12 (7): 693–715.
<http://www3.interscience.wiley.com/journal/122388144/abstract>.

Hartig, Florian, Justin M Calabrese, Björn Reineking, Thorsten Wiegand,
and Andreas Huth. 2011. “Statistical Inference for Stochastic Simulation
Models–Theory and Application.” *Ecology Letters* 14 (8): 816–827.
doi:[10.1111/j.1461-0248.2011.01640.x](http://dx.doi.org/10.1111/j.1461-0248.2011.01640.x).

Mayfield, Margaret M, and Jonathan M Levine. 2010. “Opposing Effects of
Competitive Exclusion on the Phylogenetic Structure of Communities.”
*Ecology Letters* 13 (9) (September): 1085–93.
doi:[10.1111/j.1461-0248.2010.01509.x](http://dx.doi.org/10.1111/j.1461-0248.2010.01509.x).
<http://www.ncbi.nlm.nih.gov/pubmed/20576030>.

Mokany, Karel, Thomas D Harwood, Jacob McC Overton, Gary M Barker, and
Simon Ferrier. 2011. “Combining *α* - and *β* -Diversity Models to Fill
Gaps in Our Knowledge of Biodiversity.” *Ecology Letters* 14 (10)
(October): 1043–51.
doi:[10.1111/j.1461-0248.2011.01675.x](http://dx.doi.org/10.1111/j.1461-0248.2011.01675.x).
<http://www.ncbi.nlm.nih.gov/pubmed/21812884>.

Stegen, James C., and Allen H. Hurlbert. 2011. “Inferring Ecological
Processes from Taxonomic, Phylogenetic and Functional Trait
*β*-Diversity.” *PLoS ONE* 6 (6).

Wood, Simon N. 2010. “Statistical Inference for Noisy Nonlinear
Ecological Dynamic Systems.” *Nature* 466 (7310): 1102–1104.

##Afternoon

* Updated [`Ralf`](https://github.com/rdinnager/Ralf) package with basic functionality for my #AFD and #LDA-metagenomics projects.

* Started figuring out how to push `.Rmd` `knitr` documents to package `gh-pages` branch so they will be rendered at http://rdinnager.github.io/<project.name>/<Rmd.name> (example: http://rdinnager.github.io/LDA-metagenomics/assumption_test) ala @cboettig. Doing this so that I can use `.svg` plots which I think are superior to most other formats. See [this post](http://www.carlboettiger.info/2014/05/07/integrating-github-project-repos-into-the-notebook.html) by @cboettig for my inspiration. 