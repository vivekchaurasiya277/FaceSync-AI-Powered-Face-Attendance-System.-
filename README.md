# FaceSync 📸🏫

**FaceSync** is a state-of-the-art, AI-powered Face Attendance System built for modern educational institutions and corporate environments. It utilizes deep learning to recognize faces with high precision, enforces geographical constraints with geolocation math, and provides an interactive, premium glassmorphism UI for seamless administration and student self-service.

## ✨ Features

* **High-Performance Face Recognition**: Uses `insightface` and OpenCV for robust, real-time face detection and embedding extraction.
* **Mobile Geofencing & Self-Attendance**: Students can mark attendance from their personal devices. The system leverages HTML5 APIs to capture a live selfie and verifies GPS coordinates against a centrally configured College Geofence using Haversine distance math.
* **Strict Time Windows**: Configurable Attendance Start Time, End Time, and programmable "Buffer Times" to manage tardiness.
* **Interactive Dashboards**:
  * **Admin Panel**: Manage users, view system-wide logs, approve/reject leave applications, set global Geofence constraints, and issue disciplinary notices.
  * **Student Panel**: View real-time attendance analytics, submit leave requests with document uploads, and mark mobile attendance.
* **Bulk CSV Import**: Rapidly onboard hundreds of students or staff by uploading a simple `.csv` file.
* **Sleek UI/UX**: A responsive, mobile-first design featuring Dark Mode, Vanta.js 3D backgrounds, and premium glassmorphism panels.

## 🛠️ Tech Stack

* **Backend**: Python, Flask, SQLite3
* **AI/CV Engine**: OpenCV, InsightFace (ArcFace)
* **Frontend**: Vanilla HTML5, CSS3, JavaScript, Chart.js (for Analytics), Vanta.js (for 3D aesthetics)

## 🚀 Installation & Setup

### 1. Prerequisites
* Python 3.8+
* A working USB Webcam (for Kiosk mode)

### 2. Clone the Repository
```bash
git clone https://github.com/yourusername/face-attendance-system.git
cd face-attendance-system
```

### 3. Install Dependencies
```bash
pip install flask opencv-python insightface onnxruntime numpy pandas
```
*(Note: If you plan to use GPU acceleration for face recognition, install `onnxruntime-gpu` instead of `onnxruntime`)*

### 4. Initialize the Database
The application relies on an SQLite database (`attendance.db`). It will be automatically created and seeded on the first run.

### 5. Run the Server
```bash
python web_app.py
```
The application will start on `http://127.0.0.1:5000`.

## 📖 Usage Guide

### Kiosk Mode (Hardware)
Leave the server running on a machine with a connected webcam. The main index page acts as a Kiosk. Faces are detected in real-time, bounding boxes are drawn, and recognized individuals are automatically logged into the system.

### Admin Access
1. Click the "Admin Settings" or "Lock" icon on the main dashboard.
2. Enter the default admin password.
3. From the Admin Dashboard, navigate to **System Settings** to configure your College's GPS coordinates and attendance time buffers.

### Mobile Attendance (Students)
1. Students log into their dashboard via the main page (using their ID/Name).
2. On mobile devices, they click **"📍 Mark Mobile Attendance"**.
3. They grant GPS and Camera permissions, snap a selfie, and the system handles the rest!

## 🛡️ Security & Privacy
* Face embeddings are generated and stored securely in the local SQLite database. Raw images of users are not permanently stored unless specifically uploaded for initial registration.
* Geolocation data is strictly processed at the time of attendance verification and is not continuously tracked.

## 🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## 📄 License
[MIT](https://choosealicense.com/licenses/mit/)
