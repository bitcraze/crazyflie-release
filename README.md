# crazyflie-release [![CI](https://github.com/bitcraze/crazyflie-release/workflows/CI/badge.svg)](https://github.com/bitcraze/crazyflie-release/actions?query=workflow%3ACI)
Release repository for binaries.

This repository contains functionality for collecting build artifacts
from other repositories, and package them into a zip that can be used to flash
a Crazyfile with firmware. This is also where you find the official release zips
for download.

# Install a release

There are three flavours of the firmware: **cf2**, **tag** and **bolt**. The **cf2** is to be
used with any of the Crazyflie 2.X drones, the **tag** is used with the Roadrunner and the **bolt** with the Crazyflie Bolt.

The easiest way to flash the zip to a device is to use the python client, please
see [the getting started guide](https://www.bitcraze.io/documentation/tutorials/getting-started-with-crazyflie-2-x/#update-fw).

# Building
To create a build artifact, call

        tools/build/build platform

This will download the files specified in the manifest and package them into
a zip file.

# Release instructions

Please check out the [firmware release instructions](/docs/release.md) for a checklist of how to use github actions to do a firmware release.
