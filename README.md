# README #

At the minute, the only way to install the ```cardano-node``` and the ```cardano-cli``` software components necessary to run a stake pool on Shelley is to compile them. Compilation can be troublesome and lead to issues. To avoid any complications and always get solid results and the right binaries, I provide a Docker build environment to build against the latest version/tag as in [the official documentation to build a node](https://github.com/input-output-hk/cardano-tutorials/blob/master/node-setup/build.md).

**IMPORTANT: you must run these steps to compile ```cardano-node``` and ```cardano-cli``` on your local computer, and copy them over to your servers. This is to avoid useless load and installing compilation software on your servers.**

## install docker ##

Install and run Docker Desktop for your OS from [the official site](https://www.docker.com/products/docker-desktop).

## clone the build repo ##

```bash
git clone https://github.com/gacallea/cardanoNodeBuilder.git
```

## compile the software ##

```bash
cd cardanoNodeBuilder
docker-compose up --build -d
```

## copy the binaries to your host ##

```bash
docker container cp build_bins_1:/usr/local/bin cardano-bins/
```

## scp the binaries to your nodes ##

**NOTE: Make sure you point to your actual servers.**

```bash
scp cardano-bins/bin/cardano-node node-server:/usr/local/bin/
scp cardano-bins/bin/cardano-cli node-server:/usr/local/bin/
```

```bash
scp cardano-bins/bin/cardano-node relay-server:/usr/local/bin/
scp cardano-bins/bin/cardano-cli relay-server:/usr/local/bin/
```
