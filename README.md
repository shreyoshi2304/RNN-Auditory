# RNN Models of Auditory Temporal Processing

## Overview

Auditory perception fundamentally relies on processing **temporal patterns** in sensory input. Unlike static stimuli, sound is inherently time-dependent, requiring neural systems to integrate information across multiple timescales.

In this project, I use recurrent neural networks (RNNs) as simplified models of auditory neurons to investigate how **temporal structure, memory, and noise robustness** contribute to auditory representation.

---

## Key Questions

* How do neural systems extract frequency information from temporal signals?
* Why is temporal memory necessary for auditory processing?
* How do recurrent dynamics shape neural representations?
* Can recurrent models reduce variability under noisy input?

---

## Model Framework

### 1. Spectro-Temporal Input Representation

Instead of raw signals, inputs are modeled as simplified **spectrogram-like representations**, mimicking early auditory processing:

* Time dimension → temporal evolution
* Frequency channels → tonotopic organization

Each input is a structured signal where frequency-specific channels are selectively activated.

---

### 2. Recurrent Neural Network (RNN)

The core model uses a recurrent architecture:

`h(t) = f(W_h * h(t-1) + W_x * x(t))`
`y = W_out * h(T)`

* `x(t)` = input signal at time t
* `h(t)` = hidden state (internal memory)
* `y` = predicted frequency

**Key idea:**
The hidden state acts as a **dynamical system encoding temporal information**.

---

### 3. Rate-Based Model (Baseline)

To isolate the role of temporal dynamics, we compare with a non-recurrent model:

`y = W * mean_t(x(t))`

This model averages inputs over time and lacks memory.

---

## Experiments and Results

### 1. Temporal Processing vs Static Encoding

* RNN successfully learns frequency from temporal patterns
* Rate model performs worse due to lack of memory

**Insight:**
Temporal integration is essential for auditory computation.

---

### 2. Noise Robustness and Variability

We test models under noisy inputs:

`x_noisy(t) = x(t) + η(t)`

**Observation:**

* RNN shows lower output variability
* Rate model is more sensitive to noise

**Interpretation:**
Recurrent dynamics stabilize representations by integrating information over time.

---

### 3. Neural Trajectories (Hidden Dynamics)

Hidden states are analyzed as trajectories in state space:

* Different inputs produce distinct trajectories
* Structure emerges in low-dimensional projections (PCA)

**Insight:**
RNN hidden activity resembles **neural population dynamics** observed in biological systems.

---

### 4. Frequency Tuning

The model learns a mapping:

`temporal pattern → frequency estimate`

**Result:**

* Predicted frequencies closely track true frequencies
* Indicates successful encoding of temporal structure

---

## Conceptual Insight

Across experiments, the RNN behaves as a **dynamical system performing temporal computation**:

> Auditory processing can be understood as the evolution of neural activity in a low-dimensional state space, where temporal patterns are transformed into stable representations.

---

## Key Takeaways

* Temporal memory is essential for auditory processing
* Recurrent dynamics improve robustness to noise
* Neural representations emerge as trajectories in state space
* RNNs provide a useful abstraction of auditory neural computation

---

## Motivation

This project is part of a broader effort to understand how **neural dynamics give rise to temporal processing, robustness, and representation in the brain**, bridging ideas from neuroscience and machine learning.

---
