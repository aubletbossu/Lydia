<!DOCTYPE html>


@keyframes fadeIn {
from { opacity: 0; transform: translateY(20px); }
to { opacity: 1; transform: translateY(0); }
}


@keyframes pop {
0% { transform: scale(0.5); opacity: 0; }
80% { transform: scale(1.1); }
100% { transform: scale(1); opacity: 1; }
}


.heart {
position: absolute;
color: #fff;
animation: floatUp linear infinite;
opacity: 0.7;
}


@keyframes floatUp {
from { transform: translateY(100vh) scale(1); opacity: 0.7; }
to { transform: translateY(-10vh) scale(1.4); opacity: 0; }
}
</style>
</head>
<body>
<div class="card">
<h1>Would you be my Valentine? ❤️</h1>
<div class="buttons">
<button id="yesBtn">Yes 💖</button>
<button id="noBtn">No</button>
</div>
<div id="loveMessage" class="message">Perfect 💘 Date: February 14</div>
</div>


<script>
const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const message = document.getElementById('loveMessage');


yesBtn.addEventListener('click', () => {
message.style.display = 'block';
launchHearts();
});


// Make the "No" button run away 😈
noBtn.addEventListener('mouseover', () => {
const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
noBtn.style.position = 'absolute';
noBtn.style.left = x + 'px';
noBtn.style.top = y + 'px';
});


function launchHearts() {
for (let i = 0; i < 25; i++) {
const heart = document.createElement('div');
heart.classList.add('heart');
heart.innerHTML = '❤';
heart.style.left = Math.random() * 100 + 'vw';
heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
document.body.appendChild(heart);


setTimeout(() => heart.remove(), 6000);
}
}
</script>
</body>
</html>
