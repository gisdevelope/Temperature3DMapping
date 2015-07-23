Temperature3DMapping
------
This directory contains documentation for TempMapping3D-software.

With this software, user can create 3D- and 2D-graphs of room temperature. These graphs can be used in designing Finnsaver-systems that reduce waste heat in rooms.

Requirements
-----------

Using software requires following software and hardware: 

  - Measurement rod with atleast three [Ciseco XRF Dallas sensor boards](http://shop.ciseco.co.uk/temperature-xrf-development-sensor-dallas-ds18b20/) placed in different heights.
  - [Ciseco SRF-Stick](http://shop.ciseco.co.uk/srf-stick-868-915-mhz-easy-to-use-usb-radio/).
  - [(UART-adapter for programming new XRF-boards)](https://www.sparkfun.com/products/11812).
  - .NET-Framework 4.5.

Editing source code requires following third-party resources:

  - [OxyPlot-libraries](https://oxyplot.codeplex.com/).
  - [HelixToolkit-libraries](https://helixtoolkit.codeplex.com/).
  - [EntityFramework](http://msdn.microsoft.com/fi-fi/data/ef.aspx).

How does it work?
-------------
Room is assigned with X/Y-coordinates (amount of coordinates can be set by user). Then at each X/Y-coordinate, temperatures are taken with three Ciseco XRF wireless serial data boards that utilize Dallas DS18B20 temperature sensors. Ciseco XRF transfers temperatures through wireless serial port to software and software saves these temperature values along with coordinates and some other variables to sqlite-database.

After all temperatures and all other information about measurement is saved to database, user can show different graphs about these measurements. 2D-graphs are created with OxyPlot-library and can visualize data with heatmap, temperature values or with both. 3D-graphs are created by first making a 2D-graph of each sensor with OxyPlot and after that these 2D-graphs are transfered to 3D-form with HelixToolkit-library. 3D-graphs can be rotated and zoomed. User can save these 2D and 3D graphs in a fancy report-format.

Screenshots
-------

Measurement session in progress:

![picture](./images/measurement_in_progress.JPG?raw=true)

2D-reports of temperature mapped room and three different possible graph styles (in real world all graphs of 2D-report would use same style):


From top of room -perspective:
![picture](./images/2D_report.JPG?raw=true)   

From side of room -perspective:
![picture](./images/2D_report_from_side.JPG?raw=true)

Savings report:

![picture](./images/SavingsReport.JPG?raw=true)

NOTICE! 3D-report is not complete as it will not be used in final product.

3D-report of temperature mapped room:

![picture](./images/3D_report.JPG?raw=true)  

-------------------------------------------------------------------------------
Copyright (c) Jarmo Puttonen <jarmo.puttonen@gmail.com>

Copyright (c) Finnfuture Oy <tsto@finnfuture.fi>
