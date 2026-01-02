# Hanno255.github.io
Dieses Projekt ist eine interaktive Webseite zum Spielen von verschiedenen Musikinstrumenten mit veränderbaren Sound-Einstellungen.
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>change the world with music</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>change the world with music 🎶</h1>
    
    <nav>
        <ul>
            <li><a href="#keyboard-display" data-instrument="keyboard">Keyboard</a></li>
            <li><a href="#guitar-display" data-instrument="guitar">Gitarre</a></li>
            <li><a href="#trumpet-display" data-instrument="trumpet">Trompete</a></li>
            <li><a href="#sound-settings-display" data-instrument="sounds">Sounds</a></li>
        </ul>
    </nav>
    
    <div id="note-display"></div>
    
    <div class="main-container">
        
        <div id="keyboard-display" class="instrument-display">
            <div class="keyboard" id="keyboard">
                <div class="key-wrapper"><div class="key" data-note="C4"></div><div class="key-black" data-note="C#4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="D4"></div><div class="key-black" data-note="D#4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="E4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="F4"></div><div class="key-black" data-note="F#4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="G4"></div><div class="key-black" data-note="G#4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="A4"></div><div class="key-black" data-note="A#4"></div></div>
                <div class="key-wrapper"><div class="key" data-note="H4"></div></div>
                
                <div class="key-wrapper"><div class="key" data-note="C5"></div><div class="key-black" data-note="C#5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="D5"></div><div class="key-black" data-note="D#5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="E5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="F5"></div><div class="key-black" data-note="F#5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="G5"></div><div class="key-black" data-note="G#5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="A5"></div><div class="key-black" data-note="A#5"></div></div>
                <div class="key-wrapper"><div class="key" data-note="H5"></div></div>
                
                <div class="key-wrapper"><div class="key" data-note="C6"></div></div>
            </div>
        </div>

        <div id="guitar-display" class="instrument-display">
            <h2>Akustische Gitarre</h2>
            <div class="fretboard">
                <div class="string" data-note="Low E" data-freq="82.41" data-string-id="1"></div>
                <div class="string" data-note="A" data-freq="110.00" data-string-id="2"></div>
                <div class="string" data-note="D" data-freq="146.83" data-string-id="3"></div>
                <div class="string" data-note="G" data-freq="196.00" data-string-id="4"></div>
                <div class="string" data-note="B" data-freq="246.94" data-string-id="5"></div> 
                <div class="string" data-note="High E" data-freq="329.63" data-string-id="6"></div>
            </div>
        </div>
        
        <div id="trumpet-display" class="instrument-display">
             <h2>Trompete (Ventile)</h2>
             <div class="valve-container">
                 <div class="valve-key" data-valve="1"></div>
                 <div class="valve-key" data-valve="2"></div>
                 <div class="valve-key" data-valve="3"></div>
             </div>
        </div>
        
        <div id="sound-settings-display" class="instrument-display">
            <h2>Sound-Einstellungen</h2>
            <p>Wähle die Wellenform für Keyboard und Trompete:</p>
            <div class="waveform-selection">
                <div class="waveform-option active" data-waveform="sine">Sinus (Sanft/Klar)</div>
                <div class="waveform-option" data-waveform="sawtooth">Sägezahn (Hell/Blech)</div>
                <div class="waveform-option" data-waveform="square">Rechteck (Digital/Hohl)</div>
                <div class="waveform-option" data-waveform="triangle">Dreieck (Flötenartig)</div>
            </div>
        </div>

        <div class="controls-area">
            <div class="volume-control-box">
                <strong>Lautstärke:</strong>
                <input type="range" id="volume-slider" min="0" max="1" step="0.01" value="0.5">
                <span id="volume-value">50%</span>
            </div>
            
            <div class="waveform-wrapper">
                <canvas id="waveform-display" width="350" height="120"></canvas>
                <p style="font-size: 0.9em; margin-top: 0;">Audio-Wellenform</p>
            </div>
            
            <div class="FUCHS">
                <img src="fox-vector-icon-illustration-silhouette-600nw-2513168833-removebg-preview.png" alt="Fuchs">
            </div>
            <div class="SPRECHBLASE">
                Herzlich Willkommen auf dieser Webseite!
                <br> <br>
                <button>&times;</button>
            </div>
        </div>

    </div>
    
    <div class="impressum">
        <h3>Impressum</h3>
        <p>
            Verantwortlich:<br>
            Leif Hühne [&] Hanno Reuter<br>
            Kurs: Internettechnologie 2<br>
            Semester: Wintersemester 2025/2026
        </p>
    </div>

    <script src="data.js"></script>
    <script src="audio-engine.js"></script>
    <script src="keyboard.js"></script>
    <script src="guitar.js"></script>
    <script src="trumpet.js"></script>
    <script src="ui.js"></script>

