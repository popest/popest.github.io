---
layout: default
title: Fiber Optic Thermometer
parent: HW Projects
nav_order: 1
---

# Battery-Powered Thermometer
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1. Overview
This project involved designing a battery-powered thermometer with a fiber optic link to a 16-channel control unit.

## 2. Technical Challenges
The primary challenge was ensuring signal integrity over the fiber link while maintaining ultra-low power consumption for the battery unit.

### Key Specs
| Feature | Value |
|:-------|:------|
| **MCU** | STM32L0 (Low Power) |
| **Link** | Fiber Optic (Manchester Encoding) |
| **Power** | < 10uA Sleep Current |

## 3. Implementation
We utilized a **Manchester encoding** scheme to ensure robust data transmission without a shared clock signal.
