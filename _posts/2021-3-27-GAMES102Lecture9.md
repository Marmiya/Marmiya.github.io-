---
layout: post
title: GAMES-102 Lec9 NOTES
subtitle: NOTES
cover-img: /assets/img/path.jpg
thumbnail-img: 
tags: [notes]
---

## Differential coordinate

### 1. Laplace Operator

* Gradient $$\nabla f$$:

  * $$
    \Delta f=\nabla\cdot\nabla f=\nabla^2f
    $$

* 

* In Cartesian coordinate system:

  * $$
    \Delta f=\sum_{i=1}^{n}\frac{\partial^2f}{\partial x^2_i}
    $$

* 

* 

* Particularly, for binary real function:

  * $$
    \Delta f=\frac{\partial^2f}{\partial x^2}+\frac{\partial^2f}{\partial y^2}
    $$

* 

### 2. Mean Curvature Flow Theorem

![](/assets/img/MCFC.png)
$$
\frac{1}{len(\gamma)}\int_{v\in \gamma}(\pmb{v_i}-\pmb{v})ds
$$

$$
\lim_{len(\gamma)\rightarrow 0}\frac{1}{len(\gamma)}\int_{v\in \gamma}(\pmb{v_i}-\pmb{v})ds=H(\pmb{v_i})\pmb{n_i}
$$

_Discrete form:_

![](/assets/img/MCFD.png)
$$
\pmb{\delta}_i = \frac{1}{d}\sum_{v\in N(i)}(\pmb{v}_i-\pmb{v})
$$
**Weighting Schemes**:

Cotangent weight:
$$
w_j=(\cot{\alpha}+\cot{\beta})
$$

### 3. Global  Laplacian Smoothing

![](/assets/img/GLS.png)

### 4. Mesh Parameterization

**SETPS**:

* Detect boundary
* Map the boundary to square's or circle's boundary (Convex boundary) 
* Construct sparse functions
* Resolve sparse functions
* Renew vertexes' coordinates
* Connect texture image, renew display