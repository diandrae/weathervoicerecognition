const btn = document.querySelector('.talk');
const content = document.querySelector('.content');

//
const rain = [
    'you think this is bad? the whole world will be underwater by 2080 if we dont do anything on climate change '
];

const weather = [ 'oh yeah, the weather will be significantly worse in 5 years if we dont do anything on climate change' ];

const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
const recognition = new SpeechRecognition();

recognition.onstart = function () {
    console.log('voice is activated');
};

recognition.onresult = function(event) {
    const current = event.resultIndex;
    
    const transcript = event.results[current][0].transcript;
    content.textContent = transcript;
    readOutLoud(transcript);
};

//add the listener to the btn

btn.addEventListener('click', () => {
    document.querySelector('.content').style.cssText="font-family:arial;font-size:100px; text-align:center;";
    recognition.start();
   
});

function readOutLoud(message) {
    const speech = new SpeechSynthesisUtterance();

    if (message.includes('rain')) {
        const finalText = rain[Math.floor(Math.random() * rain.length)];
        speech.text = finalText;
    }

    if (message.includes('weather')) {
        const finalText = weather[Math.floor(Math.random() * weather.length)];
        speech.text = finalText;
    }

    speech.volume = 1;
    speech.rate =1;
    speech.pitch = 1;

    window.speechSynthesis.speak(speech);
}
