---
layout: gettingstarted
title: Setting Up GeoTrellis

tutorial: gettingstarted
num: 3
outof: 9
---

### Configuration

The main application configuration defines important system parameters used by
your application. Some are required by GeoTrellis, while a particular
application might introduce others.

The configuration file should be on the classpath of your application. When
using SBT, the file is often located at `src/main/resources/application.conf`.

You can also override individual configuration parameters with Java system
properties, e.g. `java -Dgeotrellis.port=5555 ...`

Example:

    // server address to listen on
    geotrellis.host = "0.0.0.0"

    // server port to listen on
    geotrellis.port = 8888

    // package to search for REST services
    geotrellis.rest-package = "myapp.rest"

    // location for temporary files
    geotrellis.tmp = "/tmp"
