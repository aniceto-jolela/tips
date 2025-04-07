# Record Screen on Kali Linux

> Tools:
- OBS Studio
- Simple Screen Recorder
- Kazam

1. #### Using OBS Studio

OBS Studio is a powerful, open-source tool for screen recording and streaming.

Install OBS Studio: Open the terminal and run:

```bash
sudo apt-get install obs-studio
```

Configure OBS Studio:

- Launch OBS Studio.
- In the "Sources" section, click the "+" button and select "Display Capture" (to record the entire screen) or "Window Capture" (to record a specific window).
- Adjust resolution, frame rate, and other settings as needed.

Set Audio and Video:

- Configure audio in the "Mixer" section by selecting your microphone or audio source.
- Adjust video settings under "Settings" > "Output" to choose format, bitrate, and resolution.

Start Recording:

- Click "Start Recording" in the "Controls" section.
- Pause or stop recording as needed. The recording will be saved in the default location or a custom directory you specify.

2. #### Using Simple Screen Recorder

Simple Screen Recorder is another lightweight option for screen recording.

Install Simple Screen Recorder: Run the following command in the terminal:

```bash
sudo apt install simplescreenrecorder
```

Configure Settings:

- Launch the application.
- Choose to record the entire screen or a specific area.
- Set frame rates and enable audio recording by selecting your microphone.

Start Recording:

- Preview your settings and click "Start Recording."
- Minimize the application to hide it during recording.
- Stop and save the recording when finished.

3. #### Using Kazam

Kazam is a user-friendly screen recorder with basic features.

Install Kazam: Use this command in the terminal:
```bash
sudo apt install kazam
```

Configure Kazam:

- Launch Kazam and select whether to record the full screen, a window, or a specific area.
- Enable audio recording and choose your microphone if needed.

Start Recording:

- Click "Record." You can pause or stop recording as necessary.
- Save the video in your preferred format (e.g., MP4) and directory


#
#

|Tool |Features|Installation Command|
-----------|---|---|
|OBS Studio |	Advanced features for streaming/recording |sudo apt-get install obs-studio|
|Simple Screen Recorder | Lightweight, easy-to-use| sudo apt install simplescreenrecorder|
|Kazam | Simple interface for basic recordings | sudo apt install kazam
|