# 17.04.

### Todo

1. **Einarbeitung Thema KI/Polyhedra**

	1. KI: Verständnis für die Problemstellung entwickeln. Warum machen wir diese Art der Analyse? Was ist das Ziel?
	2. Polyhedra: Einstatz bei klassicher SW. Was wird da gemacht?
	3. Polyhedra: Einsatz bei KI Analyse. Warum bringt das was? Wo liegen Grenzen?

2. **Definition der Properties für die Klasse „Clustering“**

	1. Datentyp: Implementierung gemäß (P1) und (P2) aus _3 ) Definition of Polyhedron_ (siehe Paper im Anhang: Seite 8)
	2. Hinweis: Nutze „gebräuchliche“ Datenformate ;)
	3. Hinweis: Wir arbeiten erstmal „nur“ in 3D, d.h. jeder _Punkt_ im Raum ist durch 3 Dimensionen definiert

3. **Erste** (initiale) **Funktion zur Extraktion und Berechnung von P1 und P2**

	1. Hinweis: Siehe Funktion „plot_3D_cluster“ in clustering.py
	2. Hinweis: Wie kann mit verschiedenen Einheiten umgegangen werden?

### 1.
##### 1.1
dissimilarity between ML models with clustering -> correlation of FP and FN of a model
##### 1.2
###### Vertex-Face
A list of vertices:  `List[Tuple[float, float, float]]`
A list of faces: `List[List[int]]`, where each face is a list of indices into the vertex list.

**Pros:**
Simple, Easy to plot
**Cons:**
Inefficient operations if adjacaency not implemented in an extra structure

###### Graph
Vertices -> Nodes

**Pros**
Probably useful for when transforming polygons / topology
**Cons**
not suited for the application, topology not that important

###### Convex Hull
Set of points -> construct a convex Hull

**Pros**
Probaby very easily implemetable with a library
**Cons**
Has to be convex, depending on implementation but probably nightmare to work with

###### Inequalities / Linear programming
Polyhedron $P$ in $\mathbb{R}^n: \quad P = \{x | Ax \leq b\}$ where $A$ is a $\mathbb{R}^{m \times n }$ matrix and $b$ a $\mathbb{R}^{m \times 1 }$ vector
- Def 7 of [[Lecture2.pdf]]

**Pros**
Linear programing, Integer programing, Robust optimization 
**Cons**
Rendering computationally expensive, A lot of linear Algebra, Polygon cant be too much concave (best if concave)

###### Constructive Solid Geometry
Basic shapes + bollean operations

**Pros**
multiple convex Linear programming polygons to create a concave one, Probably fairly easy implementation for complex cases, maybe even discontinuaous shapes
**Cons**
overkill to use with linear programing? Not as compatible as I think?
###### Edge Based
- Winged Edge Data Structure
- Doubly Connected Edge List
- Halfedge Data Structure 
- Quad Edge Data Structure
[[eth-4320-01.pdf#page=6]]

**Pros**
Efficient traversal and editing
**Cons**
Optimazation may be tough to implement

##### 1.3
clustering boundaries, optimization problems
Limitations: 
- Scalability
- Reproducibility of results? -> computationally expensive comparisons
- Approximation errors

### 2.

easiest  to implement would be the Vertex-Face approach and make a convex hull of all points in a cluster


### 3.
