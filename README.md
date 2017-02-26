## To build and run osmo-nitb on LimeSDR
### *Semi-working edition*
#### [Help wanted](https://github.com/emilf/LimeSDR-GSM-Dockerized/issues/new)
[![Build Status](https://travis-ci.org/emilf/LimeSDR-GSM-Dockerized.svg?branch=master)](https://travis-ci.org/emilf/LimeSDR-GSM-Dockerized)

To build and run the container, just execute `./startContainer` and clean up with `./killContainers`
Nb. Assuming you are not using docker for anything else! Please don't use **killContainers** unless you are willing to lose all containers on the box. It does not clean up images, so keep that in mind.

* Why docker?
 * Well, I run Arch Linux and all guides assume Ubuntu, so either I could find all the correct libraries of the correct versions and somehow make that all work (and I did try, though not for long) or I could just run it in a container, thus making it much easier.
* Does it work?
  * Well, no. And it doesn't start the processes within the container automatically either, but starting it all manually does bring it up and a scan shows a network with the correct MCC-MNC. I can however not connect to that network.
* So what's wrong with it?
 * Being rather new to all of this, I don't know and I don't know how to find out. However, I suspect the configs are a bit off for LimeSDR, since those were copied from instructions intended for another type of BTS hardware. Any help is appreciated.

pysim is included, even if only marginally related, as I needed a specific older revision of it for it to work with my sysmocom USIMs, so I like having it around.

#### TODO
* Actually make it work
* Refactor Dockerfile and scripts to make sense, rather than just being appended to. Appending to it is fine work WIP, so you don't have to redo all the previous dockerfile steps, but is very messy in the long run.
* Make travis actually do rudimentary tests on the container it builds.
* Split scripts up into different steps for properly splitting up steps in Travis
* Add the processes to supervisord.conf, for making 'em start automatically

References:
https://wiki.myriadrf.org/Osmocom_GSM
https://osmocom.org/projects/cellular-infrastructure/wiki/SDR_OsmoTRX_network_from_scratch
https://github.com/samatt/SDR-101/blob/master/running_osmobts_with_usrp1_ubuntu_12.04.md

http://openbts.org/w/index.php?title=BuildInstallRun
https://osmocom.org/projects/osmotrx/wiki/OsmoTRX
https://osmocom.org/projects/osmonitb/wiki/OsmoNITB_LCR

http://osmocom.org/projects/pysim/wiki

On Docker
https://stackoverflow.com/questions/24225647/docker-any-way-to-give-access-to-host-usb-or-serial-device
https://docs.docker.com/engine/admin/using_supervisord/

