CLIFF Docker
============

The official Docker image for the [CLIFF-CLAVIN](http://cliff.mediameter.org/) geolocation software. 

**Note: CLAVIN, and by extension CLIFF, is very memory hungry due to the geonames index. To properly 
run, a minimum of 4GB of RAM is necessary. Any less and you'll experience errors.**

Building the Image
------------------

Build using

```
docker build -t cliff:2.4.2 .
```

Running the Image
-----------------

It is setup to use the default port of `8080`. Run using

```
docker run -p "8080:8080" -d cliff:2.4.2
```

You can test it at a URL like:

```
http://localhost:8080/CLIFF-2.4.2/parse/text?q=This%20is%20some%20text%20about%20New%20York%20City,%20and%20maybe%20about%20Accra%20as%20well,%20and%20maybe%20Boston%20as%20well.
```

Acknowledgements
-----------------

This is forked from John Beieler's [cliff-docker](https://github.com/havlicek/cliff-docker),
which pulls heavily from Andy Halterman's [CLIFF-up](https://github.com/ahalterman/CLIFF-up) Vagrant box.
