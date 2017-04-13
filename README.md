## Quickstart

**Mobile phone setup**

* Ensure that the following settings are set on the phone:

  * Settings &gt; Display &gt; Sleep after 30 minutes
  
  * Settings &gt; Security &gt; Screenlock &gt; None

* Note down the "Device ID" after executing the following command. If authorization is necessary on the phone, do authorize the computer to access the phone.

* ```
  adb devices
  ```
* You have to kill the ADB server on the host machine. Execute the following command in the shell.

* ```
  adb kill-server
  ```
    
* Download config.yml sent in the email sent to you.  Copy the "Device ID" in config.yml and save it.

**Docker setup**

* Pull docker with the following command.

* ```
  sudo docker pull moquality/atest:0.331
  ```
* Run the following command to take you inside docker
* ```
  docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
  ```
* Run the following command to obtain docker container id

* ```
  docker ps
  ```
* Copy the first four digits of container id and execute the following command where XXXX is the four digit container id

* ```
  docker cp config.yml xxxx:app/config.yml
  ```

**Running the program**

Run the automated test suite.

```
cd /app
python run.py
```

**Viewing results on Testlink**

All the results are uploaded to Testlink hosted at [http://139.196.121.67/testlink/login.php](http://139.196.121.67/testlink/login.php).

```
username: admin
password: archertest
```

You can see a matrix of current status of all test cases at:

* Test Report &gt; Test Reports and Metrics  &gt;Test Result Matrix 

## More Information

1. [Docker Setup](/docker-setup.md)
2. [Configuration Setup](/config-setup.md)
3. [Working with Testlink](/testlink.md)
4. [Writing your own test cases](/additional.md)



