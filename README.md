# affectiva-api-app
This repo demonstrates ways to use the Affectiva API 

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

# How to use
The page needs to be run on a server to process videos. 
1. Open the `affectiva_emotion_detector.html` in your favorite text editor (e.g. Sublime) and replace the filename at `var filename = 'video_file.MP4';` with your own filename that is in the same directory. 

2. Open a server to host the webpage on. 
For example, launch `jupyter notebook` from the repository directory. 

3. In a browser (e.g., Chrome) open `affectiva_emotion_detector.html` on the server. 
For example, navigate to: 
```
http://localhost:8889/files/affectiva_emotion_detector.html
```
4. The html page will give you feedback in the html page and in the javascript console (for Chrome, access via command+option+j).

5. At the end of the video, the results saved as a json file will be automatically downloaded. 

