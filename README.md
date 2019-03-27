# Debian-based Node.js images for [Shippable](https://shippable.com/)
**NOTE:** *This is a fork of [Lloyd Cotten's docker-node-shippable repo](https://github.com/lloydcotten/docker-node-shippable).*

In this repo you will find Node.js images pre-configured with the dependencies necessary to be used as CI containers on [Shippable](https://shippable.com/).

## Docker Hub
The public docker hub repository is here: https://hub.docker.com/r/woodmetocean/node_shippable/

## Tags
The images are tagged with version info using the following format: X-Y-Z, where:

* X - the Debian release name (stretch, jessie, wheezy, etc) of the base images
* Y - the Node.js version used
* Z - the general semantic version of the image build

## Usage
These images are intended to be used directly with Shippable.  You can specify the docker image in your project settings or in your shippable.yml file:

```yaml
language: node_js

node_js:
  - "10"
  - "10.15"

build_image: woodmetocean/node_shippable:stretch-v10-1.0.0

before_install:
  - . ~/.nvm/nvm.sh && nvm install $SHIPPABLE_NODE_VERSION
  - node --version
  - npm install

install:
  - npm update

script: npm test
```

## Images

* Node.js v10 (latest): `docker pull woodmetocean/node_shippable:stretch-v10-1.0.0`
* Node.js v10: `docker pull woodmetocean/node_shippable:v10`
* Node.js v8: `docker pull woodmetocean/node_shippable:v8`
