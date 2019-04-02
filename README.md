# Interactive Analysis of Large-Scale Spatial Vector Data via Visualization-oriented Computing (DEMO)
To address the scale issue for analysis of large-scale spatial vector data, we present a new spatial analysis computing model, visualization-oriented computing (VOC), for interactive analysis of large-scale spatial vector data. As show in Fig 1, VOC generates analysis results by directly determining the value of each pixel for display. Different from data-oriented computing (DOC) (see Fig 2) in traditional analysis methods, the computing units in VOC are pixels rather than spatial objects. As the number of pixels in the screen range is limited and stable, VOC has the advantage of being insensitive to data volumes.



![fig1](./figures/fig1.JPG)

*Fig1. Spatial analysis via visualization-oriented computing*

![fig2](./figures/fig2.JPG)

*Fig2.  Spatial analysis via data-oriented computing*



## Setting


***Tab1. Datasets of Demo 1: Roads, POI and Farmland of Mainland China (10-million-scale)***

| Name           | Type       | Records    | Size                 |
| -------------- | ---------- | ---------- | -------------------- |
| China_Road     | LineString | 21,898,508 | 163,171,928 segments |
| China_POI      | Point      | 20,258,450 | 20,258,450 points    |
| China_Farmland | Polygon    | 10,520,644 | 133,830,561 edges    |

***Tab2. Datasets of Demo 2&3:  Spain Datasets from [OpenStreetMap](https://download.geofabrik.de/europe/spain-latest.osm.pbf)*** ([Classification standard](https://wiki.openstreetmap.org/wiki/Map_Features))

| Name                                  | Type       | Records   | Size                |
| ------------------------------------- | ---------- | --------- | ------------------- |
| Amenity_Education                     | Point      | 6,994     | 6,994 Points        |
| Amenity_Entertainment, Arts & Culture | Point      | 6,928     | 6,928 Points        |
| Amenity_Financial                     | Point      | 13,040    | 13,040 Points       |
| Amenity_Healthcare                    | Point      | 14,757    | 14,757 Points       |
| Amenity_Sustenance                    | Point      | 89,282    | 89,282 Points       |
| Amenity_Transportation                | Point      | 3,114     | 3,114 Points        |
| Shop                                  | Point      | 82,192    | 82,192 Points       |
| Religion                              | Point      | 6,219     | 6,219 Points        |
| Historic                              | Point      | 14,974    | 14,974 Points       |
| Leisure                               | Point      | 8,334     | 8,334 Points        |
| Tourism                               | Point      | 36,462    | 36,462 Points       |
| Places                                | Point      | 582,464   | 582,464 Points      |
| Public_Transport                      | Point      | 45,478    | 45,478 Points       |
| Railway                               | Linestring | 97,675    | 309,716 Segments    |
| Highway                               | Linestring | 3,132,496 | 42,497,196 Segments |
| Waterway                              | Linestring | 33,214    | 4,254,732 Segments  |
| Natural_Beach                         | Point      | 148       | 148 Points          |
| Natural_Cave                          | Point      | 3,237     | 3,237 Points        |
| Natural_Cliff                         | Point      | 155       | 155 Points          |
| Natural_Peak                          | Point      | 28,106    | 28,106 Points       |
| Natural_Spring                        | Point      | 4,780     | 4,780 Points        |
| Natural_Tree                          | Point      | 533,856   | 533,856 Points      |
| Natural_Volcano                       | Point      | 13        | 13 Points           |
| Water_Area                            | Polygon    | 60,319    | 2,044,622 Edges     |
| Pois_Area                             | Polygon    | 279,010   | 2,462,611 Edges     |
| Pofw_Area                             | Polygon    | 23,337    | 265,523 Edges       |
| Natural_Area                          | Polygon    | 4,034     | 114184 Edges        |
| Places_Area                           | Polygon    | 4,133     | 273,679 Edges       |
| Landuse_Area                          | Polygon    | 459,946   | 18,528,176 Edges    |
| Buildings_Area                        | Polygon    | 2,039,096 | 14,829,921 Edges    |

***Tab3.  Demo Environment***

| Item             | Description                                    |
| ---------------- | ---------------------------------------------- |
| CPU              | 4core, Intel(R) Xeon(R) CPU E5-2680 v3@2.50GHz |
| Memory           | 32 GB                                          |
| Operating System | Centos7                                        |



## Application Scenarios

### [Demo 1](http://www.higis.org.cn:8080/hibuffer10million/) (Buffer analysis of 10-million-scale China datasets)

The 10-million-scale datasets (see Tab 1) used in the demonstration are provided by map service providers. As the datasets are not open published, the raw datasets are encrypted by adding offsets. The interface of the demonstration is simple to use, choose a dataset, input the buffer radius and click the Enter button, then the result layer will be added to the map in real time. Fig 3 shows the analysis results.

![fig3](./figures/fig3.JPG)

*Fig 3. Buffer analysis results of demo 1*

### [Demo 2](http://www.higis.org.cn:8080/hibo/) (Overlay analysis for housing site selection in Spain)

We have designed a housing site selection scenario for VOC based overlay analysis. Suppose that a new immigrant in Spain wants to choose a place to live which meets the following conditions: 1) convenient to traffic (within 500m from Highways); 2) convenient for children education (within 200m from Education amenities); 3) convenient to the medical care (within 2000m from Healthcare amenities); 4) near to leisure places (within 1000m from Entertainment, Arts & Culture amenities or Waterways but not in Water Area); 5) quiet (at least 300m away from Railways). The conditions can be translated into the following expression. Enter the expression and click the Create-Overlay-Layer button (Fig 4), then the result layer will be added to the map in real time. Fig 5 shows the analysis results, in which the red areas are the recommended housing places for the immigrant. 


![eq](./figures/eq.JPG)


![fig4](./figures/fig4.JPG)

*Fig 4. Input of the housing site selection in Spain*

![fig5](./figures/fig5.JPG)

*Fig 5. Analysis result of the housing site selection in Spain*

## Contact:

Mengyu Ma@ National University of Defense Technology

Email: mamengyu10@nudt.edu.cn

Tel:+8615507487344
