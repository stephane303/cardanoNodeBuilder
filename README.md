# README #

docker build environment to build cardano-node latest version/tag as in [https://github.com/input-output-hk/cardano-tutorials/blob/master/node-setup/build.md](https://github.com/input-output-hk/cardano-tutorials/blob/master/node-setup/build.md

## steps ##

- clone this repo:

```bash
git clone https://github.com/gacallea/cardanoNodeBuilder.git
```

- to compile cardano-node and cardano-cli run:

```bash
docker-compose up --build -d
```

- to copy the cardano-node files to your host run:

```bash
docker container cp build_bins_1:/usr/local/bin cardano-bins/
```

- then scp the resulting binaries to your node and relays.

enjoy :)
