This page will show you how to setup the phone and run the docker image.

## Phone Setup

Ensure that the following settings are set on the phone:

* Settings &gt; Display &gt; Sleep after 30 minutes
* Settings &gt; Security &gt; Screenlock &gt; None

Ensure that adb \(Android API\) is enabled on the machine. If typing "adb devices" on the shell returns a device, it is authorized.

## Installing Docker

Installed Docker CE. Find instructions for installing Docker CE on Ubuntu [here](https://www.docker.com/docker-ubuntu).

## Downloading the Docker

Docker is a container that automates the deployment of mobile testing application. The first step is to install the docker image, which is done with the following command:

```
sudo docker pull moquality/atest:0.331

```

You will need to have a docker account to be able to pull this image. Use the following username/password:

```
username: archermind
password: archertest
```

The latest pre-release version of the software is v0.331.

If the docker download is slow, use the [mirror offered by daocloud.io](http://stackoverflow.com/questions/28957330/acclerate-docker-pull-in-china-asia) to configure your docker. Depending on the version of your docker, you can start docker with a mirror using the following:

```
docker --registry-mirror=http://c13176d8.m.daocloud.io daemon
```
Here ```c13176d8``` is the id of the account MoQuality made.

## Running the Docker

Run the run.sh bash script with:

```
docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
```

With that you get inside the docker. Now to run the app testing framework, go to app directory and execute run.py

```
cd /app
python run.py
```

### 



