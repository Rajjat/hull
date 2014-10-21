Hull.js - JavaScript library that builds concave hull by set of points.

## Examples

See live examples [here](http://andreygeonya.github.io/hull/)</a>.

## Usage

	var points = [ [236, 126], [234, 115], [238, 109], [247, 102], ... ];
	hull(points, 50); // returns points of the hull (in clockwise order)

## Params
* 1st param - array of coordinates in format: [[x1, y1], [x2, y2], ..., [xn, yn]];
* 2nd param - concavity. 1 - thin shape. Infinity - convex hull. By default 20.

## How it works

Let's see step by step what happens when you call `hull()` function:

<ol>

<li>Hull.js takes your source points of the shape:

<img src="https://raw.githubusercontent.com/AndreyGeonya/hull/master/readme-imgs/0.png" /></li>

<li>Builds convex hull:

<img src="https://raw.githubusercontent.com/AndreyGeonya/hull/master/readme-imgs/1.png" /></li>

<li>After that, the edges flex inward (according to `concavity` param). For example:

<img src="https://raw.githubusercontent.com/AndreyGeonya/hull/master/readme-imgs/2_1.png" />
`concavity = 80`

<img src="https://raw.githubusercontent.com/AndreyGeonya/hull/master/readme-imgs/2_2.png" />
`concavity = 40`

<img src="https://raw.githubusercontent.com/AndreyGeonya/hull/master/readme-imgs/2_3.png" />
`concavity = 20`</li>

</ol>

## Development
	npm install # install dependencies
	npm test	# build dist file and run tests

## Contribute

If you want to get involved with Hull.js development, just use <a href="https://guides.github.com/introduction/flow/index.html" target="_blank">github flow</a> and feel free to contribute!

## To-do

* make point formats configurable to support formats like `{x: 10, y: 10}` and `{lat: 52, lng: 82}`;
* add new map based example that demonstrates usage with other point formats;
* think about parallelisation of the calculations (on GPU or CPU);
* think about automatic `concavity` adjustment based on density.

## Related papers

* <a target="_blank" href="http://www.it.uu.se/edu/course/homepage/projektTDB/ht13/project10/Project-10-report.pdf">Implementation of a fast and efficient concave hull algorithm</a>;
* <a target="_blank" href="http://www.cs.jhu.edu/~misha/Fall05/09.13.05.pdf">Computational Geometry: Convex Hulls</a>;
* <a target="_blank" href="http://bryceboe.com/2006/10/23/line-segment-intersection-algorithm/">Line Segment Intersection Algorithm</a>;
* <a target="_blank" href="http://allenchou.net/2013/07/cross-product-of-2d-vectors/">Game Math: "Cross Product" of 2D Vectors</a>;
* <a target="_blank" href="http://users.livejournal.com/_winnie/237714.html">Угол между двумя векторами</a>;
* <a target="_blank" href="http://habrahabr.ru/post/105882/">Когда не нужна тригонометрия</a>.

## Changelog

### 0.2.0 — 20.10.2014
Second version with better performance inspired by <a href="http://www.it.uu.se/edu/course/homepage/projektTDB/ht13/project10/Project-10-report.pdf" target="_blank">this</a> article.
### 0.1.0 — 06.09.2014
First version based on Delaunay triangulation.
