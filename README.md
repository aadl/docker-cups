# Supported tags and respective `Dockerfile` links

-	[`2.3.1` (*2.3.1/Dockerfile*)](https://github.com/aadl/docker-cups/blob/master/2.1.3/Dockerfile)

# What is CUPS?

CUPS is an open source printing system that supports IPP along with other protocols. More information can be found at [cups.org](http://cups.org/)

# About this image

This image is based off [ticosax/cups-in-docker](https://github.com/ticosax/cups-in-docker) with a few specific tweaks:

* Debian testing is used as the base image. Most of the cups updates are put into testing fairly quickly so no need for unstable. This may change in future if versions start lagging behind.
* The Debian snapshot service is used to pin the packages available to specific period of time. This is an easy way to ensure that the version provided in the tag is the one available. The snapshot will be moved over time to get security patches and debian specific changes are made, but a new tag created when a full release is available. More information on the snapshot service is available at http://snapshot.debian.org/

# Running this image

```bash
docker run -e CUPS_USER_ADMIN=admin -e CUPS_USER_PASSWORD=secr3t -p 6631:631/tcp aadl/cups
```
