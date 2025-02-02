# Hands-Free Instant Web STT Component Set
Without buttons or wake-words, use any browser (Cordova/Electron) to passively listen for any voice, record until voice stops, POST audio to Faster-Whisper & get transcription back with language detected. 

Tiny model on my GTX1070 gave results in less than half a second, so we'll call it instant... Large-V2 model took 1.5-3 sec.
To configure VAD & STT libraries see their documentation.
See ricky0123/vad and https://www.vad.ricky0123.com for details on the Voice Activity Detection.
Implementing in React? See https://www.vad.ricky0123.com/docs/react 



#### Silero VAD browser library by [ricky0123](https://github.com/ricky0123/vad)
#### STT web service endpoint by [ololoshka2871](https://github.com/ololoshka2871/Voice-2-txt-faster-whisper) 
#### ... which is based on [guillaumekln/faster-whisper](https://github.com/guillaumekln/faster-whisper) (and OpenAI model)


## How to run
1. Create python virtual environment: `python3 -m venv venv`
2. Activate virtual environment: `source venv/bin/activate`
3. Install requirements: `pip install -r requirements.txt`
4. Run server: `python main.py` (Enable CUDA: -c cuda) (Tiny model: -m tiny) (Large model: -m large-v2)
5. Open browser to localhost:3157 (0.0.0.0 is not valid for mic access outside HTTPS).
6. Approve microphone access and start speaking. Output in console & page.


## Motivation
I wanted hands-free STT in a web client using the *Faster-Whisper* model. 
But the REST server for the base Whisper model did not work with the *Faster* model.
After spending a couple days messing around I found the code from ololoshka and it worked!
Since I was unable to find anything like this all put together as a component set, here it is.
This is just a starter/skeleton/sample for adding this feature to your own app/bot/etc.
All credit to the devs behind all these projects, and the open source ethos.
