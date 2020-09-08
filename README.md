CLIFF Docker
============

The official Docker image for the [CLIFF-CLAVIN](http://cliff.mediacloud.org/) geolocation software.

**Note: CLAVIN, and by extension CLIFF, is very memory hungry due to the geonames index. To properly
run, a minimum of 4GB of RAM is necessary. Any less and you'll experience errors.**

Building the Image
------------------

Build using

```
docker build -t cliff:2.6.1 .
```

Running the Image
-----------------

It is setup to use the default port of `8080`. Run using

```
docker run -p "8080:8080" -d cliff:2.6.1
```

The first time it runs it will take a while to load all the data. You can watch the docker logs to monitor the progress.
Web requests won't return anything valid while it is loading.

Once it is loaded, you can test it at a URL like:

```
http://localhost:8080/cliff-2.6.1/parse/text?q=This%20is%20some%20text%20about%20New%20York%20City,%20and%20maybe%20about%20Accra%20as%20well,%20and%20maybe%20Boston%20as%20well.
```

Debugging
---------

This takes a lot of memory, so if it doesn't work keep an eye on the docker log for "java.lang.OutOfMemoryError: Java heap space" errors.

Acknowledgements
-----------------

This is forked from John Beieler's [cliff-docker](https://github.com/havlicek/cliff-docker),
which pulls heavily from Andy Halterman's [CLIFF-up](https://github.com/ahalterman/CLIFF-up) Vagrant box.
