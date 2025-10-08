# Outline 


## Introduction

 Introduction: summarize and introduce the ELF: what it is, how it works.
Talk about the \textcite{osth_novelty_2023} model, which explains the difference
between integral and separable data. Discuss their literature, as well as your literature.
Quickly propose the learned kernel model.

\item First section: literature review. Discuss ELF in context with other experiments. 
You need to do the literature review yourself, like look at the sources of \textcites{osth_novelty_2023} etc.,
as well as background from the ELF paper itself. The literature review here requires
re-reading \textcite{mewhort_extralist-feature_2000}, as well as other papers on the subject
from Mewhort and Jones. 

Next, take a look at the history of associative memories, \textit{namely} in relation
to cognitive models. Main sources of inspiration are recent energy-based approaches
from \textcites{krotov_dense_2016,krotov_modern_2025,krotov_hierarchical_2021,hopfield_neural_1982}.
For the heuristic approach, dicuss \textcite{salvatori_associative_2024} and 
\textcite{wu_uniform_2024}. In these models, the associative memory learns a kernel
function for the data itself, maximizing separation. The next important desideratum
is that the model learns online: need to research online learning rules, but see the 
update rule from \textcite{chartier_bidirectional_2006} and \textcite{chartier_ndram_2005}.

### Sub-section: discussion of the nature of machine learning models and how they relate to cognitive modeling (in general)

Finally, I think I need to justify the use of a machine learning model in cognitive science.
In part, I think that some of my desiderata are inspired by the PDP movement 
\textcites{mcclelland_parallel_1986,rumelhart_parallel_1986}. Even though humans have 
good one-shot learning abilities, even for these we need to be able to simulate the acquisition
of knowledge. \textcite{chartier_ndram_2005} again here is interesting, but there 
is also other literature that he cites which I think need to be reviewed.

## Summary of the Model and Methodology
Next I'm going to propose the model and the methodology. We've discussed the desiderata
of the model. But to get into more of the specifics, I will lay them out here.
1. The dataset will be annotated integral and separable dimension data (probably
    something similar to the \textcite{osth_novelty_2023} text). TBD what the exacts details
    are, I might be able to ask for the data.
    
2. I think it would fit my other interests if I were able to find an online dataset of 
    integral versus separable data. Something to do with lexical data. This is interesting,
    not sure what to do about that.

3. The model will be an content-addressable associative memory. Rather than being
    an associative memory parameterized by $N$ memory patterns of $D$ dimension $\Xi$,
    the model will be parameterized by a \textit{weight matrix} $W$. This is a learned
    $D' \times D'$ weight matrix. Query vector $x$ of dimension $D$ are presented to the associative
    memory. An autoencoder reduces the dimension of the query vector to dimension $D'$. 
    A learned kernel $\mathcal K(\cdot, \cdot)$ is used as the separation function over
    reduced dimension vectors of dimension $D'$. Projections then are fed back through the
    ``decoder'' part of the autoencoder through the weight matrix $W$. The goal
    is to be able to derive reaction time and accuracy statistics from the model itself.
\end{enumerate}

The methodology will involve online training sessions on data. We will try to follow the same
protocol as the experiments themselves (of course with modifications for the fact that it is a 
model). We will also compare derived results with the other model and how it fits.

The second interesting source of data that I would like to test the model against is large,
online corpora of human speech. Important to this investigation is the fact that there exists a distinction
between integral and separable stimuli. Lexical items and their orthographic representations have been
investigated in the literature for recall effects \cites{osth_integrating_2024,mewhort_sharpening_2005,malmberg_feature_2002}.

Is there a well motivated way to source data from word corpora? What does it mean to have integral
versus separable word data? One Osth \& Zhuang note that both word-form representations as well as semantic
representations predict similarity judgments equal well.