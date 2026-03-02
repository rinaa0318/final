[gif.html](https://github.com/user-attachments/files/25682630/gif.html)
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For My Husband ❤️</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap');

body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    text-align: center;
    color: white;
    overflow-x: hidden;
    background: linear-gradient(to right,#141e30,#243b55);
    transition: background 1s ease;
}

/* Glass Navigation */
nav {
    backdrop-filter: blur(15px);
    background: rgba(255,255,255,0.1);
    padding: 15px;
    position: sticky;
    top: 0;
    z-index: 10;
}

nav button {
    margin: 5px;
    padding: 10px 22px;
    border: none;
    border-radius: 25px;
    background: rgba(255,255,255,0.2);
    color: white;
    cursor: pointer;
    transition: 0.3s;
    font-weight: 500;
}
nav button:hover {
    background: #ff4b8b;
    box-shadow: 0 0 15px #ff4b8b;
}

/* Sections */
.section {
    display: none;
    padding: 80px 20px;
    animation: fadeIn 1.2s ease;
}
.active { display: block; }

@keyframes fadeIn {
    from {opacity:0; transform:translateY(20px);}
    to {opacity:1; transform:translateY(0);}
}

/* Premium Glow */
.glow {
    font-size: 48px;
    font-weight: 700;
    background: linear-gradient(45deg,#00dbde,#fc00ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: glow 3s infinite alternate;
}
@keyframes glow {
    from { text-shadow: 0 0 10px #00dbde; }
    to { text-shadow: 0 0 25px #fc00ff; }
}

/* Letter */
.typing {
    max-width: 750px;
    margin: auto;
    font-size: 22px;
    line-height: 1.8;
    background: rgba(255,255,255,0.1);
    padding: 30px;
    border-radius: 20px;
    backdrop-filter: blur(10px);
}

.final-message {
    opacity: 0;
    font-size: 30px;
    margin-top: 40px;
    animation: fadeMessage 4s ease forwards;
    animation-delay: 4s;
}
@keyframes fadeMessage { to { opacity:1; } }

/* Gallery */
.gallery img {
    width: 250px;
    margin: 15px;
    border-radius: 20px;
    transition: 0.4s;
    box-shadow: 0 10px 25px rgba(0,0,0,0.4);
}
.gallery img:hover { transform: scale(1.08); }

/* CENTER LOVE BURST */
.love-burst {
    position: fixed;
    left: 50%;
    top: 50%;
    font-size: 45px;
    font-weight: bold;
    color: #ff4b8b;
    pointer-events: none;
    animation: centerBurst 2s ease-out forwards;
}

@keyframes centerBurst {
    0% { 
        transform: translate(-50%, -50%) scale(0.5);
        opacity:1;
    }
    100% { 
        transform: translate(-50%, -200%) scale(2.5);
        opacity:0;
    }
}

/* Floating Hearts */
.heart {
    position: fixed;
    bottom: -10px;
    font-size: 20px;
    animation: floatUp 6s linear infinite;
}
@keyframes floatUp {
    0% {transform: translateY(0); opacity:1;}
    100% {transform: translateY(-900px); opacity:0;}
}

/* Countdown */
#timer {
    font-size: 32px;
    font-weight: bold;
    margin-top: 20px;
}
</style>
</head>

<body>

<nav>
    <button onclick="showSection('home','#141e30,#243b55')">Home</button>
    <button onclick="showSection('letter','#42275a,#734b6d', true)">Letter</button>
    <button onclick="showSection('gallery','#ff512f,#dd2476')">Memories</button>
    <button onclick="showSection('music','#1d4350,#a43931')">Songs</button>
    <button onclick="showSection('countdown','#0f2027,#2c5364')">Countdown</button>
</nav>

<div id="home" class="section active">
    <h1 class="glow">To My Forever 💙</h1>
    <p>Click anywhere on the screen 💕</p>
</div>

<div id="letter" class="section">
    <h1>My Love 💌</h1>
    <div class="typing">
        Oru kutty letter unakaga .... 
        I always love you the same as i love you now,
        you make my life special thank you very much to choose me. 
        Un dream ellamey ennala mudinja alavuku nadathi veipen. 
        From the moment you came into my life, you became my everything.
    </div>
    <div class="final-message">💬 I’m lucky to be your wife.</div>
</div>

<div id="gallery" class="section">
    <h1>Our Beautiful Memories 📸</h1>
    <div class="gallery">
        <img src="images/first photo.jpg" alt="Memory 1">
        <img src="images/our fav.jpg" alt="Memory 2">
        <img src="images/last.jpg" alt="Memory 3">
    </div>
    </div>
</div>

<div id="music" class="section">
    <h1>Our Love Songs 🎵</h1>
    
      <div style="margin-bottom:25px;">
        <button onclick="playSong('kadhal-aasai.mp3')">💖 Kadhal Aasai</button>
        <button onclick="playSong('agayam-theepiditha.mp3')">🔥 Agayam Theepiditha</button>
        <button onclick="playSong('nanbiyey.mp3')">💕 Nanbiyey</button>
    </div>

    <audio id="bgMusic" controls loop style="width:320px;"></audio>
<script>
function playSong(songFile) {
    const music = document.getElementById("bgMusic");
    
    // Stop current song if playing
    music.pause();
    
    // Set the new song
    music.src = songFile;
    
    // Load and play
    music.load();
    music.play().catch((err)=>{
        console.log("Playback blocked:", err);
        alert("Click anywhere first to enable music playback!");
    });
}
</script>
</div>

<div id="countdown" class="section">
    <h1>Countdown to August 10 💕</h1>
    <h2 id="timer"></h2>
</div>

<script>
function showSection(id, gradient, playMusic=false) {
    var sections = document.querySelectorAll(".section");
    sections.forEach(sec => sec.classList.remove("active"));
    document.getElementById(id).classList.add("active");
    document.body.style.background = "linear-gradient(to right," + gradient + ")";
    if(playMusic){
        let music = document.getElementById("bgMusic");
        music.volume = 0;
        music.play();
        let fade = setInterval(function(){
            if(music.volume < 1){ music.volume += 0.05; } 
            else { clearInterval(fade); }
        },200);
    }
}

/* Countdown */
var anniversary = new Date("August 10, 2026 00:00:00").getTime();
setInterval(function() {
    var now = new Date().getTime();
    var distance = anniversary - now;
    var days = Math.floor(distance / (1000*60*60*24));
    var hours = Math.floor((distance % (1000*60*60*24))/(1000*60*60));
    var minutes = Math.floor((distance % (1000*60*60))/(1000*60));
    var seconds = Math.floor((distance % (1000*60))/1000);
    document.getElementById("timer").innerHTML =
        days+"d "+hours+"h "+minutes+"m "+seconds+"s ";
},1000);

/* Floating hearts */
function createHeart() {
    var heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    document.body.appendChild(heart);
    setTimeout(()=>{heart.remove();},6000);
}
setInterval(createHeart,700);

/* CENTER I LOVE YOU BURST */
document.addEventListener("click", function(){
    var love = document.createElement("div");
    love.className = "love-burst";
    love.innerHTML = "I LOVE YOU 💙";
    document.body.appendChild(love);
    setTimeout(()=>{love.remove();},2000);
});
</script>

</body>
</html>
