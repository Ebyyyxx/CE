<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>To The Love Of My Life ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root{
    --pink:#ff4f81;
    --dark:#1a1a1a;
    --light:#fff5f7;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:'Poppins',sans-serif;
    overflow-x:hidden;
    background:linear-gradient(135deg,#ff5f8f,#ff8db1,#ffd1dc);
    color:white;
}

canvas{
    position:fixed;
    inset:0;
    z-index:-1;
}

.hero{
    min-height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    padding:30px;
}

.hero h1{
    font-family:'Great Vibes',cursive;
    font-size:5rem;
    margin-bottom:20px;
    animation:fadeIn 2s ease;
}

.hero p{
    max-width:700px;
    font-size:1.2rem;
    line-height:1.8;
}

.btn{
    margin-top:30px;
    padding:15px 35px;
    border:none;
    border-radius:999px;
    background:white;
    color:var(--pink);
    font-weight:bold;
    cursor:pointer;
    transition:.3s;
}

.btn:hover{
    transform:scale(1.08);
}

.section{
    padding:100px 20px;
    text-align:center;
}

.section h2{
    font-size:3rem;
    margin-bottom:30px;
    font-family:'Great Vibes',cursive;
}

.timer{
    display:flex;
    justify-content:center;
    gap:20px;
    flex-wrap:wrap;
}

.card{
    background:rgba(255,255,255,.15);
    backdrop-filter:blur(12px);
    padding:20px;
    border-radius:20px;
    min-width:120px;
}

.card span{
    display:block;
    font-size:2rem;
    font-weight:bold;
}

.gallery{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
    max-width:1100px;
    margin:auto;
}

.gallery img{
    width:100%;
    height:300px;
    object-fit:cover;
    border-radius:20px;
    transition:.4s;
}

.gallery img:hover{
    transform:scale(1.05);
}

.letter{
    max-width:700px;
    margin:auto;
    background:rgba(255,255,255,.15);
    backdrop-filter:blur(12px);
    padding:40px;
    border-radius:25px;
    line-height:2;
}

.surprise{
    margin-top:40px;
}

.hidden{
    display:none;
}

footer{
    text-align:center;
    padding:40px;
}

@keyframes fadeIn{
    from{
        opacity:0;
        transform:translateY(30px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}
</style>
</head>
<body>

<canvas id="hearts"></canvas>

<section class="hero">
    <h1>For My Beautiful Love ❤️</h1>

    <p>
        Every moment with you feels like a dream.
        This little website is just a tiny reminder
        of how much you mean to me.
    </p>

    <button class="btn" onclick="scrollToLetter()">
        Open My Heart 💌
    </button>
</section>

<section class="section">
    <h2>Our Journey Together</h2>

    <div class="timer">
        <div class="card">
            <span id="days">0</span>
            Days
        </div>

        <div class="card">
            <span id="hours">0</span>
            Hours
        </div>

        <div class="card">
            <span id="minutes">0</span>
            Minutes
        </div>

        <div class="card">
            <span id="seconds">0</span>
            Seconds
        </div>
    </div>
</section>

<section class="section" id="letterSection">
    <h2>My Love Letter</h2>

    <div class="letter">
        My dearest,

        <br><br>

        Before I met you, I never knew someone could
        completely change the way I see the world.

        You are my happiness on difficult days,
        my smile when life gets busy,
        and my favorite part of every single day.

        <br><br>

        Thank you for your love,
        your kindness,
        your patience,
        and for simply being you.

        <br><br>

        I love you today,
        tomorrow,
        and forever. ❤️
    </div>
</section>

<section class="section">
    <h2>Our Memories</h2>

    <div class="gallery">
        <img src="photo1.jpg">
        <img src="photo2.jpg">
        <img src="photo3.jpg">
        <img src="photo4.jpg">
    </div>
</section>

<section class="section">
    <h2>One Last Thing...</h2>

    <button class="btn" onclick="showSurprise()">
        Click For A Surprise 🌹
    </button>

    <div id="surprise" class="surprise hidden">
        <h1 style="font-family:Great Vibes;font-size:5rem">
            I Love You Forever ❤️
        </h1>

        <p style="font-size:1.3rem">
            Thank you for being the most beautiful part of my life.
        </p>
    </div>
</section>

<footer>
    Made with ❤️ just for you.
</footer>

<script>
// CHANGE THIS DATE
const startDate = new Date("2024-01-01");

function updateTimer(){
    const now = new Date();
    const diff = now - startDate;

    const days = Math.floor(diff/(1000*60*60*24));
    const hours = Math.floor(diff/(1000*60*60)%24);
    const minutes = Math.floor(diff/(1000*60)%60);
    const seconds = Math.floor(diff/1000%60);

    document.getElementById("days").textContent=days;
    document.getElementById("hours").textContent=hours;
    document.getElementById("minutes").textContent=minutes;
    document.getElementById("seconds").textContent=seconds;
}

setInterval(updateTimer,1000);
updateTimer();

function scrollToLetter(){
    document.getElementById("letterSection")
    .scrollIntoView({behavior:"smooth"});
}

function showSurprise(){
    document.getElementById("surprise")
    .classList.remove("hidden");
}

// Heart animation
const canvas = document.getElementById("hearts");
const ctx = canvas.getContext("2d");

canvas.width = innerWidth;
canvas.height = innerHeight;

let hearts=[];

for(let i=0;i<80;i++){
    hearts.push({
        x:Math.random()*canvas.width,
        y:Math.random()*canvas.height,
        size:Math.random()*15+5,
        speed:Math.random()*1+0.5
    });
}

function animate(){
    ctx.clearRect(0,0,canvas.width,canvas.height);

    hearts.forEach(h=>{
        ctx.fillStyle="rgba(255,255,255,.6)";
        ctx.font=h.size+"px Arial";
        ctx.fillText("❤",h.x,h.y);

        h.y-=h.speed;

        if(h.y<0){
            h.y=canvas.height;
            h.x=Math.random()*canvas.width;
        }
    });

    requestAnimationFrame(animate);
}

animate();

window.addEventListener("resize",()=>{
    canvas.width=innerWidth;
    canvas.height=innerHeight;
});
</script>

</body>
</html>
