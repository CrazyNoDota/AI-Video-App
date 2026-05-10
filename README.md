# AI Video Generator App

A simple Python desktop application built with `customtkinter` that connects to a Google Colab GPU backend via Gradio API to generate AI videos (Text-to-Video and Image-to-Video).

## Setup Instructions

### 1. Cloud Backend (Google Colab)
1. Upload the `Colab_API_Backend.ipynb` file to [Google Colab](https://colab.research.google.com/).
2. Change Runtime to **T4 GPU**.
3. Click **Run All**.
4. Copy the `https://xxxxxx.gradio.live` link generated at the bottom.

### 2. Desktop App
Run the app locally:
```bash
pip install -r requirements.txt
python app.py
```
Or use the provided `Start_Video_App.bat` script on Windows.

Paste the Gradio link into the app, enter your prompt/image, and generate your video!

## Docker

A `Dockerfile` is included to containerize the Python desktop app.
*Note: Running a GUI application from inside a Docker container requires X11 forwarding to be configured on your host machine (e.g., using VcXsrv on Windows).*

```bash
docker build -t ai-video-app .
# Example run command (Linux): docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix ai-video-app
```