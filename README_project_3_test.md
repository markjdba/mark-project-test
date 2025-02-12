# Speech_to_text_summarization_app

## PROJECT DESCRIPTION

** Earnings calls speech to text **
Our team used used NLP, transformers, Whisper, and OpenAI to transcribe Nvidia’s most recent earnings call and translate this transcription into French, Spanish, and Japanese.

Our goals: 
1. Most publicly traded companies have quarterly earnings calls where the company’s management team discusses the financial performance, future plans, and answers questions from investors and analysts.
2. These calls provide valuable insights into current performance and management perspective; however, analysts and investors may not have the time to sit through the earnings call.
3. To address this challenge the team has developed an application where an audio file could be uploaded and the app would translate speech to text, provide a summary and then also translate into other languages.
4. During development, the team recognized there could be broader usages.

## INSTALLATION

1. Ensure you have Python 3.12 or higher installed.
2. Clone this repository: `git clone https://github.com/jessegunter/Speech_to_text_summarization_app.git`

## USAGE

### Install required Python packages
pip install flask
pip install flask-cors
pip install python-dotenv
pip install openai
pip install whisper
pip install pydub
pip install numpy
pip install transformers

### if you don’t have home brew installed, run this entire command in terminal and follow prompts
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

### Install FFmpeg on Mac with Homebrew
brew install ffmpeg

### To run front end:
Navigate to file and run open Frontend.html or double click in finder

### To run backend:
Python Flask_Backend.py

### Here is an example:
(base) jessegunter@Jesses-MacBook-Pro Speech_to_text_summarization_app % python Flask_Backend.py
 * Serving Flask app 'Flask_Backend'
 * Debug mode: on
* Running on http://127.0.0.1:5000
Press CTRL+C to quit
 * Restarting with watchdog (fsevents)
 * Debugger is active!
 * Debugger PIN: 815-082-824


## APPROACH IN ACHIEVING PROJECT GOALS:
1. User Interface: HTML and Python used to develop user interface.
2. MP3 File: Any MP3 file can be uploaded through the interface.
3. Speech to Text Transformation: Whisper was utilized to transform speech into a text file.
4. Text to Summary Transformation: GPT-3.5-turbo was utilized to summarize the text file generated with Whisper.
5. Text Summary Translated to Different Languages: GPT-3.5-turbo was utilized to translate the summary into different languages.

## USER INTERFACE   
1. An interface was developed that allows the user to upload a MP3 to be summarized and translated.
2. The front end was developed in HTML and python code drives the back end of the user interface. 
3. How it works:
    A. User chooses an audio file to upload
    B. Radio button selection of Full Transcription or Summarize Text
    C. Choose Language: Select from drop down the language of the audio file
    D. Radio button selection of user wants it translated to different language
    E. Translate To: Select from drop down the language to translate into
    F. Upload & Transcribe kicks off the process

## Whisper
1. Whisper is an OpenAI developed AI model that is highly accurate in transcribing speech into text.
2. The Whisper AI model was trained on 680,000 hours of multilingual supervised data from the internet.
3. Whisper supports speech to text in over 90 languages.
4. The team utilized Whisper to transcribe an audio file in English to an English text file.
5. The team used Nvidia’s Q3 FYFY25 Financial Results.mp3 during the development of project

## Text Summarization
1. The team utilized Mistral 7b openorca.Q6_K.gguf to take the text output from the Whisper model and summarize.
2. Mistral 7b openorca.Q6_K.gguf, available on Hugging Face, is a large language model that is well-suited for summarizing long texts in an efficient and fast manner.
3. To ensure the text does not exceed limitations a chunk text function was created that divided the input text into a max length equal to 2,048
4. The chunks were summarized and then joined for a combined summary.

## Summarization Translation
1. Among all the capabilities of ChatGPT, the team utilized its API to translate text from one language to another.
2. A function was created that takes two arguments: the text to translate and target language.
3. The openai.Completion.create() method was used to send a text completion request and asks the API to translate the text into the target language.
4. The language translation function also uses the chunk text function to ensure the text does not exceed limitations.


### PROBLEMS ENCOUNTERED:
The team explored different pre-trained models to summarize the transcription text including Mistral 7b openorca.Q6_K.gguf.
However, the team had difficulty integrating the model into the developed code so moved to a streamlined approach of using GPT-3.5-turbo for both summarization and translation


### FUTURE CONSIDERATIONS:
Given more time the team would explore different ways to develop a confidence score in an efficient manner.


## REFERENCES
1. Nvidia https://events.q4inc.com/attendee/313193359/guest
2. AmongMedium https://medium.com/@kharatmoljagdish/using-openai-whisper-python-library-for-speech-to-text-dda4f558fccc
3. AmongWhisper https://github.com/openai/whisper
4. AmongFFmpeg https://www.wikihow.com/Install-FFmpeg-on-Windows
5. AmongHuggingFace https://huggingface.co/TheBloke/Mistral-7B-OpenOrca-GGUF/blob/main/mistral-7b-openorca.Q6_K.gguf
6. AmongMistral https://docs.mistral.ai/getting-started/models/models_overview/


## TEAM MEMBERS
1. Jesse Gunter
2. Mark Johnson
3. Marianne Mittelstadt
4. Tonya Soriano
5. Ethan Wyman