</body>
</html>
/*CSS*/
body {
    font-family: Arial, sans-serif;
    background-color: wheat;
    color: #333;
    margin: 0;
    padding: 20px;
    transition: background-color 0.5s ease-out; 
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
}

h1 {
    color: #000;
    margin-bottom: 20px;
}

/*Navigation*/
nav ul {
    list-style: none;
    padding: 0;
    margin-bottom: 30px;
    display: flex;
    gap: 20px;
}

nav a {
    text-decoration: none;
    color: #d2691e;
    font-weight: bold;
    padding: 5px 10px;
    border-bottom: 2px solid transparent;
    transition: border-bottom 0.2s;
}

nav a:hover {
    border-bottom: 2px solid #d2691e;
}


#note-display {
    font-size: 4.5em;
    font-weight: bold;
    color: #d2691e;
    min-height: 1.4em;
    margin-bottom: 35px;
    transition: color 0.1s;
    text-align: center;
}

.main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
}
.BOX {
    position: relative;
    height: 300px;
    width: 400px;
}

.FUCHS {
    position: absolute;
    top: 10px;
    left: 10px;
    height: 300px;
    width: 300px;
}
.FUCHS img{
    width: 100%;
    height: 100%;
    object-fit: contain;
}
.SPRECHBLASE {
    position: absolute;
    padding: 20px;
    top: 10%;
    left: 23%;
    max-width: 150px;
    transform: translate(-50%, -50%);
    border-radius: 30px 30px 30px 0;
    background-color: white;
    text-align: center;
    visibility: hidden;
}        
.SICHTBAR {
    visibility: visible
}
/*Instrumente*/
.instrument-display {
    display: none; /*verstecken */
    flex-direction: column;
    align-items: center;
    margin-bottom: 60px; 
}

/*Keyboard sichtbar*/
.instrument-display:first-of-type {
    display: flex; 
}

/*Aufbau Keyboard*/
.keyboard {
    display: flex;
    position: relative;
    background: #444;
    padding: 30px;
    border-radius: 15px;
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.7);
    transform: scale(1.0); 
    transform-origin: center;
}

.key-wrapper {
    display: block;
    position: relative;
}

.key {
    width: 65px; 
    height: 350px;
    background-color: white;
    border: 1px solid black;
    border-radius: 0 0 8px 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
    cursor: pointer;
    transition: background-color 0.1s;
    position: relative;
    z-index: 1;
}

.key-black {
    width: 40px;
    height: 220px;
    background-color: black;
    position: absolute; 
    top: 0; 
    left: 45px; 
    margin: 0; 
    z-index: 2;
    border: 1px solid black;
    border-radius: 0 0 6px 6px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.9);
}

.key-wrapper:nth-child(3) .key-black, 
.key-wrapper:nth-child(7) .key-black,
.key-wrapper:nth-child(10) .key-black,
.key-wrapper:nth-child(14) .key-black { 
    display: none; 
}

