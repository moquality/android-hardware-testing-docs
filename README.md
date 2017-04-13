## Quick Setup

**Mobile phone setup**

* Ensure that the following settings are set on the phone:

* Settings &gt; Display &gt; Sleep after 30 minutes
* Settings &gt; Security &gt; Screenlock &gt; None

* Note down the "Device ID" after executing the following command 
* ```
  adb devices
  ```
* Execute the following command in the shell

* ```
  adb kill-server
  ```
* Download config.yml sent in the email.  Copy the "Device ID" in config.yml and save it.



**Docker setup**

* Install docker with the following command.

* ```
  sudo docker pull moquality/atest:0.331
  ```
* Run the following command to take you inside docker

```
docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
```

* Run the following command to obtain docker container id
* ```
  docker ps
  ```
* Copy the first four digits of container id and execute the following command where XXXX is the four digit container id

* ```
  docker cp config.yml xxxx:config.yml
  ```

Running the program

* execute the run.py

```
cd /app
python /app/run.py
```

## More Information

1. [Docker Setup](/docker-setup.md)
2. [Configuration Setup](/config-setup.md)
3. [Working with Testlink](/testlink.md)
4. [Writing your own test cases](/additional.md)



