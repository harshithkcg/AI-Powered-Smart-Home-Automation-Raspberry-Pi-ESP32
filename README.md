# AI-Powered Voice Assistant for Smart Home Automation

An intelligent voice-controlled home automation system built using **Python**, **Raspberry Pi**, **ESP32**, **MQTT**, **DeepSeek AI**, **Wikipedia API**, **Gmail SMTP**, and **Twilio WhatsApp**. The system enables users to control home appliances using voice commands, answer general questions using AI, send emails, monitor water tank levels, and automatically send WhatsApp alerts.

---

## 🚀 Features

### 🎙️ Voice-Controlled Home Automation
- Turn Light ON/OFF
- Turn Motor ON/OFF
- Voice feedback after every command
- Hands-free smart home control

**Example Commands**
- "Light on"
- "Light off"
- "Motor on"
- "Motor off"

---

### 🤖 AI Assistant (DeepSeek AI)

The assistant uses the **DeepSeek R1** model through the OpenRouter API to answer general questions.

**Example**

**User:**
```
Who invented Python?
```

**Assistant:**
```
Python was created by Guido van Rossum in 1991.
```

---

### 📚 Wikipedia Search

Users can choose Wikipedia as the information source for quick factual answers.

**Example**

**User**
```
Tell me about Bengaluru
```

The assistant returns a short summary from Wikipedia.

---

### 📧 Voice-Based Email Sending

The assistant can send emails completely through voice.

**Example**

```
User: Send email

Assistant: What should I email?

User: Meeting starts at 10 AM tomorrow.
```

The email is automatically sent to all configured recipients.

**Supports**
- Multiple recipients
- Gmail SMTP
- Voice dictation

---

### 💬 WhatsApp Notifications

When the ESP32 detects that the water tank is full, the assistant automatically sends a WhatsApp message using Twilio.

**Notification**

```
🌱 Alert: Tank is full.
Motor turned off automatically.
```

---

### 💧 Automatic Water Tank Monitoring

The ESP32 continuously monitors the water level.

**Workflow**

```
Water Tank Full
       │
       ▼
ESP32 publishes MQTT message
       │
       ▼
Python receives notification
       │
       ▼
Motor OFF
       │
       ▼
Voice Announcement
       │
       ▼
WhatsApp Alert
```

---

### 📡 MQTT Communication

Communication between Raspberry Pi and ESP32 is performed using MQTT.

| Topic | Description |
|--------|-------------|
| home/device/control | Sends Light and Motor commands |
| home/device/tank | Receives Tank Full notification |

Supported Commands

```
ON
OFF
MOTOR ON
MOTOR OFF
```

---

### 🔊 Voice Feedback

The assistant provides natural speech responses using Google Text-to-Speech.

Examples

- Listening...
- Light On
- Motor Off
- Email Sent Successfully
- Tank is Full

---

## 🏗️ System Architecture

```
                     User
                      │
               Voice Command
                      │
            Raspberry pi 4 {Speech Recognition}------------- Voice Feedback
                      │                                            |
             Command Processing                                    |
                      │                                            |
        ┌─────────────┴─────────────┐                              |
        │                           │                              |
   Home Automation             AI Assistant------------------------|
        │                           │
      MQTT                   DeepSeek API
        │                           │
      ESP32                 Wikipedia API
        │
   Relay Module
        │
 Appliances Control
        
```

---

## 🛠️ Technologies Used

### Programming Language
- Python 3

### Hardware
- Raspberry Pi
- ESP32
- Relay Module
- Water Level Sensor
- Microphone
- Speaker

### Communication
- MQTT
- Wi-Fi

### Artificial Intelligence
- DeepSeek R1
- OpenRouter API

### APIs & Services
- Wikipedia API
- Gmail SMTP
- Twilio WhatsApp API

### Python Libraries
- SpeechRecognition
- gTTS
- pygame
- wikipedia
- paho-mqtt
- requests
- Twilio
- smtplib
- sounddevice

---

## 📂 Project Structure

```
Voice-Assistant/
│
├── main.py                 # Main application
├── requirements.txt        # Python dependencies
├── README.md
├── assets/
│   ├── images/
│   └── diagrams/
└── esp32/
    └── esp32_code.ino
```

---

## ⚙️ Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/AI-Voice-Assistant.git
cd AI-Voice-Assistant
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run the Program

```bash
python main.py
```

---

## 📌 Future Improvements

- Offline AI using Local LLM (Ollama)
- Face Recognition Authentication
- Mobile Application
- Multi-language Voice Support
- Sensor-Based Automation
- Camera-Based Home Monitoring
- Energy Consumption Analytics
- Smart Scheduling

---

## 🔐 Security

**Do NOT upload sensitive credentials to GitHub.**

Store the following in a `.env` file:

- OpenRouter API Key
- Gmail App Password
- Twilio SID
- Twilio Auth Token
- Phone Numbers
- MQTT Broker IP

Add the following to `.gitignore`:

```
.env
__pycache__/
*.pyc
```

---

 
## 📜 License

This project is developed for **educational and research purposes**.

---

## 👨‍💻 Author

**Harshith Sagar K**

Electronics and Communication Engineering  
JSS Science and Technology University, Mysuru
mail: harshithsag5@gmail.com
GitHub: https://github.com/harshithkcg


>> if in case the code is not working plz contact me in mail or else insta link in bio
>> create your own esp32 code by useing this inforamtion or else conme i wil hepl
>> it is free 
