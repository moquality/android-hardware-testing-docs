## Quick Start

**Docker start**

Open a new shell. Let's call it **shell 0. **Execute the following command in **shell 0**

```
sudo dockerd
```

**Mobile phone setup**

* Ensure that the following settings are set on the phone:

* Settings &gt; Display &gt; Sleep after 30 minutes

* Settings &gt; Security &gt; Screenlock &gt; None

* Open a shell. Let's call it **Shell 1**.

* Note down the "Device ID" after executing the following command in **Shell 1**. If authorization is necessary on the phone, do authorize the computer to access the phone.

* ```
  adb devices
  ```
* Execute the following command in the **shell 1**

* ```
  adb kill-server
  ```
* Download config.yml sent in the email.  Copy the "Device ID" in config.yml and save it.

**Docker setup**



* Open a new shell. Let's call it **shell 2**

* Pull docker with the following command in **shell 2**.

* ```
  sudo docker pull moquality/atest:0.331
  ```
* Run the following command in **shell 2** to take you inside docker. Now **shell 2** has a docker running
* ```
  sudo docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
  ```
* Run the following command in **shell 1** to obtain docker container id

* ```
  sudo docker ps
  ```
* Copy the first four digits of container id and execute the following command in **shell 1** where XXXX is the four digit container id

* ```
  sudo docker cp config.yml xxxx:app/config.yml
  ```

**Running the program**

* execute the run.py in **shell 2**

```
cd /app
python run.py
```

**Viewing results on Testlink**

A current version of Testlink is hosted at [http://139.196.121.67/testlink/login.php](http://139.196.121.67/testlink/login.php)

```
username: admin
password: archertest
```

You can see a matrix of current status of all test cases at:

* Test Report &gt; Test Reports and Metrics  &gt;Test Result Matrix 

More Information

1. [Docker Setup](/docker-setup.md)
2. [Configuration Setup](/config-setup.md)
3. [Working with Testlink](/testlink.md)
4. [Writing your own test cases](/additional.md)



