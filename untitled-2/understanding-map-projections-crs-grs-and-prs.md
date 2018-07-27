# 04. Understanding CRS, GCS and PCS

This chapter gives a summary of the concepts of Coordinate Reference System \(CRS\) \(also referred to Spatial Reference System \(SRS\)\), Geographic Coordinate System \(GCS\) and Projected Coordinate System \(PCS\). It is followed by a simple exercise to illustrate the practical implication of using different coordinate systems during design. For a complete explanation of these concepts please refer to the QGIS guide: [**Coordinate Reference Systems**](https://docs.qgis.org/testing/en/docs/gentle_gis_introduction/coordinate_reference_systems.html#figure-projection-families).

* **Coordinate Reference System \(CRS\)**: A reference system to pin-point any point on earth by specifying a set of two to three numbers \(horizontal position \(east or west\), vertical position \(north or south\) & elevation \). There are two types of CRS; GCS and PCS:
  * **Geographic Coordinate System \(GCS\)**: Uses a 3D spherical surface; an ellipsoid, to pin-point location on the earth. A GCS is defined by a Datum \(ellipsoid model\), prime meridian and the unit of the coordinates. [Different GCS uses different ellipsoid to define the shape of the earth](http://support.virtual-surveyor.com/support/solutions/articles/1000261329-what-is-an-ellipsoid-), [different longitude as its prime meridian](https://en.wikipedia.org/wiki/Prime_meridian), and different units for coordinates. Usually degrees of Latitude and Longitude are used as coordinates to specify any point on the map.  [**The World Geodetic System 1984** \(**WGS84**\)](http://support.virtual-surveyor.com/support/solutions/articles/1000261351-what-is-wgs84-) is the most commonly used GCS, map services like Google Map uses WGS84. 
  * **Projected Coordinate System \(PCS\)**: The projected GCS on a 2D plane \(map\). In a PCS, the units for the coordinates are in metres. There are many different projections. Different projections can lead to many surveying errors, as it is not possible to accurately project a spherical surface onto a 2D plane. Different projections will produce different distortions. A projection is usually chosen based on the scale, extent and resolution of the region to be projected. One interesting example that shows the consequences of using differing projection is the use of the [Mercator projection drastically shrinking the size of Africa as compared to other countries in the world](https://edition.cnn.com/2016/08/18/africa/real-size-of-africa/index.html). Typically, every country will decide on the optimal projection to used. As urban designers and architects, we just have to follow the the standard PCS. Singapore uses the SVY21 coordinate system.

## Setting CRS

**1.\) Before starting this exercise, please refer to the "**_**Obtain Singapore Master Plan**_**" & "**_**Import Shapefile into QGIS**_**" chapters.**

**2.\) Import the "Master Plan 2014 Land Use" shapefile . Right click on the layer and choose set CRS -&gt; Set Layer CRS**

![](../.gitbook/assets/image%20%28123%29.png)

**3.\) Singapore uses the SVY21 CRS. Search for SVY21 and choose the SVY21/ Singapore TM EPSG: 3414. While you click on the CRS, you will be able to see the extent the CRS covers.**

![](../.gitbook/assets/image%20%283%29.png)

**4.\) Set the CRS for the whole project by clicking the CRS symbol at the bottom right of window. The project CRS sets the CRS for the canvas. This will not affect the CRS of the individual layers. It is best to unify the CRS for the project and the layers to ensure that all layers are at their right position. When different CRS are used between different layers, maps will not be able to coincide with each other.** 

![](../.gitbook/assets/image%20%28145%29.png)

**5.\) Once you click the symbol the CRS System Selector will pop out. Search for SVY21/ Singapore TM EPSG: 3414 and choose the CRS.**

![](../.gitbook/assets/image%20%28148%29.png)

**6.\) Both the layer CRS and project CRS are set.**

![](../.gitbook/assets/image%20%2860%29.png)

**7.\) Next we will demonstrate how the map will warped when different CRS is used for the project and layer CRS. We changed the project CRS to epsg: 5850. As a result, the map is distorted as shown.**

![](../.gitbook/assets/image%20%2871%29.png)

**8.\) We revert back to the right CRS SVY21.** 

![](../.gitbook/assets/image%20%28120%29.png)

**9.\)We import another shapefile, the "Master Plan 2014 Building".** 

![](../.gitbook/assets/image%20%28116%29.png)

**10.\) Turn off the "G\_MP14\_LAND\_USE\_PL" layer. You will see the building footprints of the "G\_MP14\_BLDG\_PL" layer.**

![](../.gitbook/assets/image%20%2872%29.png)

**11.\) Next change the CRS of the "G\_MP14\_BLDG\_PL" layer. Choose epsg: 5850. The footprints will disappear.**

![](../.gitbook/assets/image%20%2836%29.png)

**12.\) Right click on the "G\_MP14\_BLDG\_PL" layer and click zoom to layer. The PCS distorted the building footprints so much, that it is not possible to see the footprints.**

![](../.gitbook/assets/image%20%2863%29.png)

**13.\) Revert back to the right CRS for the "G\_MP14\_BLDG\_PL" layer. You will be able to see the footprints again. Always remember to standardised your project and layer CRS. So as to be able to see all your data.**

![](../.gitbook/assets/image%20%287%29.png)



