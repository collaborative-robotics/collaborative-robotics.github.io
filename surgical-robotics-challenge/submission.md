---
layout: default
---

## Submission Instructions

Submissions to the challenge should use this [**form**](https://forms.gle/EECUaqJ2YReGbJte9).

The deadline for submission is June 6, 2022, 23:59 PST. However, we will accept updates after the deadline to correct minor issues
such as build problems (but only if there was an initial submission before the deadline).

Our goal is to make the submission process easy and flexible. We provided initial Docker containers
(see [System Setup](./system-setup.md)) and our expectation is that entries would submitted based on these containers.
There are, however, multiple ways to do this, as described below.

### Submitting a Dockerfile

A Dockerfile is a text file that describes how to build a Docker container. We provided initial Dockerfiles for
Ubuntu 18.04 + ROS Melodic and for Ubuntu 20.04 + ROS Noetic. You can submit an updated Dockerfile that installs
your dependencies and fetches your software. This approach should be easy if your dependencies are easily installed
(e.g., using `apt-get`) and your code only needs to be fetched from a GitHub repository (e.g., if it is Python and
does not need to be compiled).

In this case, you can provide a link (URL) to the Dockerfile in the submission form, or even upload it via the form.

### Submitting a Docker container/image

You can save your Docker image to a TGZ file using the `docker save` command (see [Docker docs](https://docs.docker.com/engine/reference/commandline/save/)):

```
docker save myimage:latest | gzip > myimage_latest.tar.gz
```

This will produce a rather large file, which should be uploaded somewhere, such as to [Docker Hub](https://hub.docker.com/).
You should then provide the URL in the submission form.

### Submitting a GitHub repository

If you are not comfortable with Docker, we will also accept a GitHub repository, assuming that it has a ReadMe that
documents how to install any dependencies and run your code.

In this case, please provide the URL of your GitHub repository in the submission form.
