# Procedural-Noise

This is a collection of procedural noise algorithms I have collected from various places over the years. They have been reworked into a common framework I use and can be added to a fractal noise object to turn the noise into a fractal. Each noise supports sampling in 1, 2 and 3 dimensions.

## Perlin Noise

First there's the classic Perlin noise. If your interested in procedural noise this is often the standard.

![Perlin Noise](./Media/Perlin.png)

## Value Noise

This is just Perlin noise but instead of using gradients for the noise its the actual value that's used. By that I mean its just a lattice of random values interpolated. The whole point of gradient noises like Perlin is that they produce better quality noise. Using the value tends to create a blocky looking noise but if that's the effect you want then this will be better and a bit cheaper to compute as well.

![Value Noise](./Media/Value.png)

## Simplex Noise

This is a improvement on Perlin and is better quality with less artifacts. Perlin is classed as lattice noise as it subdivides space into a grid of blocks. Simplex noise changes this by dividing space into a simplex rather than a block. A simplex is just the smallest convex set that can exists in a certain dimension of space. For example a line in 1D space, a triangle in 2D space and a tetrahedron in 3D space. Beyond 3D its just called a N-Simplex.

The implementation for this noise was found [here](http://staffwww.itn.liu.se/~stegu/aqsis/aqsis-newnoise/).

![Simplex Noise](./Media/Simplex.png)

## Voronoi Noise

A Voronoi diagram is just a distance field from a random set of points. The concept can be used to create noise if you just sub-dive space into blocks with a random number of points in each and then use the distance of the closest point as the noise value. By changing the distance method used and how the closest points are combined you can create a variety of interesting noises.

This implementation for this noise was found [here](https://aftbit.com/cell-noise-2/).

![Voronoi Noise](./Media/Voronoi.png)

## Worley Noise

This is just another method of generating Voronoi noise. It looks pretty much the same but is slightly different with the values being more uniform.

![Worley Noise](./Media/Worley.png)