.key-active {
    background-color: #ff4500 !important;
    transform: translateY(4px);
    box-shadow: none !important;
}


/*Gitarre Aufbau*/
#guitar-display {
    width: 600px;
    height: 300px;
    background: #a0522d; 
    border-radius: 10px;
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.5);
    position: relative;
    padding: 20px;
    box-sizing: border-box;
    justify-content: center;
}

.fretboard {
    width: 80%;
    height: 250px;
    background: #4e3629; 
    position: relative;
    border-radius: 5px;
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.5);
    margin-top: 20px;
}

.string {
    position: absolute;
    left: 0;
    right: 0;
    height: 4px; 
    background: silver;
    cursor: pointer;
    transition: transform 0.1s;
    z-index: 10;
}

.string:hover {
    background: gold;
}

.string-active {
    transform: scaleY(1.5);
    background: #ff4500 !important;
}

.string:nth-child(1) { top: 15%; height: 6px; } 
.string:nth-child(2) { top: 30%; height: 5px; }
.string:nth-child(3) { top: 45%; height: 4px; }
.string:nth-child(4) { top: 60%; height: 3px; }
.string:nth-child(5) { top: 75%; height: 2px; }
.string:nth-child(6) { top: 90%; height: 1px; } 


/*Trompete Aufbau*/
.valve-container {
    width: 300px; 
    height: 150px; 
    display: flex;
    flex-direction: row; 
    align-items: flex-start; 
    justify-content: space-around; 
    
    padding: 20px;
    padding-top: 50px; 
    box-sizing: border-box;
    
    background: #c0c0c0; 
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5); 
    position: relative;
}

.valve-key {
    width: 60px;
    height: 60px;
    border-radius: 50%; 
    background-color: #ffd700; 
    border: 3px solid #b8860b; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4), 
                 inset 0 2px 4px rgba(255, 255, 255, 0.6); 
    cursor: pointer;
    transition: all 0.1s;
    position: relative;
    z-index: 10;
    margin-top: -30px; 
}
    
/*Ventil drücken*/
.valve-key-active {
    background-color: #ff4500 !important; 
    transform: translateY(3px); 
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.4) !important; 
}

/*Sound Settings*/
#sound-settings-display {
    background: #f0f0f0;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    width: 500px;
}

.waveform-selection {
    display: flex;
    gap: 20px;
    justify-content: center;
    margin-top: 20px;
}

.waveform-option {
    padding: 10px 15px;
    border: 2px solid #ccc;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
    transition: background-color 0.2s, border-color 0.2s;
    text-align: center;
}

.waveform-option:hover {
    border-color: #d2691e;
}

.waveform-option.active {
    background-color: #d2691e;
    color: white;
    border-color: #d2691e;
}

/*Lautstärke und wellen*/
.controls-area {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 50px;
    max-width: 1000px;
    width: 100%;
    margin-bottom: 40px; 
}


.volume-control-box {
    background: #eee;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 200px;
    height: 120px; 
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

#volume-value {
    cursor: pointer;
    text-decoration: underline;
    font-weight: bold;
    color: #d2691e;
}

.volume-input {
    width: 50px; 
    text-align: center;
    border: 1px solid #d2691e;
    padding: 2px;
    font-weight: bold;
}

#volume-slider {
    width: 180px; 
    height: 12px;
    -webkit-appearance: none;
    appearance: none;
    background: #ddd;
    border-radius: 6px;
    cursor: pointer;
    outline: none;
    margin-bottom: 15px;
}

#volume-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 24px;
    height: 24px;
    background: #e96;
    border-radius: 50%;
    cursor: pointer;
}

#waveform-display {
    border: 1px solid #000;
    background-color: #f0f0f0;
    border-radius: 5px;
    box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
    width: 350px;
    height: 120px; 
}

.waveform-wrapper {
    text-align: center;
}

