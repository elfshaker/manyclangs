# Running manyclangs via emulation on x86-64

<!-- TODO(veselink1): Needs improvement -->

## Building the docker image

Clone this repository, and run the following commands to build a docker image.
```bash
docker build -t manyclangs-qemu-aarch64 .
```

## Using manyclangs-run
Once you have the docker image available on your system, all you have to do is to run `manyclangs-run` with the `USE_DOCKER_QEMU=aarch64` environment variable.

```bash
USE_DOCKER_QEMU=aarch64 manyclangs-run /path/to/manyclangs HEAD clang --version
```
