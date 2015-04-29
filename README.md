OpenCube Aggregation component
==============================

The OpenCube Aggregation component creates a set of Data Cubes out of an existing cube by summarizing observations across one or more dimensions. 
The resulted cubes define an Aggregation Set.

### How it works

The OpenCube Browser is developed as a separate component of the OpenCube toolkit and is part of the “Transform Cube” lifecycle step.
The Aggregation component can be easily initialized by creating a widget. 

Widget configuration: 
```
{{#widget: AggregationSetCreator}}
``` 

###Functionality

OLAP style browsing includes functionalities such as drill-down and roll-up. A special case of these functionalities is introducing and reducing a dimension.
In order to be able to browse a cube by removing or introducing dimensions we need to calculate the summaries of the observations across all the combinations
 of the dimensions of the cube. This activity creates a set of cubes that share one or more dimensions and describe the same measure. For example, in the case of
  a data cube that describes crime incidents per country, year and crime category, we could create 7 more cubes by summarizing the observations across one or more
  dimensions. In the same example, one of the resulted cubes could describe all crime incidents per country and year. The produced cubes are exploited by other 
  components e.g. the OpenCube Browser in order to enable OLAP style browsing.
 




 