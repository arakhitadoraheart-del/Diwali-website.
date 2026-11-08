<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Diwali ✨</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #080817;
    color: white;
    font-family: Georgia, serif;
    overflow-x: hidden;
    text-align: center;
}

.page {
    display: none;
    min-height: 100vh;
    padding: 35px 20px;
    position: relative;
    overflow: hidden;
}

.page.active {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

h1 {
    color: #ffd36a;
    font-size: clamp(2.2rem, 7vw, 4.5rem);
    text-shadow: 0 0 20px orange;
    margin-bottom: 20px;
}

h2 {
    color: #ffcf70;
    margin: 20px;
}

p {
    font-size: 1.2rem;
    line-height: 1.7;
    max-width: 650px;
}

button {
    background: linear-gradient(45deg, #ff8c00, #ffcf70);
    color: #251000;
    border: none;
    padding: 13px 25px;
    border-radius: 30px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    margin: 15px;
    box-shadow: 0 0 20px #ff9d00;
    transition: .3s;
}

button:hover {
    transform: scale(1.08);
    box-shadow: 0 0 30px orange;
}

/* Hanging lights */

.lights {
    position: absolute;
    top: 0;
    width: 100%;
    display: flex;
    justify-content: space-around;
}

.bulb {
    width: 12px;
    height: 20px;
    background: #ffdb6e;
    border-radius: 50%;
    box-shadow: 0 0 20px #ffb700;
    animation: blink 1s infinite alternate;
}

.bulb:nth-child(even) {
    animation-delay: .5s;
}

@keyframes blink {
    from { opacity: .3; }
    to { opacity: 1; }
}

/* Glowing diya */

.diya {
    font-size: 100px;
    animation: glow 2s infinite alternate;
    margin: 25px;
}

@keyframes glow {
    from {
        filter: drop-shadow(0 0 10px orange);
    }
    to {
        filter: drop-shadow(0 0 35px gold);
    }
}

/* Fireworks */

canvas {
    position: fixed;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 5;
}

/* Floating lanterns */

.lantern {
    position: fixed;
    bottom: -100px;
    font-size: 40px;
    animation: floatUp linear forwards;
    pointer-events: none;
}

@keyframes floatUp {
    to {
        transform: translateY(-120vh) rotate(15deg);
    }
}

/* Cards */

.card {
    background: rgba(255,255,255,.07);
    border: 1px solid rgba(255,215,100,.4);
    border-radius: 20px;
    padding: 30px;
    max-width: 700px;
    box-shadow: 0 0 25px rgba(255,160,0,.15);
}

.wish {
    color: #ffe2a1;
    margin: 15px;
    font-size: 1.3rem;
}

#name {
    background: transparent;
    border: 1px solid orange;
    border-radius: 20px;
    padding: 10px;
    color: white;
    text-align: center;
    margin: 10px;
}
</style>
</head>

<body>

<canvas id="fireworks"></canvas>

<!-- PAGE 1: MAIN GREETING -->

<section class="page active" id="page1">

<div class="lights">
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
    <span class="bulb"></span>
</div>

<h2>॥ My Dear ॥</h2>

<h1>शुभ दीपावली</h1>

<div class="diya">🪔</div>

<div class="card">

    <h2>A Festival of Happiness</h2>

    <p>
        May the light of Diwali bring happiness,
        peace, prosperity and success into your life.
    </p>

    <input id="name" placeholder="Enter your name">

    <p id="personalMessage"></p>

    <button onclick="showPersonalMessage()">
        Create My Wish
    </button>

    <br>

    <button onclick="showPage('page2')">
        Explore the Magic ✨
    </button>

</div>

<p style="margin-top:25px;">
    Tap anywhere to launch fireworks 🎆
</p>

</section>


<!-- PAGE 2: FESTIVAL OF LIGHTS -->

<section class="page" id="page2">

<h1>Festival of Lights</h1>

<div class="card">

    <div style="font-size:85px;">🏮</div>

    <h2>Let the Lights Shine</h2>

    <p>
        Diwali reminds us that light always triumphs
        over darkness. May your home be filled with
        warmth, joy and beautiful memories.
    </p>

</div>

<button onclick="showPage('page1')">
    Previous Page
</button>

<button onclick="showPage('page3')">
    Next Page →
</button>

</section>


<!-- PAGE 3: MAGICAL SKY -->

<section class="page" id="page3">

<h1>Magical Diwali Sky</h1>

<div class="card">

    <div style="font-size:85px;">🎆</div>

    <h2>Make a Wish!</h2>

    <p>
        Every spark tells a story.
        Every light brings a new hope.
        Tap the screen and fill the sky with colours!
    </p>

</div>

<button onclick="launchFireworks()">
    Launch Fireworks 🎇
</button>

<button onclick="showPage('page2')">
    ← Previous Page
</button>

<button onclick="showPage('page4')">
    Next Page →
</button>

</section>


<!-- PAGE 4: DIWALI WISHES -->

<section class="page" id="page4">

<h1>Happy Diwali!</h1>

<div class="card">

    <div style="font-size:80px;">🪔✨</div>

    <div class="wish">
        दीपावली की हार्दिक शुभकामनाएँ!
    </div>

    <div class="wish">
        May your life shine brighter than a thousand diyas.
    </div>

    <div class="wish">
        May happiness and success always find their way to you.
    </div>

    <div class="wish">
        Wishing you a beautiful and prosperous Diwali!
    </div>

</div>

<button onclick="showPage('page3')">
    ← Previous Page
</button>

</section>


<script>

/* PAGE NAVIGATION */

function showPage(pageId) {

    document.querySelectorAll(".page").forEach(page => {
        page.classList.remove("active");
    });

    document.getElementById(pageId).classList.add("active");

    if (pageId === "page3") {
        launchFireworks();
    }
}


/* PERSONAL GREETING */

function showPersonalMessage() {

    const name = document.getElementById("name").value.trim();

    document.getElementById("personalMessage").textContent =
        name
        ? "Happy Diwali, " + name + "! 🪔"
        : "Wishing you a very Happy Diwali! 🪔";

}


/* FIREWORKS ENGINE */

const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");

function resizeCanvas() {

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

}

resizeCanvas();

window.addEventListener("resize", resizeCanvas);

let particles = [];

function launchFireworks(x, y) {

    x = x ?? Math.random() * canvas.width;
    y = y ?? Math.random() * canvas.height * .65;

    const colors = [
        "#ff3838",
        "#ffcf40",
        "#38ffb3",
        "#43a5ff",
        "#ff55e8",
        "#ffffff"
    ];

    const color = colors[
        Math.floor(Math.random() * colors.length)
    ];

    for (let i = 0; i < 90; i++) {

        const angle = Math.random() * Math.PI * 2;
        const speed = Math.random() * 5 + 1;

        particles.push({

            x: x,
            y: y,

            vx: Math.cos(angle) * speed,
            vy: Math.sin(angle) * speed,

            alpha: 1,
            color: color,
            size: Math.random() * 3 + 1

        });

    }

}


function animateFireworks() {

    ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
    );

    for (let i = particles.length - 1; i >= 0; i--) {

        const p = particles[i];

        p.x += p.vx;
        p.y += p.vy;

        p.vy += 0.035;
        p.alpha -= 0.012;

        ctx.globalAlpha = Math.max(p.alpha, 0);
        ctx.fillStyle = p.color;

        ctx.beginPath();

        ctx.arc(
            p.x,
            p.y,
            p.size,
            0,
            Math.PI * 2
        );

        ctx.fill();

        if (p.alpha <= 0) {
            particles.splice(i, 1);
        }

    }

    ctx.globalAlpha = 1;

    requestAnimationFrame(animateFireworks);

}

animateFireworks();


/* TAP ANYWHERE FOR FIREWORKS */

document.addEventListener("click", function(event) {

    if (
        event.target.tagName !== "BUTTON" &&
        event.target.tagName !== "INPUT"
    ) {

        launchFireworks(
            event.clientX,
            event.clientY
        );

    }

});


/* AUTOMATIC FIREWORKS */

setInterval(() => {

    if (
        document.getElementById("page3")
        .classList.contains("active")
    ) {

        launchFireworks();

    }

}, 1000);


/* FLOATING LANTERNS */

function createLantern() {

    const lantern = document.createElement("div");

    lantern.className = "lantern";
    lantern.textContent = "🏮";

    lantern.style.left = Math.random() * 100 + "%";

    lantern.style.animationDuration =
        (8 + Math.random() * 8) + "s";

    document.body.appendChild(lantern);

    setTimeout(() => {
        lantern.remove();
    }, 16000);

}


setInterval(() => {

    if (
        document.getElementById("page2")
        .classList.contains("active")
    ) {

        createLantern();

    }

}, 700);

</script>

</body>
</html>
