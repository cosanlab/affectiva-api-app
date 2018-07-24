# affectiva-api-app
This provides an easy way to extract emotion predictions using Affectiva's
[JavaScript SDK](https://affectiva.readme.io/docs/getting-started-with-the-emotion-sdk-for-javascript)

# Installation
Clone or download the directory
```
git clone https://github.com/cosanlab/affectiva-api-app.git
```

# Directions for processing images using affectiva_emotion_detector_photo.html
1. Double click the `affectiva_emotion_detector_photo.html` in Finder or File Browser
which should launch a web browser such as Chrome or Firefox.

2. Wait until you see the `dectector reports initialized` in the logs,
and you will see a `Choose Files` button appear.

3. Choose a file or files with the button. The images will be processed
as soon as you click Open.

4. Results of the detector will be combined into `output.json` file which will
be automatically downloaded once processing is complete.

5. You can edit the `affectiva_emotion_detector_photo.html` to change the
output file name, toggle verbosity of logs, or use different detectors (e.g., small or large face).


# Directions for processing video using affectiva_emotion_detector.html
1. Open the `affectiva_emotion_detector.html` in your favorite text editor (e.g. Atom, Sublime) and replace the filename at `var filename = 'data/sample_vid.mp4';` with the name of your
video filename. It's easies if you have the videos in the `affectiva-api-app` directory.

2. Modify parameters
`secs`: (default: 0) Beginning time of your video to start feature extraction.
`sec_step`: (default: .1) Increment of the video to extract features. The default of
.1 indicates it would process a frame every 100ms.
`stop_sec`: (default: undefined) If you want to process only a portion of your video
set stop_sec to the timestamp you wish to stop.
`verbose`: (default: true) When true, the frame being processed, timestamp, and success will be printed on page.

3. Start a webserver on your computer.
If using a MAC, open up your terminal. Navigate to the `affectiva-api-app` folder
then start a webserver using
```
python -m SimpleHTTPServer 8000
```

4. Now open your favorite browser (e.g. Chrome, FireFox) and type the following to the address bar
```
http://localhost:8000/
```

5. You should now see a list of the files in the `affectiva-api-app` directory.
Click on affectiva_emotion_detector.html and the processing will begin.

6. When processing is finished, the browser will automatically download the results file in json format.

7. Read in files
An easy way to read in the json files using the following code.
You need to add `lines=True` parameter or it will throw a trailing lines error.
```
import pandas as pd
df = pd.read_json('~/Downloads/data_sample_vid.json',lines=True)
```

# ToDo's
- Wrapper function / file grabber that can run the extraction for a list of video files.
- Frame-level extraction (currenly analyzes for each second).
- Asynchronous method? (currently recursive until finishes but async/parallel may speed up)
- Electron App?


# Files
affectiva_emotion_detector.html
This webpage will extract emotions and expression predictions using the Affectiva JavaScript API.

Required files:
	css  
	FileSaver.min.js  
	jquery-3.1.0.slim.js  
