# Docker CI/CD Images

![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/rcmedeiros/cicd.svg)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/rcmedeiros/cicd.svg?style=popout-square)

A Dockerfile repository for images to be used in CI/CD workflows. Reference **rcmedeiros/cicd:tag**. Current images are:

|     SO     |                                  Includes                                   | Tag             |
|:----------:|:---------------------------------------------------------------------------:|:----------------|
| CentOS 7.6 |                               Node 10 latest                                | centos7-node10  |
| CentOS 7.6 |                                OpenJDK 1.8.0                                | centos7-java8   |
| CentOS 7.6 |                                Python 3.7.3                                 | centos7-python3 |
| CentOS 7.6 | <ul><li>Node 10 Latest</li><li>OpenJDK 1.8.0</li><li>Python 3.7.3</li></ul> | centos7         |

All images comes with latest Git, AWS Cli, OpenSSH, Tar and GZip