/*Impressum*/
.impressum {
    margin-top: 50px;
    padding-top: 20px;
    border-top: 1px solid #ccc;
    font-size: 0.8em;
    color: #666;
    text-align: center;
}
/*Die Sprüche für die Sprechblase.
Warum separat? Wenn wir die Frequenzen ändern wollen, muss man nicht im komplizierten Audio-Code suchen.*/
const fuchsTexte = {
    keyboard: "Hier kannst du Keyboard spielen!",
    guitar: "Probier es mal mit der Gitarre!",
    trumpet: "Jetzt ist die Trompete dran!",
    sounds: "Probiere hier verschiedene Sounds aus!"
};

/*Frequenzen Keyboard*/
/*Eine riesige Liste, die Notennamen (z. B. "C4") in Frequenzen ("261.63") übersetzt.*/
const noteFrequencies = {
    'C4': 261.63, 'C#4': 277.18,
    'D4': 293.66, 'D#4': 311.13,
    'E4': 329.63,
    'F4': 349.23, 'F#4': 369.99,
    'G4': 392.00, 'G#4': 415.30,
    'A4': 440.00, 'A#4': 466.16,
    'H4': 493.88,
    'C5': 523.25, 'C#5': 554.37,
    'D5': 587.33, 'D#5': 622.25,
    'E5': 659.26,
    'F5': 698.46, 'F#5': 739.99,
    'G5': 783.99, 'G#5': 830.61,
    'A5': 880.00, 'A#5': 932.33,
    'H5': 987.77,
    'C6': 1046.50
};

/*Frequenzen Trompete*/
/*Die Logik für die Ventile (welche Kombination ergibt welche Frequenz).*/
const trumpetFrequencies = {
    '0': 466.16, 
    '2': 440.00, 
    '1': 415.30, 
    '12': 392.00, 
    '23': 369.99, 
    '13': 349.23, 
    '123': 329.63, 
    '3': 311.13,  
};
/* Globale Variablen für Audio-Status */
/*Globale Variablen: Hier definieren wir let audioCtx, let analyser, let mainGainNode. Da sie hier "draußen" stehen, können alle anderen Dateien darauf zugreifen.*/
/*Die Web Audio API wird in diesem Abschnitt gestartet.*/
let audioCtx;
let mainGainNode;
let analyser;
const activeOscillators = {};   
const activeGuitarStrings = {}; 
const valveState = { '1': false, '2': false, '3': false }; 
const activeTrumpetOscillator = {}; 
let currentWaveform = 'sine';

/* UI Elemente Referenzen */
const volumeSlider = document.getElementById('volume-slider');
const volumeValueDisplay = document.getElementById('volume-value');
const noteDisplay = document.getElementById('note-display');
const canvas = document.getElementById('waveform-display');
canvas.width = 350; 
canvas.height = 120;
const canvasCtx = canvas.getContext('2d');

/*Audio beim Klicken*/
/* Diese Funktion startet den AudioContext. Sie muss beim ersten Klick aufgerufen werden (wegen der Browser-Sicherheitsrichtlinien).*/
function initAudio() {
    if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        mainGainNode = audioCtx.createGain();
        mainGainNode.connect(audioCtx.destination);
        
        analyser = audioCtx.createAnalyser();
        analyser.fftSize = 2048;    
        mainGainNode.connect(analyser); 
        
        mainGainNode.gain.value = volumeSlider.value;
        updateVolumeDisplay(volumeSlider.value);    
/*Hier werden die Wellenformen grafisch dargestellt*/
        drawWaveform();
        
        noteDisplay.textContent = 'KEYBOARD'; 
    }
}

