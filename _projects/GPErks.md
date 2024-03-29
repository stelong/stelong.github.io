---
layout: project
title: GPErks
categories: [GPyTorch, BoTorch, SALib]
---

Gaussian process regression is a technique to represent the relationship between a model input and its corresponding output using multivariate Gaussian distributions. These are commonly inferred by conditioning a Gaussian prior to model evaluations. The obtained posterior distribution can subsequently be used to query the input parameter space at previously unseen points (interpolation). Uncertainty around predictions grows bigger when extrapolating outside the input parameter ranges. These posterior distributions effectively become a practical tool for replacing the original model with a probabilistic surrogate model as their constituting hyperparameters gets calibrated to the input-to-output map itself. A surrogate model based on Gaussian process regression takes the name of *Gaussian Process Emulator* (GPE). In the context of GPEs, the original model takes the name of *simulator*.

**GPErks** is a Python library to (bene)fit Gaussian Process Emulators.

From the Italian word 'bene' (well, properly), the aim of GPErks is twofold: (1) to provide a fitting routine which is robust and reliable while still being flexible to user customisation, and (2) to provide an accessible tool for scientists to learn more about their model by replacing it with a surrogate, in so doing unlocking a whole lot of analyses (e.g., global sensitivity analysis, model calibration etc.) which are untractable for computationally expensive models.

## Example 1D
Let's build a GPE of the Forrester et al. (2008) function defined as:

\begin{equation}
    f_{simul}\,\colon\,[0,\,1] \to\mathbb{R}
\end{equation}
\begin{equation}
    x \mapsto (6x - 2)^2 \sin(12x - 4)
\end{equation}

<iframe src="/images/plotly/GPErks_Figure1.html" height="450" width="100%"></iframe>

We can see that the GPE uncertainty grows bigger in regions where there is less information about the underlying function (e.g., between the 3rd and the 4th red dots, and at the input space boundaries).

## Example 2D
Let's build a GPE of the Currin et al. (1988) function defined as:

\begin{equation}
f_{simul}\,\colon\,[0,\,1]^{2} \to\mathbb{R}
\end{equation}
\begin{equation}
(x_1,\,x_2) \mapsto \left[1 - \exp{\left(1 - \dfrac{1}{2 x_2}\right)}\right]\,\left(\dfrac{2300 x_{1}^3 + 1900 x_{1}^2 + 2092 x_{1} + 60}{100 x_{1}^3 + 500 x_{1}^2 + 4 x_{1} + 20}\right)
\end{equation}

<iframe src="/images/plotly/GPErks_Figure2.html" height="450" width="100%"></iframe>

Similarly to the 1D case, predictions are more accurate (low relative error) in parameter space regions that are better covered by data points.

## General case
Most often, the simulator for which we want to build an emulator is multi-parametric, non-linear, computationally intensive to run, and lacks an analytical closed form.

\begin{equation}
    f_{simul}\,\colon\,\mathbb{R}^{d} \to\mathbb{R}
\end{equation}
\begin{equation}
    \mathbf{x} \mapsto y
\end{equation}

## GPE implementation
In a GPE setting, we treat the deterministic response of the simulator $f_{simul}(\mathbf{x})$ as a realisation of a random function $f(\mathbf{x},\,\omega)$. In GPErks, we implemented the random function as the sum of a regression model and a stochastic process:

\begin{equation}
    f(\mathbf{x},\,\omega) = h(\mathbf{x}) + Z(\mathbf{x},\,\omega), \quad (\mathbf{x},\,\omega)\in\mathbb{R}^d\times\Omega \nonumber
\end{equation}

where $\Omega$ is a probability sample space, commonly the Lebesgue-measurable set of real numbers.

The regression part $h(\mathbf{x})$ provides a mean approximation to the computer code. We will only consider the parametric case where $h$ is given as a linear combination of elementary basis functions, namely $(D+1)$ one-degree polynomials:

\begin{equation}
    h(\mathbf{x}):=\sum_{i=0}^D\beta_i\,h_i(\mathbf{x}) = \mathbf{h}(\mathbf{x})^\mathsf{T}\,\boldsymbol{\beta} \nonumber
\end{equation}

where $\boldsymbol{\beta} = (\beta_0,\dots,\beta_d)^\mathsf{T}$ is the regression parameter vector and $\mathbf{h}(\mathbf{x}) = (h_0(\mathbf{x}),\dots,h_d(\mathbf{x}))$ is the basis function vector with

\begin{equation}
    h_i(\mathbf{x}):= 1 \quad\text{if}\quad i = 0
\end{equation}
\begin{equation}
    h_i(\mathbf{x}):= x_i \quad\text{if}\quad i=1,\dots,D \nonumber
\end{equation}

The stochastic part $Z(\mathbf{x},\,\omega)$ is a centred (zero-mean) Gaussian process ($\mathcal{GP}$), completely and uniquely determined by it covariance function (or *kernel*) $k$:

\begin{equation}
    Z(\mathbf{x},\,\omega):= \mathcal{GP}(\mathbf{0},\,k(\mathbf{x},\mathbf{x'})) \nonumber
\end{equation}

The covariance function specifies the covariance between pairs of random variables:

\begin{equation}
    k\colon\mathbb{R}^{D}\times\mathbb{R}^{D}\to\mathbb{R} \nonumber
\end{equation}
\begin{equation}
    (\mathbf{x},\,\mathbf{x}')\mapsto\text{Cov}(Z(\mathbf{x},\,\omega),\, Z(\mathbf{x}',\,\omega)) \nonumber
\end{equation}

Example most commonly used covariance functions are the RBF kernel ($C^{\infty}$) and the Matérn 32 / Matérn 52 kernels ($C^{1}$ / $C^{2}$, respectively).

GPErks emulators are univariate. This means that we can only emulate a scalar output, so if you have a multi-dimensional output you need to independently emulate each of its dimensions separately. In the case of strong correlations between output variables, we recommend training the emulators on uncorrelated variables obtained from the original output via dimensionality reduction techniques.



<div class="large-12 columns">
      <p>
      <a href="https://github.com/stelong/GPErks"> GPErks Repository</a></p>
      <iframe width="560" height="315" src="https://www.youtube.com/embed/e4kYIIrcAHA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
      <p></p>
</div>