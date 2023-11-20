# Interactive piecewise linear maps

For an interactive version of the below see <a href="https://www.dtubbenhauer.com/pl-reps/site/index.html">https://www.dtubbenhauer.com/pl-reps/site/index.html</a>.

# Code for *Equivariant neural networks and piecewise linear representation theory*

I collected Mathematica code relevant for the paper *Equivariant neural networks and piecewise linear representation theory*
<a href="https://arxiv.org/abs/2307.03044">https://arxiv.org/abs/2307.03044</a> on this page.

The code is in **.n** files that can be downloaded from this site and you can run it with Mathematica.

An Erratum for the paper *Equivariant neural networks and piecewise linear representation theory* can be found at the bottom of the page.

# Contact

If you find any errors in the paper *Equivariant neural networks and piecewise linear representation theory* **please email me**:

[dtubbenhauer@gmail.com](mailto:dtubbenhauer@gmail.com?subject=[GitHub]%web-reps)

You can also email Joel Gibson and Geordie Williamson. Same goes for any errors related to this page.

Also, let me know if there are any questions!

# The Mathematica code - interaction graphs

The code is hopefully pretty straightforward, so let me only comment on the various pieces briefly.

```
SizeTable := {0.07, 0.2, 0.2, 0.3, 0.3, 0.3, 0.4, 0.4, 0.4, 0.4, 0.5, 
   0.5, 0.6, 0.7, 0.8, 0.8, 0.9, 0.9, 1.1, 1};
```

is for scaling the output, and can be changed if needed.

The graphs for ReLU and Abs are the created using

```
AdMatrix[n_] := 
  Table[If[i == j, 1, 
    If[Divisible[OrderActionP[n, i - 1], OrderAction[n, j - 1]], 1, 
     0]], {i, 1, Length[Division[n]]}, {j, 1, Length[Division[n]]}];
AdMatrixAbs[n_] := 
  Table[If[Divisible[OrderActionP[n, i - 1], OrderAction[n, j - 1]], 
    1, 0], {i, 1, Length[Division[n]]}, {j, 1, Length[Division[n]]}];
```

The rest of the code is for visualiztion purpuses only.

For example, here is the cyclic group of order eight:

![Z mod 8 Z](https://github.com/dtubbenhauer/pl-reps/blob/main/graphs.png))

# The Mathematica code - plot of maps

The file cyclic-maps.nb contains the plots of maps from 2d representations to the trivial representation of the cyclic group. The maps have been precomputed with coordinates stored in

```
XX
```
The maps are then animated (the style can be easily changed) using, for example

```
Animate[{Plot3D[PlotFunction[n, a, b], {a, -3, 3}, {b, -3, 3}, 
   PlotPoints -> 45, ImageSize -> 400, MaxRecursion -> 0], 
  ContourPlot[PlotFunction[n, a, b], {a, -3, 3}, {b, -3, 3}, 
   PlotPoints -> 40, ImageSize -> 400, MaxRecursion -> 0]}, {n, 1, 8, 
  1}, LabelStyle -> {20}, DefaultDuration -> 70]
```
One gets the following pictures:

![A map](https://github.com/dtubbenhauer/pl-reps/blob/main/to-trivial.png))

# Erratum

Empty so far.
