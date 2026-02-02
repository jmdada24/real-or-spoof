# real-or-spoof
# 👤 Face Attendance System

A secure face attendance system with **real-time anti-spoofing detection** built with Streamlit and Python.

## ✨ Features

- **Face Recognition** - Identify registered users via facial features
- **Anti-Spoofing Detection** - Prevents fake face attacks (photos, screens, masks)
- **Time In/Out Tracking** - Log attendance with duplicate prevention
- **Dashboard** - View today's activity stats (check-ins, check-outs, on-time, late)
- **Attendance Records** - Filter by name, date, action with CSV export
- **User Management** - Register and manage users

---

## 📋 Requirements

- **Python 3.10** (recommended)
- **macOS / Linux** (Windows may require additional setup for dlib)
- **Webcam** for face capture

---

## 🚀 Installation

### 1. Clone or navigate to the project

```bash
cd /path/to/face-attendance-system
```

### 2. Create a virtual environment

```bash
python3.10 -m venv venv
```

### 3. Activate the virtual environment

**macOS/Linux:**
```bash
source venv/bin/activate
```

**Windows:**
```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

> **Note for macOS:** If `dlib` fails to install, first install CMake:
> ```bash
> brew install cmake
> ```

---

## ▶️ Running the App

### Option 1: With activated virtual environment

```bash
source venv/bin/activate
cd face-attendance-system
streamlit run app.py
```

### Option 2: Using full path (without activating venv)

```bash
cd face-attendance-system
/path/to/venv/bin/streamlit run app.py
```

### Example:
```bash
cd /Users/johnmheldalumpines/Documents/RealOrSpoof/face-attendance-system
/Users/johnmheldalumpines/Documents/RealOrSpoof/venv/bin/streamlit run app.py
```

The app will open at **http://localhost:8501**

---

## 📖 How to Use

### 1. Register a New User
1. Click **"Register New User"** button
2. Position your face in the camera
3. Capture a photo
4. Enter your name and click **"Complete Registration"**

### 2. Time In
1. On the home page, capture your face
2. Click **"Scan Face"**
3. If recognized, click **"Time In"** button
4. ✅ Your attendance is logged!

### 3. Time Out
1. Capture and scan your face
2. Click **"Time Out"** button
3. 🚪 Your time out is logged!

### 4. View Records
- Click **"View All Records"** to see full attendance history
- Filter by name, date, or action type
- Download as CSV

---

## 📁 Project Structure

```
face-attendance-system/
├── app.py                  # Main Streamlit application
├── requirements.txt        # Python dependencies
├── db/                     # Stored face embeddings (.pickle files)
├── log.txt                 # Attendance log file
└── Silent-Face-Anti-Spoofing/
    ├── resources/
    │   ├── anti_spoof_models/    # Anti-spoofing ML models
    │   └── detection_model/      # Face detection models
    └── src/
        ├── anti_spoof_predict.py
        ├── generate_patches.py
        ├── utility.py
        └── model_lib/
            └── MiniFASNet.py
```

---

## ⚠️ Troubleshooting

### "ModuleNotFoundError: No module named 'torch'"
You're not using the virtual environment. Run with:
```bash
source venv/bin/activate
streamlit run app.py
```

### "No face detected"
- Ensure good lighting
- Face the camera directly
- Keep your face within the frame

### "Spoof detected"
The system detected a fake face attempt. Use your real face, not a photo or screen.

### dlib installation fails
Install CMake first:
```bash
# macOS
brew install cmake

# Ubuntu/Debian
sudo apt-get install cmake
```

---

## 📦 Dependencies

| Package | Purpose |
|---------|---------|
| `streamlit` | Web application framework |
| `opencv-python` | Image processing |
| `face_recognition` | Face detection & recognition |
| `torch` | Deep learning (anti-spoofing) |
| `numpy` | Numerical operations |
| `pandas` | Data handling |
| `Pillow` | Image handling |

---

## 🔒 Anti-Spoofing

This system uses the **Silent-Face-Anti-Spoofing** model to detect:
- 📸 Printed photos
- 📱 Phone/screen displays
- 🎭 Masks

Only real faces are allowed to register and log attendance.

---

## 📝 License

This project is for educational purposes.

