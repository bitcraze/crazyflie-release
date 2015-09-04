# crazyflie-release [![Build Status](https://api.travis-ci.org/bitcraze/crazyflie-release.svg)](https://travis-ci.org/bitcraze/crazyflie-release)
Release repository for binaries.

This repository contains functionality for collecting build artifacts
from other repositories, and package them into a zip that can be used to flash
a Crazyfile with firmware.

# Building
To create a build artifact, call

        tools/build/build

This will download the files specified in the manifest and package them into
a zip file.