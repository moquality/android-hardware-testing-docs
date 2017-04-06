# Additional Documentation

### Writing your own test cases
Test cases are specified using a YAML file. An example YAML configuration that comes with the docker image is in ```archermind.test.yml```.

```
device: Android
steps:
    - home: None
    - push:
        file: data/{{filename}}
        dest: /sdcard/{{filename}}
    - play_video:
        file: /sdcard/{{filename}}
    - sleep: 2
    - screencheck:
        count: 5
        structural_similarity: 0.8
    - kill: None
```

The following test comprises of steps specified by the ```steps``` parameter.
- ```home```: Make the device go to the home screen
- ```push```: Pushes a ```file``` to ```dest```on the phone
- ```play_video```: Plays a video specified by ```file```
- ```sleep```: Sleep for some time to let the device play the video
- ```screencheck```: Use computer vision to check if the video is playing or not. Check at least as many time as specified by ```count```. Check using the  ```structural_similarity``` measure.  
- ```kill```: Kill the video player

The test's main part is the screencheck module. Our test module knows how a video should play. It takes a screencapture of the phone and tests for similarity with the original known image which was used to generate the video.

In the future, we will support arbitrary generation of video that can be used with the screencheck function.

Also see ```archermind.video.yml``` for another test. This test is analogous to ArcherMind's video test suite.