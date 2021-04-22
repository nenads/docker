# 📦 BigBlueButton 2.3 Docker

Version: 2.3-beta-5 | [Changelog](CHANGELOG.md) | [Issues](https://github.com/bigbluebutton/docker/issues)

## Note
Even though it seems to be stable so far, it is still a beta, which means that you can expect broken bits and pieces in some places.

## Features
- Easy installation
- Greenlight included
- Fully automated HTTPS certificates
- Full IPv6 support
- Runs on any major linux distributon (Debian, Ubuntu, CentOS,...)

## What is not implemented yet
- bbb-lti

## Install
1. Install docker-ce & docker-compose
    1. follow instructions
        * Debian: https://docs.docker.com/engine/install/debian/
        * CentOS: https://docs.docker.com/engine/install/centos/
        * Fedora: https://docs.docker.com/engine/install/fedora/
        * Ubuntu: https://docs.docker.com/engine/install/ubuntu/
    2. Ensure docker works with `$ docker run hello-world`
    3. Install docker-compose: https://docs.docker.com/compose/install/
    4. Ensure docker-compose works and that you use a version ≥ 1.28 : `$ docker-compose --version`
2. Clone this repository
   ```sh
   $ git clone --recurse-submodules https://github.com/bigbluebutton/docker.git bbb-docker
   $ cd bbb-docker
   ```
3. Run setup:
   ```bash
   $ ./scripts/setup
   ```
4. (optional) Make additional configuration adjustments
   ```bash
   $ nano .env
   # always recreate the docker-compose.yml file after making any changes
   $ ./scripts/generate-compose
   ```
5. Start containers:
    ```bash
    $ docker-compose up -d
    ```
6. If you use greenlight, you can create an admin account with:
    ```bash
    $ docker-compose exec greenlight bundle exec rake admin:create
    ```

## Further How-To's
- [Upgrading](docs/upgrading.md)
- [Running behind NAT](docs/behind-nat.md)
- [BBB-Docker Development](docs/development.md)
- [Integration into an existing web server](docs/existing-web-server.md)