/*Lautstärke Funktion*/
function updateVolumeDisplay(value) {
    volumeValueDisplay.textContent = `${Math.round(value * 100)}%`; 
    volumeSlider.value = value;
}
/*Regelt die Lautstärke für alles.*/
function setVolume(newVolume) {
    initAudio();
    if (mainGainNode) {
        mainGainNode.gain.setValueAtTime(newVolume, audioCtx.currentTime);
    }
    updateVolumeDisplay(newVolume);
}
/*Die Endlosschleife (requestAnimationFrame). Sie holt sich 60-mal pro Sekunde Daten vom analyser und malt die rote Linie auf das Canvas.*/
function drawWaveform() {
    requestAnimationFrame(drawWaveform);
    if (!analyser) return;

    const bufferLength = analyser.fftSize;
    const dataArray = new Uint8Array(bufferLength);
    
    analyser.getByteTimeDomainData(dataArray);

    canvasCtx.fillStyle = '#f0f0f0';    
    canvasCtx.fillRect(0, 0, canvas.width, canvas.height);

    canvasCtx.lineWidth = 2;
    canvasCtx.strokeStyle = 'rgb(200, 0, 0)';   

    canvasCtx.beginPath();

    const sliceWidth = canvas.width * 1.0 / bufferLength;
    let x = 0;
    let maxAmplitude = 0;

    for(let i = 0; i < bufferLength; i++) {
        const v = dataArray[i] / 128.0;
        const y = v * canvas.height / 2;
        
        maxAmplitude = Math.max(maxAmplitude, Math.abs(dataArray[i] - 128));

        if(i === 0) {
            canvasCtx.moveTo(x, y);
        } else {
            canvasCtx.lineTo(x, y);
        }

        x += sliceWidth;
    }

    if (maxAmplitude < 5) { 
        canvasCtx.beginPath();
        canvasCtx.moveTo(0, canvas.height / 2);
        canvasCtx.lineTo(canvas.width, canvas.height / 2);
    }

    canvasCtx.lineTo(canvas.width, canvas.height/2);
    canvasCtx.stroke();
}

// Initialer Listener für AudioContext (Autoplay Policy)
document.addEventListener('mousedown', initAudio, { once: true });
document.addEventListener('touchstart', initAudio, { once: true });
/*Erstellt einen Oszillator (Standard-Wellengenerator).
Setzt die Frequenz basierend auf der gedrückten Taste.
Verbindet ihn mit dem mainGainNode.
Speichert ihn in activeOscillators (damit wir ihn später wiederfinden und stoppen können).*/
function playNote(keyElement) {
    initAudio();    
    const note = keyElement.dataset.note;
    const frequency = noteFrequencies[note];

    if (!frequency || activeOscillators[note]) return;  

    const oscillator = audioCtx.createOscillator();
    
    oscillator.type = currentWaveform;
    oscillator.frequency.setValueAtTime(frequency, audioCtx.currentTime);

    oscillator.connect(mainGainNode);
    oscillator.start();

    activeOscillators[note] = oscillator;
    keyElement.classList.add('key-active');
    
    noteDisplay.textContent = note;
}

function stopNote(keyElement) {
    const note = keyElement.dataset.note;
    const oscillator = activeOscillators[note];
    
    if (oscillator) {
        oscillator.stop(audioCtx.currentTime + 0.05);   
        delete activeOscillators[note];
        keyElement.classList.remove('key-active');

        if (Object.keys(activeOscillators).length === 0 && Object.keys(activeGuitarStrings).length === 0 && !activeTrumpetOscillator.osc) {
            noteDisplay.textContent = 'KEYBOARD'; 
        }
    }
}

