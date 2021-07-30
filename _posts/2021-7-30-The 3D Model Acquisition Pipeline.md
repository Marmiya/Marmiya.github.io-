---
layout: post
title: The 3D Model Acquisition Pipeline
subtitle: NOTES
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/lec8.png
tags: [notes]
---

# The 3D Model Acquisition Pipeline

## Attention: This is a 2002 Eurographics paper, something in it may be out-of-date.

## Basic

### Range image

- produce a 2D image showing the distance to points in a scene from a specific point

### Resolution

- the smallest distance between two points that the instrument measures

### Triangulation

- Defination

	- a subdivision of a planar object into triangles, and by extension the subdivision of a higher dimension geometric object into simplices

- Delaunay Triangulation

	- For general position

		- No (d + 1) points lie in a common (d-1)-dimensional plane
		- No (d + 2) points lie in a common (d-1)-sphere

	- no point in P is inside the circumcircle of any triangle in DT(P)

### Delaunay complex D(S)

- associated with a set of points S in R3 decomposes the convex hull of S and imposes a connectivity structure

### Photometric stereo

- uses N images of an object from a single viewpoint under N different lighting conditions

## Range Scanners

### Triangulation systems

### Time-of-flight systems

## Registration

### Registration of two views

- ICP(Iterative Closest Point)

	- Euclidean closest point
	-  find the intersection between a line normal to the first surface at the given point and the second surface, then minimize the distance between the given point and the tangent plane to the second surface at the intersection point

		- Pros:

			- less sensitive to non-uniform sampling
			- poses no penalty for two smooth surfaces sliding tangentially 

### Registration of multiple views

- incremental approach

	- Bergevin's method 

		- One of the views is selected as the central (or reference) view. All the other views are transformed into the reference frame of the central view. At each iteration, each view is registered with respect to all other views using a varaition of Chen and edioni’s method. The process is repeated until all  incremental registration matrices are close to the identity matrix

	- Pulli's method

		- By using a small number of pairs of points in the global registration phase, the need to have all the scans in memory is eliminated.

- other method

	- simulated annealing algorithm
	- Levenberg-Marquardt method

### Using the textures to aid registration

- Texture images may be used in the initial alignment phase
- Texture images may also be used in the refinement of the initial alignment

	- the color image values are used as additional coordinates defining each point captured in the scan
	- matching operations are performed using the images directly

## Line-of-sight Error

### the effects of viewing angle and distance

- an uncertainty ellipsoid defined by a Gaussian distributaion
- For atypical triangulation scanner, the error in x, y position is smaller than the error in depth z

### non-Gaussian error

- shadows
- surface specularities
- depth discontinuities

### Resolution

- Rutishauser's method(which is a reconstruction method)

	- define an optimal reconstruction of a surface from two sets of estimates, in the sense of probability theory

- Soucy and Laurendeau model error in a laser triangulation system as proportional to the fraction of illuminance received by the sensor, expressed by the cosine square of the angle between the surface normal at the measured point and the sensor viewing direction
- Turk and Levoy employ a similar method, but invert the steps of creating a triangulated surface and finding better surface position estimates
- Neugebauer adjusts point positions along the scanner line-of-sight

## Scan Integration

### Input data

- unorganized points(point cloud)

	- Techniques that deal with this are more general, but usually less robust in the presence of noise and outliers

- a set of range scans

	- Because of estimated surface normal, partial connectivity, sensor position, it is better estimate the actual surface

### Delaunay-based methods

### Surface-based methods

- create the surface by locally parameterizing (or implicitly assuming a local parameterization of) the surface and connecting each points to its neighbors
by local operations.

### Volumetric methods

- based on computing a signed distance field in a regular grid enclosing the
data (usually, only in proximity of the surface), and then extracting the zero-set of the trevorite function using the marching cube algorithm

### Deformable

## Postprocessing

### common use of mesh simplification

## Texture

### the rendering of high quality images requires the fine scale surface appearance

### BRDF

### Texture-geometry registration

- registration by calibration
- Finding the camera position and orientation associated with a 2D image of a 3D object is the well-known camera calibration problem.

### Illumination invariance

### Direct use of captured images

- Lambertian reflectance

## Texture Map Reconstruction

### combining all the texture maps acquired for an object into a single non-redundant
map over the entire object

### Methods for reconstructing texture from sets of images have in common that for each texture image, the triangles visible in that image are identified. 

## Need of improvement

### planning method for data acquisition

### reliable capture and robust processing of data for a larger class of objects, including large size objects, environments, and objects with challenging surface properties

### automation of all the steps, to minimize user input

### real-time feedback of the acquired surface

### improved capture and representation of surface appearance

### methods for assessing global model accuracy after range scan registration

*XMind - Evaluation Version*
