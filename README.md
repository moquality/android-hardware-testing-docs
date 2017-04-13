## Quick Setup

* Ensure that the phone sleep mode is on.
* adb is enabled on the machine. If typing "adb devices" on the shell returns a device, it is authorized.
* Install docker with the following command.

  `sudo docker pull moquality/atest:0.331`

* Run the following command to take you inside docker

```
docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
```

* Once inside the docker, execute the run.py

```
cd /app
python /app/run.py
```

## More Information

1. [Docker Setup](/docker-setup.md)
2. [Configuration Setup](/config-setup.md)
3. [Working with Testlink](/testlink.md)
4. [Writing your own test cases](/additional.md)