/*Tastenfunktionen Event Listener*/
/*Hier wird mousedown (Maus), touchstart (Handy) und mouseup überwacht, um Töne zu starten und zu stoppen.*/
document.querySelectorAll('.key, .key-black').forEach(key => {
    key.addEventListener('mousedown', (e) => {
        e.preventDefault(); 
        playNote(key);
    });
    
    key.addEventListener('mouseup', () => stopNote(key));   
    
    key.addEventListener('mouseleave', (e) => {
        if (activeOscillators[key.dataset.note] && e.buttons !== 1) {
            stopNote(key);
        }
    });
    key.addEventListener('touchstart', (e) => {
        e.preventDefault();
        playNote(key);
    });
    key.addEventListener('touchend', (e) => {
        e.preventDefault();
        stopNote(key);
    });
});
/*Erzeugt Rauschen (Noise Buffer) für den "Anschlag".
Nutzt einen DelayNode (Verzögerung) für die Tonhöhe.
Nutzt Feedback, damit der Ton ausklingt wie eine Saite.
Unterschied: Ein Keyboard-Ton bleibt an, solange man drückt. Ein Gitarren-Ton klingt von alleine aus (setTimeout), auch wenn man loslässt.*/
function playGuitarString(stringElement) {
    initAudio();
    const note = stringElement.dataset.note;
    const frequency = parseFloat(stringElement.dataset.freq);

    if (activeGuitarStrings[note]) return; 

    const noise = audioCtx.createBufferSource();
    const bufferSize = audioCtx.sampleRate * 0.5; 
    const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
    const output = buffer.getChannelData(0);
    for (let i = 0; i < bufferSize; i++) {
        output[i] = Math.random() * 2 - 1;  
    }
    noise.buffer = buffer;

    const delay = audioCtx.createDelay(1.0); 
    delay.delayTime.setValueAtTime(1 / frequency, audioCtx.currentTime);    

    const feedbackGain = audioCtx.createGain();
    feedbackGain.gain.setValueAtTime(0.998, audioCtx.currentTime);  

    noise.connect(delay);
    delay.connect(feedbackGain);
    feedbackGain.connect(delay); 
    
    feedbackGain.connect(mainGainNode);

    noise.start(audioCtx.currentTime);
    noise.stop(audioCtx.currentTime + 0.01);    

    activeGuitarStrings[note] = { delay, feedbackGain, noise };
    stringElement.classList.add('string-active');
    noteDisplay.textContent = 'Gitarre: ' + note + ' (' + frequency.toFixed(2) + 'Hz)';

    setTimeout(() => {
        feedbackGain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 1.0); 
        
        setTimeout(() => {
            delay.disconnect();
            feedbackGain.disconnect();
            noise.disconnect();
            delete activeGuitarStrings[note];
            stringElement.classList.remove('string-active');
            if (Object.keys(activeOscillators).length === 0 && Object.keys(activeGuitarStrings).length === 0 && !activeTrumpetOscillator.osc) {
                noteDisplay.textContent = 'GITARRE'; 
            }
        }, 1000); 

    }, 4000); 
}

/*Funktion Gitarrensaiten Event Listener*/
document.querySelectorAll('.string').forEach(stringElement => {
    stringElement.addEventListener('mousedown', (e) => {
        e.preventDefault(); 
        if (!activeGuitarStrings[stringElement.dataset.note]) {
            playGuitarString(stringElement);
        }
    });
    stringElement.addEventListener('touchstart', (e) => {
        e.preventDefault();
        if (!activeGuitarStrings[stringElement.dataset.note]) {
            playGuitarString(stringElement);
        }
    });
});
/*valve state: Merkt sich: Ist Ventil 1 gedrückt? Ventil 2?*/
/*Baut einen Code (z. B. "13" für Ventil 1+3).*/
function getCurrentValveKey() {
    let key = '';
    if (valveState['1']) key += '1';    
    if (valveState['2']) key += '2';
    if (valveState['3']) key += '3';
    return key || '0'; 
}
/* Schaut in trumpetFrequencies nach, welcher Ton zu diesem Code gehört, und spielt ihn (ähnlich wie das Keyboard, aber mit nur einem Oszillator gleichzeitig, weil eine Trompete nur einen Ton spielen kann)*/
function playTrumpetTone() {
    const valveKey = getCurrentValveKey();
    const frequency = trumpetFrequencies[valveKey];
    const noteName = Object.keys(noteFrequencies).find(key => Math.abs(noteFrequencies[key] - frequency) < 1.0) || 'N/A';
    const displayNote = `Trompete: ${noteName} (${valveKey} gedrückt)`;

    if (!frequency) {
        noteDisplay.textContent = 'Unbekannte Kombination';
        return;
    }

    if (activeTrumpetOscillator.osc) {
            activeTrumpetOscillator.osc.stop(audioCtx.currentTime);
            delete activeTrumpetOscillator.osc;
    }

    const oscillator = audioCtx.createOscillator();
    
    oscillator.type = currentWaveform; 
    oscillator.frequency.setValueAtTime(frequency, audioCtx.currentTime);

    oscillator.connect(mainGainNode);
    oscillator.start();

    activeTrumpetOscillator.osc = oscillator;
    noteDisplay.textContent = displayNote;
}

