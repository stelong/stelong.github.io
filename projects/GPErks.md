---
layout: project
title: GPErks
description: A Python library to (bene)fit Gaussian Process Emulators.
categories: [GPyTorch, BoTorch, SALib]
image: /images/GPErks_logo.png
url: /projects/{{ page.title | slugize }}/
---

Gaussian process regression is a technique to represent the relationship between a model input and its corresponding output using multivariate Gaussian distributions. These are commonly inferred by conditioning a Gaussian prior to model evaluations. The obtained posterior distribution can subsequently be used to query the input parameter space at previously unseen points (interpolation). Uncertainty around predictions grows bigger when extrapolating outside the input parameter space boundaries. These derived distributions effectively become a practical tool for replacing the original model with a probabilistic surrogate model as their constituting hyperparameters gets calibrated to the input-to-output map itself through an optimisation routine. A surrogate model based on Gaussian process regression takes the name of *Gaussian Process Emulator* (GPE).

**GPErks** is a Python library to (bene)fit Gaussian Process Emulators.

From the Italian word 'bene' (well, properly), the aim of GPErks is twofold: (1) to provide a fitting routine which actually works (i.e., robust and reliable - we will discuss later about fitting GPEs not being a simple task in general), and (2) to create an accessible tool for scientists to learn more about their model by replacing it with a surrogate, in so doing unlocking a whole lot of analyses (e.g., global sensitivity analysis, model calibration etc.) which are untractable for computationally expensive models.

\begin{align}
    f_{simul}\colon\mathbb{R}^{N\times D} &\to\mathbb{R}^{N} \nonumber \\
    X &\mapsto \mathbf{y} \nonumber
\end{align}

Let's take a look at the 1D Forrester et al. (2008) function defined as:

\begin{equation}
    f_{simul}(x) = (6x - 2)^2 \sin(12x - 4)
\end{equation}


<iframe src="/images/plotly/GPErks_Figure1.html" height="450" width="100%"></iframe>

More commonly, the model for which we would like to build a GPE is multidimensional, nonlinear, lacks an analytical closed form, and is highly computationally intensive for each individual model evaluation.


Let's build a dataset specifying the number of samples we want to have in our training and testing dataset. This will call the function to generate model evaluations at every point in the defined datasets.




MATHS ALERT: we need some formalism before continuing.

Let's consider $N$ realisations $y^{(i)},\,i=1,\,\dots,\,N$ of a computer code $f$ ($=f_{simul}$) for $N$ different input parameter points $\mathbf{x}^{(i)},\,i=1,\,\dots,\,N$ each one with dimension $D$: $\mathbf{x}^{(i)}=(x_{1}^{(i)},\,\dots,\,x_{D}^{(i)})^\mathsf{T}$. More concisely, this can be written as $f(X)$ (or $\mathbf{f}$) where $X=(\mathbf{x}^{(1)},\,\dots,\,\mathbf{x}^{(N)})$ is the input matrix. The pair $(X,\,f(X))$ is called *learning sample*. A Gaussian process emulator (GPE) treats the deterministic response $f(\mathbf{x})$ as a realisation of a random function $f(\mathbf{x},\,\omega)$.

In GPErks, we model this function as the sum of a regression model and a stochastic process:

\begin{equation}
    f(\mathbf{x},\,\omega) = h(\mathbf{x}) + Z(\mathbf{x},\,\omega), \quad (\mathbf{x},\,\omega)\in\mathbb{R}^D\times\Omega \nonumber
\end{equation}

where $\Omega$ is a probability sample space, commonly the Lebesgue-measurable set of real numbers.

The regression part $h(\mathbf{x})$ provides a mean approximation to the computer code. We will only consider the parametric case where $h$ is given as a linear combination of elementary basis functions, namely $(D+1)$ one-degree polynomials:

\begin{equation}
    h(\mathbf{x}):=\sum_{i=0}^D\beta_i\,h_i(\mathbf{x}) = \mathbf{h}(\mathbf{x})^\mathsf{T}\,\boldsymbol{\beta} \nonumber
\end{equation}

where $\boldsymbol{\beta} = (\beta_0,\dots,\beta_d)^\mathsf{T}$ is the regression parameter vector and $\mathbf{h}(\mathbf{x}) = (h_0(\mathbf{x}),\dots,h_d(\mathbf{x}))$ is the basis function vector with

\begin{equation}
    h_i(\mathbf{x}):=\begin{cases}
        1 \quad\text{if}\quad i = 0\\
        x_i \quad\text{if}\quad i=1,\dots,D \nonumber
    \end{cases}
\end{equation}

The stochastic part $Z(\mathbf{x},\,\omega)$ is a centred (zero-mean) Gaussian process ($\mathcal{GP}$), completely and uniquely determined by it covariance function (or *kernel*) $k$:

\begin{equation}
    Z(\mathbf{x},\,\omega):= \mathcal{GP}(\mathbf{0},\,k(\mathbf{x},\mathbf{x'})) \nonumber
\end{equation}

The covariance function specifies the covariance between pairs of random variables:

\begin{align}
    k\colon\mathbb{R}^{D}\times\mathbb{R}^{D}&\to\mathbb{R}\,,\quad\text{with}  \nonumber \\
    (\mathbf{x},\,\mathbf{x}')&\mapsto k(\mathbf{x},\,\mathbf{x}') = \text{Cov}(Z(\mathbf{x},\,\omega),\, Z(\mathbf{x}',\,\omega)) \nonumber
\end{align}

Example covariance functions are the RBF kernel (also called *squared exponential*, infinitely differentiable) and the Matern12 / Matern52 kernel (once / twice differentiable).

GPErks emulators are univariate. This means that we can only emulate a scalar output, so if you have a multi-dimensional output you need to independently emulate each of its dimensions separately.

Let's setup a GPE in GPErks: we need to define all its components.