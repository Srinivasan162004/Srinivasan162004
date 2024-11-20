import speech_recognition as sr
import pyttsx3
import openai

# Set up the OpenAI API key (Get your API key from OpenAI)
openai.api_key = 'your-openai-api-key'

# Initialize text-to-speech engine
engine = pyttsx3.init()

# Function to speak text (Text-to-Speech)
def speak(text):
    engine.say(text)
    engine.runAndWait()

# Function to recognize speech (Speech-to-Text)
def listen():
    recognizer = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening...")
        audio = recognizer.listen(source)
        
        try:
            # Use Google Web Speech API to recognize speech
            print("Recognizing...")
            query = recognizer.recognize_google(audio)
