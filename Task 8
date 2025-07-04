import speech_recognition as sr
import pyttsx3
import webbrowser
import datetime
import random

engine = pyttsx3.init()
engine.setProperty('rate', 145)

def speak(text):
    print(f"Bot: {text}")
    engine.say(text)
    engine.runAndWait()

def listen():
    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("🎤 Sun raha hoon...")
        audio = r.listen(source)
    try:
        query = r.recognize_google(audio, language='hi-IN')
        print(f"You: {query}")
        return query.lower()
    except sr.UnknownValueError:
        speak("Arre yeh samajh nahi aaya, dobara bol zara.")
        return ""
    except sr.RequestError:
        speak("Network problem lag rahi hai bhai.")
        return ""

def tell_joke():
    jokes = [
        "Ek ladka computer ke saath date pe gaya. Computer bola: Sorry, I'm already processing someone else! 😂",
        "Teacher: Why are you late? Student: GPS signal lost! 😅",
        "Mujhe coding se itna pyaar ho gaya hai ki ab python mujhe sapne me bhi dikhai deta hai!",
        "Tu itna funny hai ki tere bina WhatsApp status bhi udaas rehta hai!"
    ]
    return random.choice(jokes)

# 🧡 Welcome
speak("Namaste bhai! Main tera voice chatbot hoon. Baat cheet shuru karein?")

while True:
    query = listen()

    if any(p in query for p in ["kaise ho", "kya haal hai", "how are you"]):
        speak(random.choice([
            "Main badhiya hoon bhai! Tu sunaa?",
            "Zinda hoon, system chal raha hai! Tu kaisa hai?",
            "Bas chill hoon, tere jaise dost mil jaaye to aur kya chahiye!"
        ]))

    elif any(p in query for p in ["kya kar rahe ho", "what are you doing", "tum kya kar rahe ho"]):
        speak(random.choice([
            "Bas teri baatein sun raha hoon. Tu kya kar raha hai?",
            "Main to ready hoon baat cheet ke liye! Bata tu kya kar raha hai?",
            "Mujhe laga tu busy hoga, accha hua bula liya!"
        ]))

    elif any(p in query for p in ["bore", "bored", "bore ho gaya"]):
        speak("Bore ho gaya? Chal ek chutkula sun:")
        speak(tell_joke())

    elif any(p in query for p in ["joke", "chutkula", "hansao"]):
        speak("Suno suno! Maza aayega:")
        speak(tell_joke())

    elif any(p in query for p in ["kon ho", "tum kaun ho", "who are you"]):
        speak(random.choice([
            "Main tera chatbot dost hoon, pyar se log mujhe BhaiBot kehte hain!",
            "Main hoon ek awaaz wala dost, bina khaye peeye tere saath ready hoon!",
            "Main tere sawalon ka jawaab dene wala banda hoon — chatbot type 😉"
        ]))

    elif any(p in query for p in ["google kholo", "open google", "google pr le chalo", "take me to google"]):
        speak(random.choice([
            "Le chalo tujhe Google pr. Wahan sab milta hai!",
            "Google ki duniya mein le chala bhai!",
            "Tu bas bol, Google tere liye khol diya!"
        ]))
        webbrowser.open("https://www.google.com")

    elif any(p in query for p in ["youtube kholo", "open youtube", "play a video"]):
        speak("YouTube ready bhai!")
        webbrowser.open("https://www.youtube.com")

    elif any(p in query for p in ["haryanvi song", "gaana chala", "music sunao", "play a music"]):
        speak("Le bhai! Ek number Haryanvi beat bajaa raha hoon.")
        webbrowser.open("https://www.youtube.com/results?search_query=haryanvi+songs")

    elif any(p in query for p in ["time", "samay", "kitna baj gaya"]):
        now = datetime.datetime.now().strftime("%I:%M %p")
        speak(f"Abhi ka time hai {now}")

    elif any(p in query for p in ["date", "aaj ki tareekh", "what's the date"]):
        today = datetime.datetime.now().strftime("%d %B %Y")
        speak(f"Aaj hai {today}")

    elif any(p in query for p in ["exit", "band ho ja", "bye", "chal nikal"]):
        speak(random.choice([
            "Achha bhai, milte hain fir! Apna khayal rakhiyo!",
            "Bye bye! Maza aaya baat karke!",
            "Thik hai bhai, fir milenge. Ram Ram!"
        ]))
        break

    elif query.strip() == "":
        continue

    else:
        speak(random.choice([
            "Yeh thoda naya tha bhai, dubara samjha de?",
            "Samajhne mein dikkat hui. Ek baar aur boliyo.",
            "Lagta hai thoda fast bola tune, zara dheere bol."
        ]))
