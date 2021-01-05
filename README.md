# crazyflie-release [![CI](https://github.com/bitcraze/crazyflie-release/workflows/CI/badge.svg)](https://github.com/bitcraze/crazyflie-release/actions?query=workflow%3ACI)
Release repository for binaries.

This repository contains functionality for collecting build artifacts
from other repositories, and package them into a zip that can be used to flash
a Crazyfile with firmware.

# Building
To create a build artifact, call

        tools/build/build platform

This will download the files specified in the manifest and package them into
a zip file.
