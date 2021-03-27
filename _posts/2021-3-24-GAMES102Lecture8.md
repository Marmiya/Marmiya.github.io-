---
layout: post
title: GAMES-102 Lec8 NOTES
subtitle: NOTES
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/lec8.png
tags: [notes]
---

## Discrete differential geometry

### 1. Half-edge Data Structure

Every edge is expressed two "half-edge".

A half-edge includes:

* Starting points
* The other pair of half-edge
* A face
* Next half-edge

### 2. Differential Geometry of Curve and Surface

![](/assets/img/doc.png)

![](/assets/img/dos.png)

### 3. Discrete differential geometry

**Approximate the (unknown) underlying surface**

* Continuous approximation
* Discrete approximation

#### Continuous approximation

* At each mesh vertex (using surrounding triangles)
  * Compute normal at vertex
    * Typically average face normals
  * Compute tangent plane and local coordinate system.
  * For each neighbor vertex compute location in local system 

* Find quadric function approximating vertices
  $$
  F(x,y,z)=ax^2+bxy+cy^2-z=0
  $$

* To find coefficients use least squares fit
  $$
  min\sum_{i}(ax^2_i+bx_iy_i+cy_i^2-z_i)
  $$

#### Discrete Approximation

Mean Curvature

Gauss Curvature