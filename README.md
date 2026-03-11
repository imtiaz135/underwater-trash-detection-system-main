# underwater-trash-detection-system-main
🌊 Underwater Trash Detection System
A beautiful web application for detecting underwater trash using your trained YOLO model. This system provides both video upload processing and live webcam detection capabilities with an immersive ocean-themed user interface. To test the website visit : https://underwater-trash-detection-system-zu5kchkzrfkok5pew2wnza.streamlit.app/

Features
🌊 Ocean-themed UI: Beautiful underwater design with animated bubbles and ocean gradients
📹 Video Upload: Upload and process underwater videos frame by frame
📷 Live Webcam Detection: Real-time trash detection using your device's camera
⚙️ Adjustable Parameters: Customize frame skip interval, confidence threshold, and max detections
🔍 Frame-by-Frame Analysis: Detailed results showing each processed frame with detected trash
📊 Grid Display: Results displayed in an organized grid layout
🎯 Bounding Box Visualization: Color-coded bounding boxes around detected trash items with specific class names
🎬 Video Recreation: Recreate the processed video with detection overlays for download
📱 Responsive Design: Works on desktop, tablet, and mobile devices
Prerequisites
Python 3.8 or higher
Your trained YOLO model file (best.pt)
Web browser with camera access (for live detection)
Supported Trash Types
The system can detect and classify the following 15 types of underwater trash:

😷 Mask - Face masks and protective gear
🥫 Can - Metal beverage cans and containers
📱 Cellphone - Mobile phones and electronic devices
🔌 Electronics - Electronic components and devices
🍾 Glass Bottle - Glass containers and bottles
🧤 Glove - Rubber gloves and protective gear
🔧 Metal - Metal objects and debris
📦 Misc - Miscellaneous items
🕸️ Net - Fishing nets and gear
🛍️ Plastic Bag - Plastic shopping bags and packaging
🥤 Plastic Bottle - Plastic beverage containers
🧴 Plastic - Other plastic materials
🪢 Rod - Metal rods and pipes
😎 Sunglasses - Eyewear and accessories
🚗 Tyre - Vehicle tires and rubber materials
Installation
Option 1: Flask Web Application
Clone or download this project to your local machine

Install Python dependencies:

pip install -r requirements.txt
Ensure your model file is in place:

Make sure best.pt is in the root directory of the project
Option 2: Streamlit Application (Recommended)
Clone or download this project to your local machine

Install Streamlit dependencies:

pip install -r requirements_streamlit.txt
Ensure your model file is in place:

Make sure best.pt is in the root directory of the project
Usage
Flask Web Application
Start the application:

python app.py
Open your web browser and navigate to:

http://localhost:5000
Streamlit Application (Recommended)
Start the Streamlit application:

python run_streamlit.py
Or directly:

streamlit run streamlit_app.py
Open your web browser and navigate to:

http://localhost:8501
Choose your detection method:

Video Upload
Click "Choose Video File" or drag and drop a video file
Supported formats: MP4, AVI, MOV, MKV
Adjust processing parameters:
Frame Skip Interval: Process every Nth frame (1 = all frames, 5 = every 5th frame)
Confidence Threshold: Minimum confidence for detection (0.1 = 10%, 0.9 = 90%)
Max Detections: Maximum number of detections to show per frame
Click "Process Video" to analyze the video
View results in the grid below
Click "Recreate Video with Detections" to download the processed video with detection overlays
Live Webcam Detection
Click "Start Webcam" to begin live detection
Allow camera access when prompted
Adjust confidence threshold and max detections for real-time processing
Real-time detection results will appear on the video feed
Click "Stop Webcam" to end the session
How It Works
Video Processing
Upload a video file through the web interface
The system processes every 5th frame to optimize performance
Your YOLO model detects trash in each frame
Bounding boxes are drawn around detected objects
Results are displayed in a grid format with frame numbers and detection counts
Use the "Recreate Video" feature to download the processed video with detection overlays
Live Detection
Start the webcam through the browser
Frames are captured and sent to the server every second
Your model processes each frame in real-time
Detection results are overlaid on the video feed
Green bounding boxes show detected trash with confidence scores
File Structure
under_trash/
├── app.py                 # Main Flask application
├── best.pt               # Your trained YOLO model
├── trash_classes.py      # Trash class definitions and colors
├── requirements.txt      # Python dependencies
├── README.md            # This file
├── templates/
│   └── index.html       # Main web interface
└── uploads/             # Temporary upload directory (created automatically)
Technical Details
Backend: Flask web server with OpenCV and YOLO integration
Frontend: HTML5, CSS3, JavaScript with modern web APIs
Model: Uses Ultralytics YOLO for object detection
Video Processing: OpenCV for frame extraction and processing
Real-time: WebRTC for webcam access and real-time processing
Customization
Model Configuration
The system automatically loads your best.pt model file
Detection confidence thresholds can be adjusted in app.py
Frame processing frequency can be modified (currently every 5th frame)
Trash Class Configuration
Trash classes and their colors can be customized in trash_classes.py
The system supports 15 different trash types as trained in your model
Each trash type has its own color for easy identification
UI Customization
Ocean theme colors can be modified in the CSS section of templates/index.html
Animation speeds and effects can be adjusted
Grid layout and card styling can be customized
Troubleshooting
Common Issues
Model not loading:

Ensure best.pt is in the correct location
Check that the file is not corrupted
Webcam not working:

Ensure your browser supports WebRTC
Check camera permissions in your browser
Try using HTTPS (required for webcam in some browsers)
Video upload fails:

Check file format (MP4, AVI, MOV supported)
Ensure file size is reasonable
Check server logs for specific error messages
Performance issues:

Reduce video resolution for faster processing
Increase frame skip interval in app.py
Use a more powerful machine for large videos
Error Messages
"No video file provided": Ensure you've selected a video file
"Model loading error": Check that best.pt exists and is valid
"Webcam access denied": Grant camera permissions in your browser
Performance Tips
For large videos, consider processing in smaller segments
Adjust the frame processing interval based on your needs
Use GPU acceleration if available (requires CUDA setup)
Optimize video resolution before upload for faster processing
Contributing
Feel free to enhance this system with additional features:

Export detection results to CSV/JSON
Video download with detection overlays
Multiple model support
Advanced filtering options
Database integration for result storage
License
This project is open source. Feel free to modify and distribute as needed.

Happy detecting! 🌊♻️
