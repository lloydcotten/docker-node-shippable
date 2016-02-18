# Debian-based Node.js images for [Shippable](https://shippable.com/)
In this repo you will find Node.js images pre-configured with the dependencies necessary to be used as CI containers on [Shippable](https://shippable.com/).

## Docker Hub
The public docker hub repository is here: https://hub.docker.com/r/lloydcotten/node_shippable/

## Tags
The images are tagged with version info using the following format: X-Y-Z, where:

* X - the Debian release name (jessie, wheezy, etc) of the base images
* Y - the Node.js version used
* Z - the general semantic version of the image build

## Usage
These images are intended to be used directly with Shippable.  You can specify the docker image in your project settings or in your shippable.yml file:

```yaml
language: node_js

node_js:
  - "4"
  - "4.2"

build_image: lloydcotten/node_shippable:jessie-v4-1.0.2

before_install:
  - . ~/.nvm/nvm.sh && nvm install $SHIPPABLE_NODE_VERSION
  - node --version
  - npm install

install:
  - npm update

script: npm test
```

## Images

* Node.js v4 (latest): `docker pull lloydcotten/node_shippable:jessie-v4-1.0.2`
* Node.js v0.10.32: `docker pull lloydcotten/node_shippable:jessie-v0.10.32-1.0.2`
