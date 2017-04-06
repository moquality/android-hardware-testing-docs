## Config.yml Setup

The configuration file is used to setup internal parameters as needed. config.yml resides in the /app.

### Parameters:
- Obtain the api_server and api_key from MoQuality.
- First field is device_1. This field represent the device id and is unique to every phone. A user must enter the valid device id. The device id is obtained using the command  “adb devices” inside the docker machine.
- Next few fields are “testlink_url”,  “testlink_key”, “testlink_tester” (default is bot 1). These details are filled beforehand and need not to be changed.
- Next field is “project_name”. Default name is “Video Playback Testing”. It can be changed, but a project with the same name must be created in the Testlink.
- Next field is “Testplan_name”. Default name is “Videoplan”.
- Next field is “Build name”. Administrator must create a build on the Testlink (instructions given below) and enter the name of the build here. The test results will be updated for a build.


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