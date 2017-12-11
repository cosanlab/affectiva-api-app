# affectiva-api-app
This repo demonstrates ways to use the Affectiva API 

# Files

affectiva_emotion_detector.html 
This webpage will extract emotions and expression predictions using the Affectiva JavaScript API. 

Required files: 
	css
	FileSaver.min.js
	jquery-3.1.0.slim.js

# How to use
The page needs to be run on a server to process videos. 
1. Open a server to host the webpage on. 
For example, launch `jupyter notebook` from the repository directory. 

2. In a browser (e.g., Chrome) open `affectiva_emotion_detector.html` on the server. 
For example, navigate to: 
```
http://localhost:8889/files/affectiva_emotion_detector.html
```
3. The html page will give you feedback in the html page and in the javascript console (for Chrome, access via command+option+j).

4. At the end of the video, the results saved as a json file will be automatically downloaded. 

