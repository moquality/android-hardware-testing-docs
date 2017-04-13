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

* Start the docker server with the following command
* ```
  sudo dockerd
  ```

* Pull docker with the following command.

* ```
  sudo docker pull moquality/atest:0.331
  ```

  You will need to have a docker account to be able to pull this image. You can use username: `archermind` with password: `archertest`.

* Run the following command to start the docker image:
* ```
  sudo docker run -i -t --privileged -v /dev/bus/usb:/dev/bus/usb -v /home/archermind/.android:/root/.android moquality/atest:0.331
  ```
* Run the following command in host terminal to obtain docker container id

* ```
  sudo docker ps
  ```
* In the host terminal, copy the first four digits of container id and execute the following command where XXXX is the four digit container id

* ```
  sudo docker cp config.yml xxxx:app/config.yml
  ```

**Running the program**

Inside the docker terminal execute the following command to run the automated test suite.

```
cd /app
python run.py
```

The test suite should show you status messages for each test as they run.

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

## FAQ

** Testsuite fails to run or doesn't show status messages. **

The configuration file might be incorrectly specified. Follow [Configuration Setup](/config-setup.md).

** Testsuite fails because it cannot connect to an API server.**

Testsuite needs to be authenticated with the correct API key to run. Before running each test, the test suite authenticates with our server. Ping our API server to see if it is online with `ping 139.196.121.67`

If you can ping our server and the test suite fails, contact MoQuality.

** Cannot find the test results on Testlink. **

You are possibly seeing the results under the incorrect project name or build. Check to see if the project name and build are same as config.yml.

