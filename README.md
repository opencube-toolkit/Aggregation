OpenCube Aggregator
==============================

The role of the Aggregator is twofold. First, given an initial cube with n dimensions the aggregator creates 2^n-1 new cubes taking into account all the possible combinations of the n dimensions. Second, given an initial cube and a hierarchy of a dimension, the aggregator creates new observations for all the attributes of the hierarchy.
 

###How it works

The OpenCube Aggregator is developed as a separate component of the OpenCube toolkit and is part of the “Data Expanding” lifecycle step. The Aggregator component can be easily initialized by creating a widget.

Widget configuration:

```
{{#widget: AggregationSetCreator}}
```
 

###Functionality

 
The OpenCube Aggregator distinguishes two categories of aggregation:

+ **Aggregation across a dimension**. In this case the observations are aggregated across one of the dimensions of the cube. For example, compute the SUM of the sales over time and thus ignore the time dimension of the cube. This type of aggregation enables the “Add Dimension” functionality of the OpenCube Expander.
+ **Aggregation across a hierarchy**. In this case the observations are aggregated across a hierarchy of a dimension. For example, if a cube contains the election results at municipality level, then the Aggregator can compute the results at region and at country level with the prerequisite that the corresponding hierarchy (municipality > region> country) exists. Note that the opposite is not possible, i.e. to go down from the country level to regions and municipality. This type of aggregation enables the “Add hierarchy” functionality of the OpenCube Expander.

The aggregate function that can be applied to a cube depends on the following parameters:

+ The dimensions and measures of a cube. For example, the SUM function can be applied to the sales measure over time, while it cannot be applied to the election results over time.
+ The measure’s unit of the cube. For example, if a cube’s unit is “percentage” the SUM or AVG functions cannot be applied to the observations.



