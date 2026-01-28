---
layout: default
title: Nonlinear SPICE Inductor
parent: Simulation & Modeling
nav_order: 1
---

# Nonlinear Inductor SPICE Model
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1. Overview
This Octave script processes measured $L(i)$ data to generate a behavioral SPICE subcircuit. It accurately models saturation effects in toroidal power inductors.

## 2. Methodology
Standard SPICE inductors are linear. To model saturation, we must integrate the inductance to find the Flux Linkage ($\psi$) vs. Current ($i$) relationship:

$$\psi(i) = \int_{0}^{i} L(x) \, dx$$

The script performs this numerical integration and fits the result to a polynomial or lookup table for the SPICE engine.

## 3. The Octave Script
The script reads the CSV output from my [Inductance Extractor](../sw-projects/inductance-extractor) and generates a `.lib` file.

```matlab
% Core integration logic
current = data(:,1);
inductance = data(:,2);

% Integrate L over I to get Flux
flux = cumtrapz(current, inductance);

% Curve fitting (Polynomial degree 5)
p = polyfit(current, flux, 5);
