## Config.yml Setup

The configuration file is used to setup internal parameters as needed. config.yml resides in the /app.

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

```

config.yml file is present in the /app folder. You can find the current docker’s container-id with "docker ps".  Config.yml can be edited with the following command

```
docker cp config.yml <container-id> /app/config.yml
```

### Parameters:

* Obtain the api\_server and api\_key from MoQuality (see our email).
* device\_1: The device id of the device to be tested.
* moq: MoQuality related parameters.
* testlink: Testlink related parameters.

**moq Parameters**

* api\_server: Server to authenticate against
* api\_key: Provided by MoQuality
* options: use\_cv: Set to True if you want to use Computer Vision to test device. If false the test uses internal Android logs.

**testlink Parameters**

* url: Url to testlink server
* user: Testlink user
* key: Key of the testlink user
* project: Project name
* plan: Plan name
* build: Build name
* test: MoQuality Testfile

## Standalone Tests

If you want to run a standalone test, it can be set in config.yml file as:

```
device_1: <device-id>

moq:
  api_server: "<api-server>"
  api_key: "<api-key>"
  options:
    use_cv: true

testcases:
  <test.file.yml>:
    option_1: arg_1
    option_2: arg_2
```



