# 👁️ Eye Mouse Control

Control your computer mouse completely hands-free using just your eyes and facial gestures.

This project uses **OpenCV** and **MediaPipe** to track your eye movements and map them to the screen cursor. It detects blinks to perform mouse clicks.

## ⚠️ Important Compatibility Note

**This project requires Python 3.10.**

Google's MediaPipe library has removed the `mp.solutions` API in newer versions. To ensure this code works correctly, you must use **MediaPipe v0.10.14**, which is most stable on Python 3.10.

If you are using Python 3.11, 3.12, or 3.13, you **must** create a virtual environment with Python 3.10 (see instructions below).

## 📦 Requirements

* Python 3.10 (Required)
* Webcam

## 🛠️ Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/Eye-Mouse.git](https://github.com/YOUR_USERNAME/Eye-Mouse.git)
    cd Eye-Mouse
    ```

2.  **Create a Virtual Environment (Recommended):**
    Since you likely have a newer Python installed, use this command to force Python 3.10 for this project:

    *Windows (PowerShell):*
    ```powershell
    py -3.10 -m venv venv
    .\venv\Scripts\activate
    ```
    
    *Mac/Linux:*
    ```bash
    python3.10 -m venv venv
    source venv/bin/activate
    ```

3.  **Install Dependencies:**
    Once your virtual environment is active (you should see `(venv)` in your terminal), run:
    ```bash
    pip install -r requirements.txt
    ```

## 🚀 How to Run

1.  Make sure your webcam is connected.
2.  Run the script:
    ```bash
    python main.py
    ```

## 🎮 Controls

* **Move Cursor:** Simply look around. The mouse cursor follows your pupil movement.
* **Left Click:** Blink your **Left Eye**.
    * *Note:* The code includes a small "cooldown" so it doesn't double-click accidentally.
* **Exit:** Press `Esc` or `Ctrl+C` in the terminal to stop the program.

## 🔧 Troubleshooting

* **"AttributeError: module 'mediapipe' has no attribute 'solutions'":**
    * This means you are running a too-new version of MediaPipe. Run `pip uninstall mediapipe` then `pip install mediapipe==0.10.14`.
* **Cursor is jittery:**
    * Ensure you are in a well-lit room. Good lighting helps the AI detect the iris more stably.
* **Clicks are not registering:**
    * Move closer to the camera or adjust the `0.0095` threshold in `main.py` if your eyes are naturally smaller/larger.

## 📄 License
[MIT](https://choosealicense.com/licenses/mit/)
