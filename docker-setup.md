This page will show you how to setup the phone and run the docker image.

## Phone Setup

Ensure that the following settings are set on the phone:

- Settings > Display > Sleep after 30 minutes
- Settings > Security > Screenlock > None


## Downloading the Docker
 
Pull the image from dockerhub. To do so you will need a Dockerhub ID. Find documentation [here](https://docs.docker.com/docker-hub/accounts/). Then pull the docker image using:

```
sudo docker pull moquality/atest:0.331
```
The latest pre-release version of the software is v0.331.

## Running the Docker

Ensure that the host machine is authorized to use adb. If ```adb devices``` returns a device, it is authorized

Run the run.sh bash script inside the docker with:
```
docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
```

Inside the docker,

```
cd /app
python /app/run.py
```

### Configuration

All tests can be configured through the [config.yml file](/configuration-setup.md). An example config file is:
```
device_1: <device-id>

moq:
  api_server: "<api-server>"
  api_key: "<api-key>"
  options:
    use_cv: true

testlink:
  url: "<testlink-url>"
  key: "<testlink-key>"
  user: "bot1"
  project: "<project-name>"
  plan: "<project-plan-name>"
  build: "<build-name>"
  test: "<test.file.yml>"

```
It should be saved in the /app folder.

If you want to edit the config.yml, edit it on the host machine and put it on the docker using:
```
docker cp config.yml <container-id> /app/config.yml
```
You can find the current docker’s container-id with docker ps.

