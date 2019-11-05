# Prebuilt Tensorflow Runtime Docker image for non-AVX machine

## Description
Prebuild Tensorflow Runtime downloaded from Tensorflow Docker repository doesn't support CPU which don't have 
AVX, so people who have Intel CPU which is manufactured before 2011 (with consumer product, it's older than Sandy Bridge, with server/datacenter, it's older than Westmere, although some CPUs in Westmere family manufactured in early 2011 have AVX support) or AMD CPU which is older than Bulldozer family may have to recompile the runtime from the source. Please check your CPU information in the manufacturer website.

This is a prebuild runtime built on Intel® Xeon(R) CPU E5645 and NVIDIA Titan XP. Note that this build is for GPU
and dedicated to those CPU and GPU. Please look at [my github](https://github.com/aperture147/tensorflow-non-avx-docker) for build template. 

## How to build
* Clone this repository to a directory and move to that.
* Run:
```
docker build . -t <your-image-name> --build-arg comp-cap=<your-gpu-compute-capabilites>
```
* Wait for the building process

## Tags
`bionic-slim`: Ubuntu 18.04 GPU build without AWS, GPU, HDFS, Apache Ignite, Kafka and NCCL support

more build template will be made
