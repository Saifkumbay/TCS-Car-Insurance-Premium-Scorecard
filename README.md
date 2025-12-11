🚗 Traffic Speed Estimation & Insurance Premium Scorecard System
📋 Project Overview
This is a comprehensive traffic analysis system that processes traffic videos to:

Detect vehicles in real-time using YOLOv8

Track vehicles across frames using ByteTrack

Estimate speeds using perspective transformation

Detect violations (speeding >100 km/h)

Generate AI-powered insurance premium scorecards based on driving behavior

Provide multi-channel outputs: SMS alerts, Email reports, Interactive dashboard

🚀 Quick Start Guide
1. Prerequisites Installation
bash
# Install all required dependencies
pip install ultralytics supervision opencv-python numpy twilio pymongo streamlit plotly pandas requests
2. Running the System
Basic Usage (Speed Estimation Only):
bash
# Run the ultralytics_example.py script
python ultralytics_example.py --source_video_path your_video.mp4
Full System with All Features:
bash
# Run the complete traffic analyzer
python ultralytics_example.py --source_video_path your_video.mp4 --send_email --auto_gui --mongodb --generate_scorecard
🎯 Key Features
1. Real-time Vehicle Detection & Tracking
Uses YOLOv8 for accurate vehicle detection

ByteTrack algorithm for consistent vehicle tracking

Real-time speed calculation using perspective transformation

2. Speed Estimation & Violation Detection
Calculates vehicle speeds in km/h

Detects speeding violations (>100 km/h)

Sends SMS alerts via Twilio for violations

3. Multi-format Reporting
Node.js style TXT reports with detailed statistics

HTML interactive reports for web viewing

Premium management scorecards for executives

JSON data exports for further analysis

4. Cloud Integration
MongoDB Atlas for data storage

Real-time analytics saving during processing

Historical data tracking and analysis

5. Interactive Dashboard
Auto-launching Streamlit web application

Real-time data visualization

Interactive charts and metrics

Email reports directly from dashboard

6. AI-Powered Insights
Groq API integration for intelligent scorecard generation

Risk assessment and premium calculation suggestions

Management recommendations based on traffic patterns

📁 Project Structure
text
TCS-Car-Insurance-Premium-Scorecard/
│
├── ultralytics_example.py           # MAIN SCRIPT - Run this file
│
├── auto_dashboard.py                # Auto-generated dashboard (created during runtime)
├── ultimate_traffic_data.json       # Generated analysis data
├── ultimate_scorecard.txt           # AI-generated scorecard
│
├── requirements.txt                 # Python dependencies
└── README.md                        # This file
⚙️ Command Line Arguments
bash
# Basic video processing
python ultralytics_example.py --source_video_path traffic.mp4

# Advanced options:
python ultralytics_example.py \
  --source_video_path traffic.mp4 \
  --confidence_threshold 0.3 \        # Detection confidence (0.1-1.0)
  --iou_threshold 0.7 \               # Overlap threshold for NMS
  --generate_scorecard \              # Enable AI scorecard generation
  --auto_gui \                        # Auto-launch dashboard
  --mongodb \                         # Save to MongoDB Atlas
  --send_email                        # Send comprehensive email report
🔧 Configuration Setup
1. Video Setup
Place your traffic video in the project folder

Update SOURCE polygon coordinates in the script for accurate speed calculation

Default speed limit: 100 km/h (modifiable in code)

2. API Keys (Optional for basic speed estimation)
The system uses several APIs that require configuration:

python
# In the code, you'll need to configure:
TWILIO_ACCOUNT_SID = "your_twilio_sid"
TWILIO_AUTH_TOKEN = "your_twilio_token"

# For email reports:
EMAIL_CONFIG = {
    "sender_email": "your_email@gmail.com",
    "sender_password": "your_app_password"  # Use Gmail App Password
}

# For AI scorecards:
GROQ_API_KEY = "your_groq_api_key"

# For MongoDB Atlas:
MONGODB_CONNECTION_STRING = "your_mongodb_connection_string"
Note: The system will work for basic speed estimation even without these APIs.

🎮 How to Use
Step 1: Run Basic Speed Estimation
bash
python ultralytics_example.py --source_video_path your_video.mp4
This will open a window showing real-time vehicle detection

Each vehicle will have its speed displayed

Speeding vehicles (>100 km/h) will be highlighted

Step 2: Press 'q' to quit processing
After processing completes, you'll see statistics in the terminal

Data will be saved to ultimate_traffic_data.json

Step 3: View Results
Check the generated files:

ultimate_traffic_data.json - Complete analysis data

Console output - Summary statistics

📊 Understanding the Output
Real-time Display:
Green boxes: Normal speed vehicles

Red boxes: Speeding vehicles (>100 km/h)

Labels: #ID VehicleType Speed km/h

Header: Total vehicles and violations count

Terminal Output:
text
📋 Analysis ID: analysis_20240115_143022
✅ Video loaded successfully:
   📏 Resolution: 1920x1080
   🎞️  FPS: 30.00
   📊 Total frames: 1800
🎯 Starting video processing...
📊 Frame 100: 15 vehicles, 3 violations
✅ VIDEO PROCESSING COMPLETE!
📈 Final Results:
   • Total Vehicles: 45
   • Total Violations: 8
   • Max Speed: 125 km/h
   • Processing Time: 60.32 seconds
💾 Local data saved
Generated Files:
ultimate_traffic_data.json - Complete dataset for further analysis

ultimate_scorecard.txt - AI-generated insights (if enabled)

auto_dashboard.py - Interactive web dashboard (if enabled)

🛠️ Troubleshooting
Common Issues:
Video won't open:

Check file path is correct

Ensure video format is supported (mp4, avi, mov)

Try using absolute path: --source_video_path /full/path/to/video.mp4

No vehicles detected:

Adjust --confidence_threshold lower (try 0.1)

Check video quality and lighting

Ensure vehicles are clearly visible

Speed calculations inaccurate:

Adjust SOURCE polygon coordinates in code

The polygon should cover the road area where vehicles move

Import errors:

Install missing packages: pip install missing-package-name

Ensure Python version is 3.8+

📈 Performance Tips
For faster processing: Use lower resolution videos

For better accuracy: Use higher quality videos with clear vehicle views

Adjust confidence threshold:

Lower (0.1-0.3): More detections, more false positives

Higher (0.5-0.8): Fewer detections, higher accuracy

🎥 Demo Video
[Include a link to your demo video or screenshots here]

📚 Technical Details
Core Technologies:
YOLOv8: State-of-the-art object detection

ByteTrack: Multi-object tracking algorithm

Perspective Transformation: Accurate speed calculation

OpenCV: Video processing and computer vision

Streamlit: Interactive web dashboard

MongoDB Atlas: Cloud database storage

Algorithms:
Vehicle Detection: YOLOv8 convolutional neural network

Vehicle Tracking: ByteTrack with Kalman filtering

Speed Calculation: Pixel-to-real-world transformation

Violation Detection: Threshold-based speed checking

🤝 Contributing
Feel free to fork this repository and submit pull requests for:

Bug fixes

New features

Performance improvements

Documentation enhancements


🙏 Acknowledgments
Ultralytics for YOLOv8

Supervision library for computer vision utilities

Twilio for SMS services

MongoDB for cloud database

Streamlit for dashboard framework

Groq for AI API services

📞 Support
For questions or issues:

Check the troubleshooting section above

Open an issue on GitHub

Contact: +91 8788594863
