---
title: "Simple Poker Hand Probability"
author: "C. Lewis (@ctjlewis)"
date: April 3, 2022

abstract: >
  Simple formulae for estimating the probability of chosen poker hands.

toc: false
header-includes:
  - \renewcommand\arraystretch{1.5}  
  - \hypersetup{colorlinks=true}
  - \usepackage{xcolor}
  - \usepackage[letterpaper, margin=1in]{geometry}
  - \hypersetup{colorlinks=true,
    linkcolor=darkgray,
    allbordercolors={0 0 0},
    pdfborderstyle={/S/U/W 1}}
    
  # - \newcommand{\hideFromPandoc}[1]{#1}\hideFromPandoc{\let\Begin\begin\let\End\end}
---



## General

The probability of drawing a hand with $D$ cards of $S$ chosen suits and $R$ chosen ranks, excluding $E$ cards from the deck before drawing the remainder of an $H$-card hand, is estimated as follows:

$$
P(S, R, D, E, H) = \frac{\dbinom{4}{S}\dbinom{13}{R}\dbinom{52 - E}{H - D}}{\dbinom{52}{H}}
$$

> *Note that this will include higher value hands, e.g. $P_{OAK}$ below will not exclude chance of drawing FH, straight, etc.*

## $N$-of-a-kind (or better)

The probability of drawing an $N$-of-a-kind (or better) in an $H$-card hand is estimated by choosing $N$ cards from 1 rank and $N$ suits, excluding the 4 cards of the given rank from the rest of the hand:

$$
P_{OAK}(N, H) = P(N, 1, N, 4, H)
$$


Ex.: Probability of 4OAK on a 5-card hand is estimated by $P_{OAK}(4, 5) \approx 0.024\%$. 3OAK on 5-card hand estimated as $\approx 2.25\%$ vs. $\approx 2.11\%$ excluding FH etc.


## $N$-card flush (or better)

The probability of drawing an $N$-card flush (or better) in an $H$-card hand is estimated by choosing $N$ cards from 1 suit and $N$ ranks, excluding the 13 cards of that suit from the rest of the draw:

$$
P_{FLUSH}(N, H) = P(1, N, N, 13, H)
$$

Ex.: Probability of a 3-card flush in a 7-card hand is estimated by $P_{FLUSH}(3, 7) \approx 70\%$.


--------------------------------------------------------------------------------