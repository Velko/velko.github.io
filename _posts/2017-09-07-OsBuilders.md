---
layout: post
title:  "OsBuilders Docker images"
date:   2017-09-07 10:28:51 +0200
categories: docker gcc crosscompiler
---

Since building GCC cross-compiler for OsDev work takes a while, here's the idea: let's build a Docker image(s) containing pre-built
compilers and use those to build kernels.

Image consists of minimal Debian image (debian:buster-slim) with added cross-compiler for target architecture. The main purpose of
provided images is to eliminate the long cross-compiler build process. One has to create a Docker image, using provided image as a
base and add neccessary tools (GNU Make, CMake, etc.) and services (SSH, rsync) to produce an actual builder.
