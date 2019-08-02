MCloud master instance
==================

MCloud is dockerized QA infrastructure for remote web access to physical devices (Android and iOS). Is is fully integrated into the [qps-infra](http://www.qps-infra.io) ecosystem and can be used for manual so automation usage.

* It is built on the top of [OpenSTF](https://github.com/openstf) with supporting iOS devices remote control.

## Contents
* [Software prerequisites](#software-prerequisites)
* [Initial setup](#initial-setup)
* [Services start/stop/restart](#services-restart)
* [License](#license)


## Software prerequisites
* Change current user uid/guid to uid=1000 and gid=1000 - (https://github.com/jenkinsci/docker)
  Note: for current user just change uid/guid inside /etc/passwd and reboot host
* Install [docker](http://www.techrepublic.com/article/how-to-install-docker-on-ubuntu-16-04/)
* Installed [docker-composer](https://docs.docker.com/compose/install/#install-compose)


## Initial setup
* Execute ./setup.sh shell script providing public and private addresses of the iSTF farm
```
./setup.sh demo.qaprosoft.com 192.168.88.10
```
<B>Note</B>: public ip and 80 http port should be accessible from user's browsers. Private ip should be used for internal services communication. Also to be able to connect to devices remotely range of ports should be opened (7400-7700).
* Setup Android provider using steps from android-slave branch (TODO: publish steps and ansible scripts with details)
* Setup iOS provider using steps from ios-slave (not officially released yet)


## Services start/stop/restart
* Use ./stop.sh script to stop everything
* User ./start.sh to start all containers

## License
Code - [Apache Software License v2.0](http://www.apache.org/licenses/LICENSE-2.0)

Documentation and Site - [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/deed.en_US)