function stopTrumpetTone() {
    if (activeTrumpetOscillator.osc) {
        activeTrumpetOscillator.osc.stop(audioCtx.currentTime + 0.05); 
        delete activeTrumpetOscillator.osc;
    }
    noteDisplay.textContent = 'TROMPETE'; 
}

/*Trompete Event Listener*/
document.querySelectorAll('.valve-key').forEach(valve => {
    const valveId = valve.dataset.valve;
    
    const handleValvePress = (e) => {
            initAudio();
            e.preventDefault();
            if (!valve.classList.contains('valve-key-active')) {
                valveState[valveId] = true;
                valve.classList.add('valve-key-active');
                playTrumpetTone();
            }
    };
    
    const handleValveRelease = (e) => {
            if (e.type !== 'mouseleave') {
                e.preventDefault();
            }
            
            if (!valveState[valveId]) return;
            
            valveState[valveId] = false;
            valve.classList.remove('valve-key-active');
            
            const newKey = getCurrentValveKey();
            
            if (newKey === '0') {
                stopTrumpetTone();
            } else {
                playTrumpetTone();
            }
    };
    
    valve.addEventListener('mousedown', handleValvePress);
    valve.addEventListener('touchstart', handleValvePress);
    valve.addEventListener('mouseup', handleValveRelease);  
    valve.addEventListener('touchend', handleValveRelease);
    
    valve.addEventListener('mouseleave', (e) => {
        if (valveState[valveId]) { 
            handleValveRelease(e);
        }
    });
});
/*Hier passiert alles, was nicht direkt Sound macht, aber die Seite steuert.
Navigation: Wenn man auf "Gitarre" klickt:
Verstecke alle anderen Divs (display: none).
Zeige das Gitarren-Div (display: flex).
Wichtig: Rufe stopAllSounds() auf (damit kein Keyboard-Ton hängen bleibt, wenn man wechselt).
Fuchs (Tone.js Integration):
Hier (oder in einer extra fox.js) liegt der Code für Tone.MembraneSynth.
Beim Klick auf .FUCHS: Spielt den "Plopp"-Sound und zeigt die Sprechblase (classList.add('SICHTBAR')).*/
/*Fuchs Logik*/
document.querySelector(".FUCHS").addEventListener("click",SprechblaseAn);
document.querySelector(".SPRECHBLASE button").addEventListener("click",SprechblaseAus);
function SprechblaseAn() {
    document.querySelector(".SPRECHBLASE").classList.add("SICHTBAR");
}
function SprechblaseAus(event) {
    event.stopPropagation();
    document.querySelector(".SPRECHBLASE").classList.remove("SICHTBAR");
}

