# 🏋️‍♂️ AI Real-time Gym Coach (Apna AI Coach)

An interactive, real-time AI-powered fitness coaching web application. This application utilizes **MediaPipe** for high-fidelity pose estimation, **Streamlit** (with WebRTC) for high-performance camera streaming in the browser, and the **Groq API** paired with **Google Text-to-Speech (gTTS)** to deliver proactive, voice-guided AI coaching during your workouts.

---

## ✨ Features
- **Real-time Pose Tracking:** Real-time metrics calculations (angles, alignment, stability) for 5 popular exercises:
  - Squats (Knee angle, back angle, depth status)
  - Push-ups (Elbow angle, body alignment, hip position)
  - Biceps Curls (Elbow angle, shoulder stability, swing detection)
  - Shoulder Press (Elbow angle, arm extension, back arch detection)
  - Lunges (Front knee angle, torso alignment, balance status)
- **AI Voice Coaching:** Dynamic voice encouragement and correction driven by a **Groq LLM** and synthesized via **gTTS**.
- **Workout Dashboard:** Persistent tracking of sets, reps, active workout time, and complete history aggregate view.
- **Modern User Experience:** Styled with a polished custom theme, bespoke typography, and modular authentication pages.

---

## 🏗️ Project Structure
```text
├── core/                         # Core abstractions for exercise evaluation
├── detectors/                    # Concrete pose rules and calculations per exercise
├── ml_models/                    # MediaPipe ML models (pose_landmarker_full.task)
├── services/                     
│   ├── auth/                     # Authentication components and login page
│   ├── coaching/                 # Groq client, voice engine, and LLM text generation
│   ├── config/                   # Exercise selections and parameters configuration
│   ├── persistence/              # SQLite database setups and querying repositories
│   ├── state/                    # Session management helper utilities
│   ├── tracking/                 # Live state synchronization metrics
│   ├── ui/                       # Theme injectors and CSS loader rules
│   └── vision/                   # OpenCV and MediaPipe frame parsing engine
├── static/                       # Custom design assets (CSS styles, clean fonts)
├── main.py                       # Main Streamlit web application entrypoint
├── packages.txt                  # Linux OS dependencies for Streamlit Cloud deployment
├── requirements.txt              # Python packages dependencies list
└── .gitignore                    # Ensures environment keys & virtualenvs remain private
```

---

## 🛠️ Prerequisites
- **Python 3.12** is required (versions such as 3.13 are currently incompatible due to lack of stable prebuilt binaries for `mediapipe` and `opencv`).
- A **Groq API Key** (Get one for free at [Groq Console](https://console.groq.com/)).

---

## 🚀 Local Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/aDImAX1729/ai-gym-trainer
   cd ai-gym-trainer
   ```

2. **Set Up a Virtual Environment (Python 3.12):**
   Using `uv` (recommended):
   ```bash
   uv venv --python 3.12
   .venv\Scripts\activate
   ```
   Or using standard Python:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # On macOS/Linux, use: source .venv/bin/activate
   ```

3. **Install Dependencies:**
   Using `uv`:
   ```bash
   uv pip install -r requirements.txt
   ```
   Or using `pip`:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables:**
   Create a `.env` file in the root folder of the project:
   ```env
   GROQ_API_KEY="your_actual_groq_api_key_here"
   ```

5. **Run the Application:**
   Using `uv` (shortcut):
   ```bash
   uv run streamlit run main.py
   ```
   Or using standard streamlit command:
   ```bash
   streamlit run main.py
   ```

