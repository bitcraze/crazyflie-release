# crazyflie-release [![CI](https://github.com/bitcraze/crazyflie-release/workflows/CI/badge.svg)](https://github.com/bitcraze/crazyflie-release/actions?query=workflow%3ACI)
Release repository for binaries.

This repository contains functionality for collecting build artifacts
from other repositories, and package them into a zip that can be used to flash
a Crazyfile with firmware. This is also where you find the official release zips
for download.

# Install a release

There are two flavours of the firmware: **cf2** and **tag**. The **cf2** is to be
used wit any of the Crazyflie 2.X drones while the **tag** is used with the
Roadrunner.

The easiest way to flash the zip to a device is to use the python client, please
see [the getting started guide](https://www.bitcraze.io/documentation/tutorials/getting-started-with-crazyflie-2-x/#update-fw).

# Building
To create a build artifact, call

        tools/build/build platform

This will download the files specified in the manifest and package them into
a zip file.
