AI Exercise Tracker Web App
This project is a real-time AI-powered exercise tracker that uses Flask, OpenCV, and MediaPipe to detect human poses and count exercise repetitions. It features BMI calculation, calorie tracking, graphical analytics, and a user-friendly web interface.

🚀 Features
🎥 Real-time pose detection via webcam (OpenCV + MediaPipe)

🔁 Automatic repetition counting for:

Bicep Curls

Sit-ups

📊 Calorie chart based on exercise reps

📈 Exercise line chart to show activity over time

📦 Exercise history stored in SQLite database

🧮 BMI Calculator with automatic health status classification

💾 Data persistence using SQLAlchemy ORM

🎨 Responsive UI with gradient background and animated buttons

📂 Folder Structure
bash
Copy
Edit
.
├── app.py                   # Main Flask backend with camera tracking logic
├── exercise_logs.db         # SQLite database (auto-generated)
└── static/
    └── style.css            # (Optional) External styles if extended
🛠️ Setup Instructions
✅ Requirements
Install the following packages using pip:

bash
Copy
Edit
pip install flask flask_sqlalchemy opencv-python mediapipe matplotlib pytz numpy
▶️ Run the App
bash
Copy
Edit
python app.py
Then open your browser and go to:
http://localhost:5000

📸 Webcam Pose Tracking
Exercises Supported:
Bicep Curls

Based on shoulder-elbow-wrist angle

Sit-ups

Based on shoulder-hip-knee angle

MediaPipe's pose estimation is used to track key landmarks and calculate joint angles. Reps are counted by checking when the angle transitions from a contracted to extended position.

📈 Charts & Visualization
Calories Chart: Total calories burned each day (based on reps × calories/exercise).

Exercise Line Chart: Daily exercise count visualized per type.

Charts are generated using matplotlib and rendered as PNG images.

📋 BMI Calculator
BMI is calculated from user input (height and weight):

python
Copy
Edit
BMI = weight / ((height / 100) ** 2)
Categories:

Underweight: < 18.5

Normal: 18.5–24.9

Overweight: 25–29.9

Obese: ≥ 30

🧠 Code Overview
Models (SQLAlchemy)
ExerciseLog: Stores exercise type, count, and timestamp

UserBMI: Stores height, weight, calculated BMI, and health status

Key Routes
Route	Function
/	Home page with webcam feed, charts, BMI form, and history
/video_feed	Live webcam stream with pose tracking
/toggle_tracking	Start/stop webcam tracking
/switch_exercise	Toggle between bicep curls and sit-ups
/reset_counter	Reset repetition counter
/submit_bmi	Save BMI data
/calories_chart	View calories burned over time
/exercise_line_chart	View reps per day by exercise

🎯 Future Scope
🧍 Add more exercises (push-ups, lunges, squats)

👥 Add user registration & login system

📱 Convert into a mobile-friendly PWA or Android app

💾 Export data as CSV/PDF reports

🗃️ Use PostgreSQL or Firebase for cloud storage
👨‍💻 Author
Syed Akash Hussain
BSc Data Science | Assam Downtown University
Email: akashhussian7771@gmail.com
GitHub: @Akashhussain111
