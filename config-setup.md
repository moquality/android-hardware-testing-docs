## Config.yml Setup

The configuration file is used to setup internal parameters as needed. config.yml resides in the /app.

### Parameters:
- Obtain the api_server and api_key from MoQuality.
- device_1: The device id of the device to be tested.
- moq: MoQuality related parameters.
- testlink: Testlink related parameters.

**moq Parameters
**
- api_server: Server to authenticate against
- api_key: Provided by MoQuality
- options: use_cv: Set to True if you want to use Computer Vision to test device. If false the test uses internal Android logs.

**testlink Parameters
**
- url: Url to testlink server
- user: Testlink user
- key: Key of the testlink user
- project: Project name
- plan: Plan name
- build: Build name
- test: MoQuality Testfile

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