AIoT Smart Proctoring & Vision Dashboard

This project is an AIoT-based examination monitoring prototype.
IoT components collect and transmit exam-room video data.
AI components analyze motion and pose landmarks to detect suspicious behavior.

REQUIREMENTS:
- Python 3.8 or higher
- Node.js 18 or higher
- npm

PYTHON SETUP:
1. Open Terminal in the project folder.
2. Create a virtual environment:

   python3 -m venv .venv

3. Activate it:

   source .venv/bin/activate

4. Install Python dependencies:

   pip install fastapi uvicorn websockets opencv-python mediapipe numpy requests

RUN THE BACKEND:
1. In the project folder, run:

   python server.py

2. The FastAPI server should run on:

   http://127.0.0.1:8000

RUN THE DASHBOARD:
1. Open a second Terminal.
2. Go to the dashboard folder:

   cd dashboard

3. Install dependencies:

   npm install

4. Start the dashboard:

   npm run dev

5. Open the dashboard in a browser:

   http://localhost:3000

6. The monitor page is:

   http://localhost:3000/monitor

RUN THE AI SCANNER:
1. Open a third Terminal.
2. Activate the Python environment again:

   source .venv/bin/activate

3. Run:

   python auto_scanner.py

NOTE:
The scanner expects a video file such as Video3.mp4.
If the video file is not included in GitHub because of size limits, place the video file inside the project folder and update VIDEO_PATH in auto_scanner.py.
The GitHub upload zip includes pose_landmarker_lite.task for auto_scanner.py.
The larger pose_landmarker_heavy.task file is excluded from the upload zip to stay under GitHub's 25 MB web upload limit.
If you want to run auto_scanner2.py or auto_scanner3.py, add pose_landmarker_heavy.task back into the project folder.

PROJECT COMPONENTS:
- auto_scanner.py: Edge AI scanner using OpenCV and MediaPipe
- server.py: FastAPI relay server
- dashboard/: Web dashboard for proctor/admin review
- pose_landmarker_lite.task: MediaPipe pose model file

LIMITATION:
This is a prototype. The suspicious-behavior detection uses heuristic rules and still needs formal evaluation using precision, recall, false positive rate, latency, and human review agreement.
