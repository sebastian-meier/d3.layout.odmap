# d3.layout.odmap
d3 layout helper for origin-destination visualizations (od-maps). Using the helper one can switch between various visualizations without and data handling. Explore the examples here: http://prjcts.sebastianmeier.eu/odmap/example/index.html

![Examples](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/overview.png)

## Data

This layout helper takes care of the data handling for origin-destination visualizations. The data needs to be in the following format:

```
id,		x, y, id_1,	id_2
id_1,	1, 1, 1,	2
id_2,	1, 1, 1,	2
```
The first column holds the ids of all origins. x/y represent geographic coordinates. The other columns hold the origin destination data, the columns need to be have the same labels as the ids in the first column.

## Usage

```
od = d3.layout.odmap({
	//Size of the output visualization
	width:550,
	height:550
});

//Send the data
od.data(data);

```

To receive data for a certain visualization use on of the following functions:
```
var d = od.geo(od.geo());
var d = od.grid(od.grid());
var d = od.nmap(od.nmap());
var d = od.list(od.list());
var d = od.matrix(od.matrix());
var d = od.hand(od.hand());

//A little bit more specialized outputs
var d = od.sankey();
var d = od.bipartite();
```
Its easy to toggle between origin-destination and destination origin:

```
od.toggle();
```
![od-do](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/od-do.png)


After calling the toggle function require the data again. The nested functions allow to request different layouts for outer and inner positions:

```
var d = od.geo(od.hand());
```

![InsideOut](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/insideout.png)

Take a look at the interactive explorer: http://prjcts.sebastianmeier.eu/odmap/example/index.html

Most visualizations focus on the geographic space, but the layout also includes matrix and list views.

![Matrix](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/matrix.png)

And additionally data preparation for the biPartite plugin and the sankey plugin.

![biPartite](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/bipartite.png)
http://prjcts.sebastianmeier.eu/odmap/example/bipartite.html

![Sankey](https://raw.githubusercontent.com/sebastian-meier/d3.layout.odmap/master/img/sankey.png)
http://prjcts.sebastianmeier.eu/odmap/example/sankey.html
