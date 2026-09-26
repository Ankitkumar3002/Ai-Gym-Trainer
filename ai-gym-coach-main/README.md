# AI Gym Coach

AI Gym Coach is a real-time fitness assistant that uses computer vision to analyze exercise form, track repetitions, and provide coaching feedback through the webcam. It is built as a Streamlit app and includes a separate landing page for product presentation.

## Project Links

- **Project folder:** [ai-gym-coach-main](https://github.com/Ankitkumar3002/Ai-Gym-Trainer/tree/main/ai-gym-coach-main)
- **Live application:** [AI Real-time GYM Coach](https://ai-realtime-gym-coach.streamlit.app/)
- **Repository:** [Ankitkumar3002/Ai-Gym-Trainer](https://github.com/Ankitkumar3002/Ai-Gym-Trainer)

## Overview

This project combines:

- Computer vision pose analysis using MediaPipe and OpenCV
- Exercise-specific form detection for squats, push-ups, biceps curls, shoulder press, and lunges
- Real-time rep counting and workout tracking
- AI-powered voice coaching with Groq + text-to-speech
- Workout history persistence for logged-in users
- A polished landing page for showcasing the product

The app is designed to help users train safely and effectively by identifying posture issues in real time and giving instant corrective feedback.

## Key Features

- Live exercise tracking from webcam input
- Real-time feedback on posture and movement quality
- Exercise presets for multiple workout movements
- Sets/reps planning before starting a session
- AI coaching responses and voice prompts
- Session summaries and exercise history
- Responsive product landing page

## Tech Stack

- Python
- Streamlit
- OpenCV
- MediaPipe
- streamlit-webrtc
- Pandas
- Groq API
- gTTS (Google Text-to-Speech)
- HTML/CSS landing page

## Project Structure

```text
AI-Gym-Trainer/
├── ai-gym-coach-main/
│   ├── LandingPage/
│   │   ├── index.html
│   │   ├── style.css
│   │   ├── fonts/
│   │   └── IMGs/
│   └── Main App/
│       ├── main.py
│       ├── requirements.txt
│       ├── packages.txt
│       ├── core/
│       ├── detectors/
│       ├── ml_models/
│       ├── pages/
│       ├── services/
│       ├── static/
│       ├── tutorial-info/
│       └── ...
└── README.md
```

## Application Modules

### Landing Page

The `LandingPage` folder contains the marketing website for the app. It includes a hero section, feature highlights, metrics, demo video area, and contact links.

### Main App

The `Main App` folder contains the actual AI trainer application.

Important parts include:

- `main.py` — app entry point, workout flow, camera integration, and session UI
- `detectors/` — pose and movement evaluation logic for each exercise
- `services/` — app services for authentication, coaching, state, persistence, tracking, UI, and computer vision
- `static/` — front-end styling assets for the Streamlit app
- `requirements.txt` — Python dependencies

## Supported Exercises

The app supports detection and feedback for these exercise types:

- Squats
- Push-ups
- Biceps curls
- Shoulder press
- Lunges

## How It Works

1. User logs in to the app.
2. User selects an exercise, target sets, and reps.
3. The webcam stream starts using WebRTC.
4. MediaPipe pose landmarks are processed frame by frame.
5. Exercise-specific detectors calculate joint angles and movement quality.
6. The app tracks rep counts and updates workout progress.
7. The AI coach provides real-time corrective instructions using voice and chat feedback.
8. Workout history is stored for future review.

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/Ankitkumar3002/Ai-Gym-Trainer.git
cd Ai-Gym-Trainer
```

### 2. Navigate to the app directory

```bash
cd "ai-gym-coach-main/Main App"
```

### 3. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Set your Groq API key

Create a `.env` file or export the environment variable:

```bash
export GROQ_API_KEY="your_api_key_here"
```

On Windows PowerShell:

```powershell
$env:GROQ_API_KEY="your_api_key_here"
```

### 6. Run the app

```bash
streamlit run main.py
```

## Landing Page

To preview the static landing page, open `ai-gym-coach-main/LandingPage/index.html` in a browser or serve the directory with a local HTTP server:

```bash
cd ai-gym-coach-main/LandingPage
python -m http.server 8000
```

Then visit [http://localhost:8000](http://localhost:8000).

## Environment Notes

- Webcam access is required for real-time pose detection.
- A valid Groq API key is required for AI coaching voice feedback.
- The app is optimized for local machine use and browser-based execution.
- Use a well-lit environment and position your full body within the camera frame for better pose detection.

## Screenshots and Demo

The landing page includes product presentation assets, a gallery, and a demo video section. The main application works in a browser session and uses the user's webcam for live exercise analysis.

## Future Improvements

Potential enhancements for this project include:

- More exercises and movement templates
- Improved exercise detection accuracy
- Better personalized coaching models
- User profile and progress analytics
- Mobile-friendly and deployment-ready packaging
- REST API or backend service integration

## Project Summary

AI Gym Coach is a practical demonstration of AI-powered fitness training using real-time computer vision and coaching feedback. It showcases how machine learning, pose estimation, and AI assistants can be combined to help users improve their form, track workouts, and train more consistently.

## Credits

This project uses several open-source technologies and libraries, including:

- Streamlit
- MediaPipe
- OpenCV
- Groq
- gTTS

This project is intended for learning, experimentation, and personal fitness assistance use.
