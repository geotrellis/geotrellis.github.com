---
layout: tutorials
title: Running the Demo

tutorial: tutorials
num: 2
---

If you want to see GeoTrellis in action, this tutorial will show you how to run the GeoTrellis demo project.

The code for the demo project can be found in the [demo
folder of the source.](https://github.com/geotrellis/geotrellis/tree/0.8/demo/src/main/scala/demo)

The AMI has a script to start the demo service, called ```start-demo-server.sh```

#### Running from SBT

Clone GeoTrellis from github: 

`git clone https://github.com/geotrellis/geotrellis`

Start sbt!: 

`cd geotrellis`
`./sbt`

At the sbt prompt, switch to the demo project and run:

`> project demo`<br/>
`[info] Set current project to demo (in build file:...)`<br/>
`> run`<br/>
`...`<br/>
`Starting server on port 8000.`<br/>

Now the GeoTrellis demo server is listening to port 8000 on localhost. You can try out the various demo services
by hitting these endpoints with your browser:

- [/demo1](http://localhost:8000/demo1)
- [/greeting](http://localhost:8000/greeting)
- [/adder/5](http://localhost:8000/adder/5)
- [/bbox/0,0,5,5/union/4,4,10,10](http://localhost:8000/bbox/0,0,5,5/union/4,4,10,10)
- [/simpleDraw/SBN_RR_stops_walk](http://localhost:8000/simpleDraw/SBN_RR_stops_walk)
- [/draw/SBN_inc_percap/palette/ECBE1D,E77124,A33936,7F182A,68101A/shades/150](http://localhost:8000/draw/SBN_inc_percap/palette/ECBE1D,E77124,A33936,7F182A,68101A/shades/150)
