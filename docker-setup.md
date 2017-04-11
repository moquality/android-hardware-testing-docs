This page will show you how to setup the phone and run the docker image.

## Phone Setup

Ensure that the following settings are set on the phone:

* Settings &gt; Display &gt; Sleep after 30 minutes
* Settings &gt; Security &gt; Screenlock &gt; None

Ensure that adb \(Android API\) is enabled on the machine. If typing "adb devices" on the shell returns a device, it is authorized.

## Downloading the Docker

Docker is a container that automates the deployment of mobile testing application. The first step is to install the docker image, which is done with the following command:

```
sudo docker pull moquality/atest:0.331
```

The latest pre-release version of the software is v0.331.

## Running the Docker

Run the run.sh bash script with:

```
docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
```

With that you get inside the docker. Now to run the app testing framework, go to app directory and execute run.py

```
cd /app
python /app/run.py
```

### Configuration

All tests can be configured through the [config.yml file](/configuration-setup.md). Structure of the config file is:

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

The fields in "&lt;..&gt;" need to entered by a user.  "&lt;api-server&gt;" and "&lt;api-key&gt;" are the link to the testlink server and the key associated. The key can be obtained from testlink. Other information such as user, project, plan and build can be obtained from testlink. A sample config.yml file is given below:



```
device_1: 063ebefaf0ddfb78

moq:
  api_server: "http://127.0.0.1:5000"
  api_key: "k347582vdg0rt7alo1586r2acak7kewu"
  options:
    use_cv: true


testlink:
  url: "http://tl.moquality.com"
  key: "6d698f088a786126016440887694ef8e"
  user: "bot1"
  project: "Video Playback Testing"
  plan: "Videoplan"
  build: "NexusM"
  test: "archermind.video.yml"


testcases:
  archermind.test.yml:
    filename: "patterns_base.mp4"
```

config.yml file is present in the /app folder. You can find the current docker’s container-id with "docker ps".  Config.yml can be edited with the following command 

```
docker cp config.yml <container-id> /app/config.yml
```