/*Soundsettings Umschaltung*/
document.querySelectorAll('.waveform-option').forEach(option => {
    option.addEventListener('click', () => {
        /*Deaktivierung aller anderen*/
        document.querySelectorAll('.waveform-option').forEach(opt => opt.classList.remove('active'));
        
        /*Aktivierung gewählter Töne*/
        option.classList.add('active');
        
        /*Wellenform*/
        currentWaveform = option.dataset.waveform;
        noteDisplay.textContent = `Wellenform: ${currentWaveform.toUpperCase()}`;
        
        /*Aktive Töne nutzen*/
        Object.values(activeOscillators).forEach(osc => osc.stop(audioCtx.currentTime));
        Object.keys(activeOscillators).forEach(key => delete activeOscillators[key]);
        if (activeTrumpetOscillator.osc) {
            stopTrumpetTone();
        }
    });
});

/*Umschaltung Instrumente (Navigation)*/
document.querySelectorAll('nav a').forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        const targetId = link.getAttribute('href');
        const instrumentName = link.dataset.instrument.toUpperCase();
        const instrumentKey = link.dataset.instrument;
        document.querySelector(".SPRECHBLASE").innerHTML =
            fuchsTexte[instrumentKey] + '<br><br><button>&times;</button>';
        document.querySelector(".SPRECHBLASE button")
                .addEventListener("click", SprechblaseAus);
        
        /*Alle Instrumenten-Container verstecken und alle Sounds stoppen*/
        document.querySelectorAll('.instrument-display').forEach(display => {
            display.style.display = 'none';
        });

        /*Alle Töne stoppen*/ 
        Object.values(activeOscillators).forEach(osc => osc.stop(audioCtx.currentTime));
        Object.keys(activeOscillators).forEach(key => delete activeOscillators[key]);
        Object.values(activeGuitarStrings).forEach(obj => {
            obj.delay.disconnect(); obj.feedbackGain.disconnect(); obj.noise.disconnect();
        });
        Object.keys(activeGuitarStrings).forEach(key => delete activeGuitarStrings[key]);
        if (activeTrumpetOscillator.osc) {
            stopTrumpetTone();
            valveState['1'] = valveState['2'] = valveState['3'] = false;
            document.querySelectorAll('.valve-key').forEach(v => v.classList.remove('valve-key-active'));
        }


        /*Ausgewählten Container anzeigen*/
        const targetElement = document.querySelector(targetId);
        if (targetElement) {
                targetElement.style.display = 'flex'; 
        }
        
        /*Aktuelles Instrument in der Note-Anzeige anzeigen*/
        if (instrumentName === 'SOUNDS') {
            noteDisplay.textContent = `Wellenform: ${currentWaveform.toUpperCase()}`;
        } else {
            noteDisplay.textContent = instrumentName;
        }
    });
});

/*Lautstärke Slider Event Listener*/
volumeSlider.addEventListener('input', (e) => {
    const newVolume = parseFloat(e.target.value);
    setVolume(newVolume);
});

/*Lautstärke Text-Input Event Listener*/
volumeValueDisplay.addEventListener('click', () => {
    
    const currentValuePercent = parseInt(volumeValueDisplay.textContent);   
    
    const inputField = document.createElement('input');
    inputField.type = 'number';
    inputField.className = 'volume-input';
    inputField.min = 0;
    inputField.max = 100;
    inputField.value = currentValuePercent;

    volumeValueDisplay.parentNode.replaceChild(inputField, volumeValueDisplay);
    
    inputField.focus();

    function handleInputEnd() {
        let newValuePercent = parseInt(inputField.value);
        
        if (isNaN(newValuePercent) || newValuePercent < 0) {
            newValuePercent = 0;
        } else if (newValuePercent > 100) {
            newValuePercent = 100;
        }
        
        const newVolume = newValuePercent / 100;    
        
        setVolume(newVolume);
        
        inputField.parentNode.replaceChild(volumeValueDisplay, inputField);
    }

    inputField.addEventListener('blur', handleInputEnd);    
    inputField.addEventListener('keydown', (e) => {
        if (e.key === 'Enter') {
            handleInputEnd();
        }
    });
});
