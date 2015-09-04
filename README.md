# crazyflie-release
Release repository for binaries.

This repository contains functionality for collecting build artifacts
from other repositories, and pacage them into a zip that can be used to flash
firmware in a Crazyfile.

# Building
To create a build artifact, call

        tools/build/build

This will download the files specified in the manifest and package them into
a zip file.