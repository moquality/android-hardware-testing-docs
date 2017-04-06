## Config.yml Setup

The configuration file is used to setup internal parameters as needed. config.yml resides in the /app.

### Parameters:
- Obtain the api_server and api_key from MoQuality.
- device_1: The device id of the device to be tested.
- moq: MoQuality related parameters.
- testlink: Testlink related parameters.

**moq Parameters

- api_server: Server to authenticate against
- api_key: Provided by MoQuality
- options: use_cv: Set to True if you want to use Computer Vision to test device. If false the test uses internal Android logs.

**testlink Parameters
- 
**- Next few fields are “testlink_url”,  “testlink_key”, “testlink_tester” (default is bot 1). These details are filled beforehand and need not to be changed.
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