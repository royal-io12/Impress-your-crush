    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>For The Most Amazing Person ❤️</title>
        <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Montserrat:wght@400;600&display=swap" rel="stylesheet">
        <style>
            /* CSS Styles */
            * {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }

            body {
                background-color: #fff0f5;
                overflow-x: hidden;
                font-family: 'Montserrat', sans-serif;
            }

            .page {
                min-height: 100vh;
                width: 100%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                padding: 40px 20px;
                position: relative;
                overflow: hidden;
                opacity: 0;
                transform: translateY(20px);
                transition: opacity 1s, transform 1s;
            }

            .page.active {
                opacity: 1;
                transform: translateY(0);
            }

            .hidden {
                display: none;
            }

            h1 {
                color: #ff1493;
                font-size: 3rem;
                margin-bottom: 30px;
                text-align: center;
                text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
                font-family: 'Dancing Script', cursive;
                background: linear-gradient(45deg, #ff1493, #ff69b4);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                animation: titleGlow 3s infinite alternate;
            }

            @keyframes titleGlow {
                0% {
                    text-shadow: 0 0 10px rgba(255, 20, 147, 0.5);
                }
                100% {
                    text-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
                }
            }

            p {
                color: #555;
                font-size: 1.3rem;
                line-height: 1.8;
                max-width: 800px;
                text-align: center;
                margin-bottom: 25px;
                position: relative;
                z-index: 2;
            }

            .heart {
                position: absolute;
                pointer-events: none;
                animation: float 4s ease-in-out infinite;
                z-index: 1;
                filter: drop-shadow(0 0 5px rgba(255, 20, 147, 0.7));
            }

            .flower {
                position: absolute;
                pointer-events: none;
                animation: float 6s ease-in-out infinite;
                z-index: 1;
                filter: drop-shadow(0 0 5px rgba(255, 215, 0, 0.5));
            }

            @keyframes float {
                0%, 100% {
                    transform: translateY(0) rotate(0deg);
                }
                50% {
                    transform: translateY(-30px) rotate(5deg);
                }
            }

            @keyframes pulse {
                0%, 100% {
                    transform: scale(1);
                }
                50% {
                    transform: scale(1.15);
                }
            }

            .btn-container {
                display: flex;
                gap: 20px;
                margin-top: 40px;
                z-index: 10;
            }

            button {
                background: linear-gradient(45deg, #ff69b4, #ff1493);
                color: white;
                border: none;
                padding: 15px 30px;
                border-radius: 50px;
                font-size: 1.1rem;
                cursor: pointer;
                transition: all 0.3s;
                box-shadow: 0 4px 15px rgba(255, 105, 180, 0.4);
                position: relative;
                overflow: hidden;
                z-index: 1;
            }

            button:hover {
                transform: translateY(-3px);
                box-shadow: 0 8px 20px rgba(255, 105, 180, 0.6);
            }

            button::before {
                content: '';
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: linear-gradient(45deg, #ff1493, #ff69b4);
                z-index: -1;
                opacity: 0;
                transition: opacity 0.3s;
            }

            button:hover::before {
                opacity: 1;
            }

            .pulse {
                animation: pulse 2s infinite;
            }

            /* Page-specific styles */
            #page1 {
                background: linear-gradient(135deg, #fff0f5 0%, #ffe6ee 100%);
            }

            #page2 {
                background: linear-gradient(135deg, #fffaf0 0%, #fff0e6 100%);
            }

            #page3 {
                background: linear-gradient(135deg, #f0fff0 0%, #e6ffe6 100%);
            }

            #page4 {
                background: linear-gradient(135deg, #f0f8ff 0%, #e6f0ff 100%);
            }

            .special-text {
                font-size: 1.8rem;
                color: #ff1493;
                font-weight: bold;
                margin: 30px 0;
                font-family: 'Dancing Script', cursive;
                text-shadow: 0 0 10px rgba(255, 20, 147, 0.3);
                animation: textColorChange 8s infinite alternate;
            }

            @keyframes textColorChange {
                0% { color: #ff1493; }
                25% { color: #ff69b4; }
                50% { color: #ff8c00; }
                75% { color: #da70d6; }
                100% { color: #ff1493; }
            }

            .photo-frame {
                width: 220px;
                height: 220px;
                border: 12px solid white;
                border-radius: 50%;
                box-shadow: 0 0 30px rgba(255, 105, 180, 0.4);
                margin: 30px;
                overflow: hidden;
                background-color: #f8f8f8;
                display: flex;
                justify-content: center;
                align-items: center;
                transition: transform 0.5s, box-shadow 0.5s;
                animation: photoFloat 4s ease-in-out infinite;
            }

            @keyframes photoFloat {
                0%, 100% {
                    transform: translateY(0) rotate(0deg);
                }
                50% {
                    transform: translateY(-15px) rotate(2deg);
                }
            }

            .photo-frame:hover {
                transform: scale(1.05) rotate(5deg);
                box-shadow: 0 0 40px rgba(255, 105, 180, 0.6);
            }

            .photo-placeholder {
                width: 100%;
                height: 100%;
                display: flex;
                justify-content: center;
                align-items: center;
                background: linear-gradient(45deg, #f8f8f8, #e8e8e8);
                color: #aaa;
                font-size: 1.2rem;
                text-align: center;
                padding: 20px;
            }

            .love-meter {
                width: 80%;
                max-width: 500px;
                height: 40px;
                background-color: #f0f0f0;
                border-radius: 20px;
                margin: 30px 0;
                overflow: hidden;
                box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.1);
                position: relative;
            }

            .love-progress {
                height: 100%;
                width: 0;
                background: linear-gradient(90deg, #ff69b4, #ff1493, #ff69b4);
                background-size: 200% 100%;
                border-radius: 20px;
                animation: fillLove 3s forwards, progressGradient 3s infinite;
                position: relative;
                overflow: hidden;
            }

            .love-progress::after {
                content: '';
                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                background: linear-gradient(90deg, 
                                rgba(255,255,255,0) 0%, 
                                rgba(255,255,255,0.8) 50%, 
                                rgba(255,255,255,0) 100%);
                animation: shine 2s infinite;
            }

            @keyframes fillLove {
                from { width: 0%; }
                to { width: 100%; }
            }

            @keyframes progressGradient {
                0% { background-position: 0% 50%; }
                50% { background-position: 100% 50%; }
                100% { background-position: 0% 50%; }
            }

            @keyframes shine {
                0% { transform: translateX(-100%); }
                100% { transform: translateX(100%); }
            }

            .memory {
                background-color: white;
                padding: 25px;
                border-radius: 15px;
                margin: 15px;
                box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
                max-width: 320px;
                text-align: center;
                transition: all 0.4s;
                position: relative;
                overflow: hidden;
                z-index: 1;
            }

            .memory:hover {
                transform: translateY(-10px) scale(1.03);
                box-shadow: 0 12px 25px rgba(0, 0, 0, 0.15);
            }

            .memory::before {
                content: '';
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 5px;
                background: linear-gradient(90deg, #ff69b4, #ff1493);
                z-index: 2;
            }

            .memory h3 {
                color: #ff1493;
                margin-bottom: 10px;
                font-size: 1.4rem;
            }

            .memory p {
                font-size: 1.1rem;
                color: #666;
            }

            .memory-container {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                margin: 30px 0;
                perspective: 1000px;
            }

            .firework {
                position: absolute;
                width: 8px;
                height: 8px;
                border-radius: 50%;
                pointer-events: none;
                box-shadow: 0 0 10px 5px rgba(255, 20, 147, 0.7);
                animation: fireworkExplode 1s forwards;
                transform: scale(0);
            }

            @keyframes fireworkExplode {
                0% {
                    transform: scale(0);
                    opacity: 1;
                }
                100% {
                    transform: scale(20);
                    opacity: 0;
                }
            }

            .floating-text {
                position: absolute;
                font-size: 1.2rem;
                color: #ff1493;
                font-weight: bold;
                pointer-events: none;
                animation: floatUp 4s linear forwards;
                z-index: 5;
            }

            @keyframes floatUp {
                0% {
                    transform: translateY(0) rotate(0deg);
                    opacity: 1;
                }
                100% {
                    transform: translateY(-100px) rotate(10deg);
                    opacity: 0;
                }
            }

            .sparkle {
                position: absolute;
                width: 6px;
                height: 6px;
                background-color: white;
                border-radius: 50%;
                pointer-events: none;
                animation: sparkleTwinkle 1.5s infinite alternate;
                filter: blur(0.5px);
            }

            @keyframes sparkleTwinkle {
                0% {
                    transform: scale(0.8);
                    opacity: 0.7;
                }
                100% {
                    transform: scale(1.3);
                    opacity: 1;
                }
            }

            .heart-beat {
                position: absolute;
                font-size: 30px;
                animation: heartBeat 1.5s infinite;
                z-index: 1;
            }

            @keyframes heartBeat {
                0% {
                    transform: scale(1);
                }
                14% {
                    transform: scale(1.3);
                }
                28% {
                    transform: scale(1);
                }
                42% {
                    transform: scale(1.3);
                }
                70% {
                    transform: scale(1);
                }
            }

            .confetti {
                position: absolute;
                width: 15px;
                height: 15px;
                background-color: #f00;
                opacity: 0;
                z-index: 10;
                animation: confettiFall 5s linear forwards;
            }

            @keyframes confettiFall {
                0% {
                    transform: translateY(-100vh) rotate(0deg);
                    opacity: 1;
                }
                100% {
                    transform: translateY(100vh) rotate(720deg);
                    opacity: 0;
                }
            }

            .page-background {
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                z-index: 0;
                opacity: 0.1;
                pointer-events: none;
            }

            .cursor-follower {
                position: fixed;
                width: 30px;
                height: 30px;
                background-color: rgba(255, 105, 180, 0.3);
                border-radius: 50%;
                pointer-events: none;
                z-index: 9999;
                transform: translate(-50%, -50%);
                mix-blend-mode: multiply;
                filter: blur(5px);
            }

            .ripple {
                position: absolute;
                border-radius: 50%;
                background-color: rgba(255, 20, 147, 0.3);
                transform: scale(0);
                animation: rippleEffect 1s linear;
                pointer-events: none;
            }

            @keyframes rippleEffect {
                to {
                    transform: scale(4);
                    opacity: 0;
                }
            }
        </style>
    </head>
    <body>
        <div class="cursor-follower"></div>

        <!-- Page 1: First Impressions -->
        <div id="page1" class="page">
            <div class="page-background"></div>
            <h1>To The Most Amazing Person 💖</h1>
            <div class="special-text">Every moment with you feels magical ✨</div>
            <p>From the very first time we met, there was something about you that captured my heart. Your smile is like sunshine, and your laughter is my favorite melody.</p>
            <p>I created this little space to show you how special you are to me. Each page is filled with my feelings for you 🌹</p>
            <div class="photo-frame">
        <img src="R.jpg" alt="My Crush" style="width:100%; height:100%; object-fit:cover;">
    </div>
            <div class="btn-container">
                <button onclick="nextPage()">Discover More ➡️</button>
            </div>
        </div>

        <!-- Page 2: Reasons I Like You -->
        <div id="page2" class="page hidden">
            <div class="page-background"></div>
            <h1>Why You're Incredible 🌟</h1>
            <div class="special-text">Let me count the ways... ✨</div>
            <div class="love-meter">
                <div class="love-progress"></div>
            </div>
            <p>1. Your kindness radiates from you like warm sunlight 🌈</p>
            <p>2. That smile of yours could light up the darkest night ☀️</p>
            <p>3. Your intelligence and passion leave me in awe every day 📚</p>
            <p>4. The way you care about others shows your beautiful soul 💝</p>
            <div class="btn-container">
                <button onclick="prevPage()">⬅️ Back</button>
                <button onclick="nextPage()">Continue Journey ➡️</button>
            </div>
        </div>

        <!-- Page 3: Memories -->
        <div id="page3" class="page hidden">
            <div class="page-background"></div>
            <h1>Our Special Moments 🌸</h1>
            <div class="special-text">Every memory with you is precious 💎</div>
            <div class="memory-container">
                <div class="memory">
                    <h3>Our First Meeting 🌱</h3>
                    <p>I'll never forget how my heart raced when I first saw you</p>
                </div>
                <div class="memory">
                    <h3>That Time We Laughed 😂</h3>
                    <p>When we couldn't stop laughing together</p>
                </div>
                <div class="memory">
                    <h3>Deep Conversations 🌙</h3>
                    <p>Those late-night talks that meant so much</p>
                </div>
            </div>
            <p>I treasure every second we've shared and dream of countless more moments together ✨</p>
            <div class="btn-container">
                <button onclick="prevPage()">⬅️ Back</button>
                <button onclick="nextPage()">Final Message ➡️</button>
            </div>
        </div>

        <!-- Page 4: Final Confession -->
        <div id="page4" class="page hidden">
            <div class="page-background"></div>
            <h1>My Heart's True Words 💌</h1>
            <div class="special-text pulse">I've fallen for you... completely and deeply ❤️</div>
            <p>This isn't just a passing feeling - it's something real and profound. You've touched my heart in ways I never thought possible.</p>
            <p>I don't know what the future holds, but I know I want you in mine. Would you let me show you how wonderful we could be together? 🌹</p>
            <div class="btn-container">
                <button onclick="prevPage()">⬅️ Back</button>
                <button id="finalBtn" onclick="showFinalSurprise()">Click for Magic! ✨</button>
            </div>
        </div>

        <script>
            // Enhanced JavaScript with more animations
            let currentPage = 1;
            const totalPages = 4;

            // Initialize first page
            document.addEventListener('DOMContentLoaded', function() {
                document.getElementById(`page${currentPage}`).classList.add('active');
                createHearts();
                createFlowers();
                addSparkles();
                setupCursorFollower();
                setupRippleEffect();
            });

            function nextPage() {
                if (currentPage < totalPages) {
                    const currentPageEl = document.getElementById(`page${currentPage}`);
                    currentPageEl.classList.remove('active');
                    currentPageEl.classList.add('hidden');
                    
                    currentPage++;
                    const nextPageEl = document.getElementById(`page${currentPage}`);
                    nextPageEl.classList.remove('hidden');
                    setTimeout(() => {
                        nextPageEl.classList.add('active');
                    }, 50);
                    
                    createHearts();
                    createFlowers();
                    addSparkles();
                    createFloatingText();
                }
            }

            function prevPage() {
                if (currentPage > 1) {
                    const currentPageEl = document.getElementById(`page${currentPage}`);
                    currentPageEl.classList.remove('active');
                    currentPageEl.classList.add('hidden');
                    
                    currentPage--;
                    const prevPageEl = document.getElementById(`page${currentPage}`);
                    prevPageEl.classList.remove('hidden');
                    setTimeout(() => {
                        prevPageEl.classList.add('active');
                    }, 50);
                }
            }

            // Create floating hearts with more variety
            function createHearts() {
                const hearts = ['❤️', '🧡', '💛', '💚', '💙', '💜', '🤎', '🖤', '🤍', '💖', '💗', '💓', '💞', '💕'];
                const page = document.getElementById(`page${currentPage}`);
                
                for (let i = 0; i < 15; i++) {
                    const heart = document.createElement('div');
                    heart.className = Math.random() > 0.7 ? 'heart-beat' : 'heart';
                    heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.top = Math.random() * 100 + 'vh';
                    heart.style.fontSize = (Math.random() * 25 + 15) + 'px';
                    heart.style.animationDuration = (Math.random() * 4 + 3) + 's';
                    heart.style.animationDelay = (Math.random() * 2) + 's';
                    heart.style.opacity = Math.random() * 0.6 + 0.4;
                    page.appendChild(heart);
                }
            }

            // Create floating flowers with more variety
            function createFlowers() {
                const flowers = ['🌹', '🌸', '🌺', '🌻', '🌼', '🌷', '💐', '🏵️', '🌱', '🌿', '🍀', '🌾'];
                const page = document.getElementById(`page${currentPage}`);
                
                for (let i = 0; i < 12; i++) {
                    const flower = document.createElement('div');
                    flower.className = 'flower';
                    flower.innerHTML = flowers[Math.floor(Math.random() * flowers.length)];
                    flower.style.left = Math.random() * 100 + 'vw';
                    flower.style.top = Math.random() * 100 + 'vh';
                    flower.style.fontSize = (Math.random() * 30 + 20) + 'px';
                    flower.style.animationDuration = (Math.random() * 5 + 4) + 's';
                    flower.style.animationDelay = (Math.random() * 3) + 's';
                    flower.style.opacity = Math.random() * 0.6 + 0.4;
                    page.appendChild(flower);
                }
            }

            // Add sparkling effects
            function addSparkles() {
                const page = document.getElementById(`page${currentPage}`);
                
                for (let i = 0; i < 20; i++) {
                    const sparkle = document.createElement('div');
                    sparkle.className = 'sparkle';
                    sparkle.style.left = Math.random() * 100 + 'vw';
                    sparkle.style.top = Math.random() * 100 + 'vh';
                    sparkle.style.width = (Math.random() * 6 + 3) + 'px';
                    sparkle.style.height = sparkle.style.width;
                    sparkle.style.animationDelay = (Math.random() * 2) + 's';
                    page.appendChild(sparkle);
                }
            }

            // Create floating text elements
            function createFloatingText() {
                const texts = ['Amazing', 'Beautiful', 'Special', 'Lovely', 'Wonderful', 'Gorgeous', 'Perfect'];
                const page = document.getElementById(`page${currentPage}`);
                
                for (let i = 0; i < 5; i++) {
                    const text = document.createElement('div');
                    text.className = 'floating-text';
                    text.textContent = texts[Math.floor(Math.random() * texts.length)];
                    text.style.left = Math.random() * 80 + 10 + 'vw';
                    text.style.top = Math.random() * 80 + 10 + 'vh';
                    text.style.fontSize = (Math.random() * 20 + 16) + 'px';
                    text.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    text.style.color = `hsl(${Math.random() * 60 + 330}, 100%, 65%)`;
                    page.appendChild(text);
                    
                    // Remove after animation
                    setTimeout(() => {
                        text.remove();
                    }, 4000);
                }
            }

            // Fireworks effect for final page
            function showFinalSurprise() {
                const colors = ['#ff1493', '#ff69b4', '#ff8c00', '#da70d6', '#9400d3', '#4b0082', '#ff0000', '#00ff00'];
                const page = document.getElementById('page4');
                
                // Create big fireworks
                for (let i = 0; i < 30; i++) {
                    setTimeout(() => {
                        createFirework(page, colors);
                    }, i * 200);
                }
                
                // Create confetti
                createConfetti();
                
                document.getElementById('finalBtn').innerHTML = "You're Perfect! 💖";
                document.getElementById('finalBtn').style.animation = "pulse 1s infinite";
                
                // Add heartbeat element
                const heartBeat = document.createElement('div');
                heartBeat.className = 'heart-beat';
                heartBeat.innerHTML = '❤️';
                heartBeat.style.position = 'fixed';
                heartBeat.style.top = '50%';
                heartBeat.style.left = '50%';
                heartBeat.style.transform = 'translate(-50%, -50%)';
                heartBeat.style.fontSize = '100px';
                heartBeat.style.zIndex = '100';
                document.body.appendChild(heartBeat);
                
                setTimeout(() => {
                    heartBeat.remove();
                }, 3000);
            }

            function createFirework(container, colors) {
                const x = Math.random() * 80 + 10;
                const y = Math.random() * 80 + 10;
                const color = colors[Math.floor(Math.random() * colors.length)];
                
                const firework = document.createElement('div');
                firework.className = 'firework';
                firework.style.left = x + 'vw';
                firework.style.top = y + 'vh';
                firework.style.backgroundColor = color;
                firework.style.boxShadow = `0 0 10px 5px ${color}`;
                container.appendChild(firework);
                
                // Create smaller particles
                for (let i = 0; i < 12; i++) {
                    setTimeout(() => {
                        const particle = document.createElement('div');
                        particle.className = 'firework';
                        particle.style.left = x + 'vw';
                        particle.style.top = y + 'vh';
                        particle.style.backgroundColor = color;
                        particle.style.width = '4px';
                        particle.style.height = '4px';
                        particle.style.animation = `particleMove ${Math.random() * 1 + 0.5}s linear forwards`;
                        container.appendChild(particle);
                        
                        // Set random direction
                        const angle = Math.random() * Math.PI * 2;
                        const distance = Math.random() * 100 + 50;
                        const xMove = Math.cos(angle) * distance;
                        const yMove = Math.sin(angle) * distance;
                        
                        particle.style.setProperty('--x-move', xMove + 'px');
                        particle.style.setProperty('--y-move', yMove + 'px');
                        
                        setTimeout(() => {
                            particle.remove();
                        }, 1000);
                    }, i * 50);
                }
                
                setTimeout(() => {
                    firework.remove();
                }, 1000);
            }

            // Add CSS for particle movement
            const style = document.createElement('style');
            style.textContent = `
                @keyframes particleMove {
                    to {
                        transform: translate(var(--x-move), var(--y-move));
                        opacity: 0;
                    }
                }
            `;
            document.head.appendChild(style);

            function createConfetti() {
                const colors = ['#ff1493', '#ff69b4', '#ff8c00', '#da70d6', '#9400d3', '#4b0082', '#ff0000', '#00ff00'];
                
                for (let i = 0; i < 150; i++) {
                    setTimeout(() => {
                        const confetti = document.createElement('div');
                        confetti.className = 'confetti';
                        confetti.style.left = Math.random() * 100 + 'vw';
                        confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                        confetti.style.width = (Math.random() * 15 + 5) + 'px';
                        confetti.style.height = (Math.random() * 5 + 3) + 'px';
                        if (Math.random() > 0.5) {
                            confetti.style.borderRadius = '50%';
                        }
                        document.body.appendChild(confetti);
                        
                        setTimeout(() => {
                            confetti.remove();
                        }, 5000);
                    }, i * 20);
                }
            }

            // Cursor follower effect
            function setupCursorFollower() {
                const follower = document.querySelector('.cursor-follower');
                let posX = 0, posY = 0;
                let mouseX = 0, mouseY = 0;
                
                document.addEventListener('mousemove', (e) => {
                    mouseX = e.clientX;
                    mouseY = e.clientY;
                });
                
                const followerAnimation = () => {
                    posX += (mouseX - posX) / 5;
                    posY += (mouseY - posY) / 5;
                    
                    follower.style.left = posX + 'px';
                    follower.style.top = posY + 'px';
                    
                    requestAnimationFrame(followerAnimation);
                };
                
                followerAnimation();
            }

            // Ripple click effect
            function setupRippleEffect() {
                document.addEventListener('click', function(e) {
                    const ripple = document.createElement('span');
                    ripple.className = 'ripple';
                    ripple.style.left = e.clientX + 'px';
                    ripple.style.top = e.clientY + 'px';
                    document.body.appendChild(ripple);
                    
                    setTimeout(() => {
                        ripple.remove();
                    }, 1000);
                });
            }
        </script>
    </body>
    </html>
