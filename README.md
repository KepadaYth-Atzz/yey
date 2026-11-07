<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Maafin Aku Ya, Feny sayaangg💌</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@500;600;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        poppins: ['Poppins', 'sans-serif'],
                        caveat: ['Caveat', 'cursive']
                    },
                    colors: {
                        pinky: {
                            50: '#fdf2f8',
                            100: '#fce7f3',
                            200: '#fbcfe8',
                            300: '#f9a8d4',
                            400: '#f472b6',
                            500: '#ec4899',
                            600: '#db2777',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Poppins', sans-serif;
            overflow: hidden; /* Prevent scroll when button runs away */
            /* Gradasi animasi yang lebih hangat (Pink, Peach, Rose, Soft Yellow) */
            background: linear-gradient(135deg, #ffe4e6, #fbcfe8, #fef08a, #fecdd3);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            height: 100vh;
            width: 100vw;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Glassmorphism utility */
        .glass {
            background: rgba(255, 255, 255, 0.45);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.7);
            box-shadow: 0 8px 32px 0 rgba(236, 72, 153, 0.25);
        }

        /* Floating Animation for Background Hearts */
        @keyframes floatUp {
            0% { transform: translateY(100vh) scale(0.5) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-20vh) scale(1.2) rotate(360deg); opacity: 0; }
        }

        .bg-heart {
            position: absolute;
            /* Warna diatur dinamis via JS agar lebih ramai */
            animation: floatUp 8s linear infinite;
            z-index: 0;
            pointer-events: none;
        }

        /* Typewriter Cursor */
        .cursor::after {
            content: '|';
            animation: blink 1s step-end infinite;
            color: #db2777;
        }
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        /* Heart Beat Animation */
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            14% { transform: scale(1.3); }
            28% { transform: scale(1); }
            42% { transform: scale(1.3); }
            70% { transform: scale(1); }
        }
        .animate-heartbeat {
            animation: heartbeat 2s infinite;
        }

        /* Shake Animation for Password */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
        }
        .animate-shake {
            animation: shake 0.4s ease-in-out;
        }

        /* Sparkle Trail Effect */
        .sparkle {
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            animation: sparkleAnim 1s forwards;
            font-size: 20px; /* Diperbesar dari 14px agar lebih meriah */
            text-shadow: 0 0 6px rgba(255,255,255,0.9);
        }
        @keyframes sparkleAnim {
            0% { opacity: 1; transform: scale(1) translateY(0) rotate(0deg); }
            100% { opacity: 0; transform: scale(0) translateY(-20px) rotate(180deg); }
        }
        
        /* Escape Poof Effect */
        .poof {
            position: fixed;
            pointer-events: none;
            z-index: 50;
            animation: poofAnim 0.6s forwards ease-out;
            font-size: 24px;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
        }
        @keyframes poofAnim {
            0% { opacity: 1; transform: scale(0.5); }
            100% { opacity: 0; transform: scale(1.5) translateY(-30px); }
        }

        /* Smooth transition for runaway button */
        #btn-no {
            transition: all 0.15s ease-out; /* Made much faster! */
        }
    </style>
</head>
<body class="relative flex items-center justify-center text-gray-800">

    <!-- Background Floating Hearts Container -->
    <div id="hearts-container" class="fixed inset-0 overflow-hidden pointer-events-none z-0"></div>

    <!-- 1. INTRO SCREEN -->
    <div id="intro-screen" class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-white/20 backdrop-blur-sm transition-opacity duration-700">
        <div class="relative glass p-8 rounded-3xl text-center max-w-sm mx-4 transform transition hover:scale-105 duration-500 border-2 border-white/60">
            <!-- Dekorasi Ekstra Biar Ramai -->
            <div class="absolute -top-5 -left-5 text-4xl animate-bounce" style="animation-delay: 0.2s; filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.1));">🌸</div>
            <div class="absolute -bottom-4 -right-4 text-4xl animate-bounce" style="animation-delay: 0.5s; filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.1));">✨</div>

            <i class="fas fa-envelope-open-text text-5xl text-pinky-500 mb-4 animate-bounce"></i>
            <h1 class="text-2xl font-semibold text-pinky-600 mb-2">Hai Feny...</h1>
            <p class="text-pinky-500 mb-8">Ada pesan spesial buat kamu 💌</p>
            
            <button onclick="showPasswordScreen()" class="bg-pinky-500 hover:bg-pinky-600 text-white font-medium py-3 px-8 rounded-full shadow-lg hover:shadow-pinky-400/50 transition-all flex items-center justify-center gap-2 mx-auto animate-heartbeat">
                <i class="fas fa-heart"></i> Buka Pesan
            </button>
        </div>
    </div>

    <!-- 1.5 PASSWORD SCREEN -->
    <div id="password-screen" class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-white/20 backdrop-blur-sm transition-opacity duration-700 hidden opacity-0">
        <div class="relative glass p-8 rounded-3xl text-center max-w-sm mx-4 transform transition duration-500 border-2 border-white/60" id="password-card">
            <div class="absolute -top-5 -right-5 text-4xl animate-bounce" style="animation-delay: 0.3s; filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.1));">🔐</div>
            
            <i class="fas fa-lock text-5xl text-pinky-500 mb-4"></i>
            <h2 class="text-2xl font-semibold text-pinky-600 mb-2">Masukin Password</h2>
            <p class="text-pinky-500 mb-3 text-sm">Hanya Cintakuuu yang tau 🤫</p>
            
            <!-- Tambahan Clue / Petunjuk (Awalnya disembunyikan) -->
            <div id="password-clue" class="bg-white/60 rounded-xl p-3 mb-5 border border-pinky-200 shadow-sm animate-pulse hidden opacity-0 transition-opacity duration-500">
                <p id="clue-text" class="text-xs text-pinky-600 font-medium"><i class="fas fa-lightbulb text-yellow-500 mr-1"></i> Clue: Gabungan tanggal spesial kita ya sayang 😉 (6 angka)</p>
            </div>
            
            <input type="password" id="password-input" class="w-full px-4 py-3 rounded-xl border-2 border-pinky-300 focus:outline-none focus:border-pinky-500 text-center text-2xl tracking-[0.3em] font-bold mb-2 text-pinky-600 bg-white/70" placeholder="••••••">
            <p id="password-error" class="text-red-500 text-sm font-medium h-5 mb-4 opacity-0 transition-opacity">Password salah sayang! Coba lagi.</p>
            
            <button onclick="verifyPassword()" class="bg-pinky-500 hover:bg-pinky-600 text-white font-medium py-3 px-8 rounded-full shadow-lg transition-all w-full flex items-center justify-center gap-2">
                Buka Kunci <i class="fas fa-unlock"></i>
            </button>
        </div>
    </div>

    <!-- 2. MAIN CONTENT (Apology Card) -->
    <main id="main-content" class="relative z-10 w-full max-w-md p-4 opacity-0 transition-opacity duration-1000 hidden">
        <div class="relative glass rounded-3xl p-6 md:p-8 flex flex-col items-center text-center border-2 border-white/60">
            
            <!-- Dekorasi Ekstra Biar Ramai -->
            <div class="absolute top-4 right-4 text-2xl animate-pulse">🦋</div>
            <div class="absolute top-1/2 -left-3 text-3xl animate-pulse" style="animation-delay: 0.7s;">🌷</div>

            <!-- Cute Header -->
            <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center shadow-md mb-4 text-pinky-500 text-3xl">
                <i class="fas fa-sad-tear"></i>
            </div>
            
            <h2 class="text-2xl font-bold text-pinky-600 mb-4 font-poppins">To: Feny Sayang 💖</h2>

            <!-- Typewriter Letter -->
            <div class="bg-white/50 rounded-2xl p-5 w-full min-h-[160px] flex items-start text-left mb-6 border border-pinky-200">
                <p id="typewriter-text" class="font-caveat text-2xl text-gray-700 leading-snug cursor"></p>
            </div>

            <!-- Interaction Buttons -->
            <div id="button-container" class="relative w-full h-16 flex items-center justify-center gap-4 opacity-0 transition-opacity duration-1000">
                <!-- YES Button -->
                <button onclick="acceptApology()" class="bg-pinky-500 hover:bg-pinky-600 text-white font-semibold py-3 px-8 rounded-full shadow-lg transition-transform hover:scale-110 active:scale-95 flex items-center gap-2 z-20">
                    Maafin yaa🥺<i class="fas fa-heart"></i>
                </button>

                <!-- NO Button (Runaway) -->
                <button id="btn-no" class="absolute bg-gray-400 hover:bg-gray-500 text-white font-semibold py-3 px-8 rounded-full shadow-lg flex items-center gap-2 z-10" style="left: 60%;">
                    Gak <i class="fas fa-times"></i>
                </button>
            </div>
        </div>
    </main>

    <!-- 3. SUCCESS MODAL -->
    <div id="success-modal" class="fixed inset-0 z-[100] flex items-center justify-center bg-black/40 backdrop-blur-sm opacity-0 pointer-events-none transition-opacity duration-500">
        <div class="glass bg-white/70 p-8 rounded-3xl text-center max-w-sm mx-4 transform scale-75 transition-transform duration-500 shadow-2xl border-2 border-pinky-300" id="success-card">
            <div class="w-20 h-20 bg-pinky-100 rounded-full flex items-center justify-center mx-auto mb-4 shadow-inner">
                <i class="fas fa-face-grin-hearts text-5xl text-pinky-500 animate-heartbeat"></i>
            </div>
            <h2 class="text-3xl font-bold text-pinky-600 mb-2 font-caveat">Yeeeyyy! 🎉</h2>
            <p class="text-gray-700 font-medium mb-6">
                Makasih banyak ya sayang udah mau maafin aku. Aku janji bakal jadi lebih baik lagi buat kamu.<br><br>
                <span class="text-pinky-600 font-bold">I Love You, Feny! 💖♾️</span>
            </p>
            <button onclick="showWhatsAppChat()" class="bg-pinky-500 hover:bg-pinky-600 text-white font-medium py-2 px-6 rounded-full shadow-md transition-all">
                Love you too! 🥰
            </button>
        </div>
    </div>

    <!-- 4. WHATSAPP CHAT MODAL -->
    <div id="wa-modal" class="fixed inset-0 z-[110] flex items-center justify-center bg-black/40 backdrop-blur-sm opacity-0 pointer-events-none transition-opacity duration-500">
        <div class="glass bg-white/70 p-8 rounded-3xl text-center w-full max-w-sm mx-4 transform scale-75 transition-transform duration-500 shadow-2xl border-2 border-pinky-300" id="wa-card">
            <!-- Ikon WhatsApp -->
            <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4 shadow-inner">
                <i class="fab fa-whatsapp text-4xl text-green-500 animate-bounce"></i>
            </div>
            
            <h2 class="text-2xl font-bold text-green-600 mb-2 font-poppins">Balas ke Ayang 💌</h2>
            <p class="text-gray-700 font-medium mb-4 text-sm">
                Tulis pesan balasan buat aku ya sayangku cintaku maniskuuuuuu...
            </p>
            
            <!-- Tempat Ngetik Pesan -->
            <textarea id="wa-message" rows="4" class="w-full px-4 py-3 rounded-xl border-2 border-green-300 focus:outline-none focus:border-green-500 text-gray-700 mb-4 bg-white/80 resize-none shadow-inner" placeholder="Ketik pesanmu di sini..."></textarea>
            
            <button onclick="sendWhatsApp()" class="bg-green-500 hover:bg-green-600 text-white font-medium py-3 px-6 rounded-full shadow-md transition-all w-full flex justify-center items-center gap-2">
                Kirim via WA <i class="fas fa-paper-plane"></i>
            </button>
        </div>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // --- TEXT CONTENT ---
        const apologyText = "Maafin aku ya sayang... Aku sadar aku udah salah dan bikin kamu sedih. Aku nyesel banget. Aku janji bakal perbaiki semuanya dan jadi lebih baik lagi. Kamu mau kan maafin aku?";

        // --- MAGICAL CURSOR TRAIL ---
        function createSparkle(x, y) {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            // Randomize emojis for the trail
            sparkle.innerHTML = ['✨', '💖', '🌸', '⭐', '🤍'][Math.floor(Math.random() * 5)];
            sparkle.style.left = (x - 10) + 'px';
            sparkle.style.top = (y - 10) + 'px';
            document.body.appendChild(sparkle);
            
            setTimeout(() => {
                sparkle.remove();
            }, 1000);
        }

        // Mouse trail for Desktop
        document.addEventListener('mousemove', function(e) {
            // Limit spawn rate to avoid performance issues
            if (Math.random() > 0.8) { 
                createSparkle(e.clientX, e.clientY);
            }
        });

        // Touch trail for Mobile
        document.addEventListener('touchmove', function(e) {
            if (e.touches.length > 0 && Math.random() > 0.7) {
                createSparkle(e.touches[0].clientX, e.touches[0].clientY);
            }
        }, { passive: true });


        // --- WEB AUDIO API (Soft Background Music & Sound Effects) ---
        const AudioContext = window.AudioContext || window.webkitAudioContext;
        let audioCtx;
        
        function initAudio() {
            if (!audioCtx) {
                audioCtx = new AudioContext();
            }
        }

        function playSoftBGM() {
            try {
                // A very soft, repetitive lullaby/music-box style melody
                const melody = [
                    { f: 329.63, d: 0.5 }, // E4
                    { f: 392.00, d: 0.5 }, // G4
                    { f: 440.00, d: 1.0 }, // A4
                    { f: 392.00, d: 0.5 }, // G4
                    { f: 329.63, d: 0.5 }, // E4
                    { f: 261.63, d: 1.5 }  // C4
                ];
                
                let time = audioCtx.currentTime;
                
                function playSequence() {
                    let seqTime = time;
                    melody.forEach(note => {
                        const osc = audioCtx.createOscillator();
                        const gain = audioCtx.createGain();
                        
                        osc.type = 'sine'; // Soft sine wave
                        osc.frequency.setValueAtTime(note.f, seqTime);
                        
                        // Envelope for soft attack and release
                        gain.gain.setValueAtTime(0, seqTime);
                        gain.gain.linearRampToValueAtTime(0.05, seqTime + 0.1);
                        gain.gain.exponentialRampToValueAtTime(0.001, seqTime + note.d - 0.05);
                        
                        osc.connect(gain);
                        gain.connect(audioCtx.destination);
                        
                        osc.start(seqTime);
                        osc.stop(seqTime + note.d);
                        
                        seqTime += note.d;
                    });
                    
                    // Loop the melody every 6 seconds
                    setTimeout(playSequence, 6000);
                }
                playSequence();
            } catch (e) {
                console.log("Audio not supported or blocked");
            }
        }

        function playClickSound() {
            if(!audioCtx) return;
            try {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(600, audioCtx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(1200, audioCtx.currentTime + 0.1);
                gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.1);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + 0.1);
            } catch (e) {}
        }

        function playSuccessSound() {
            if(!audioCtx) return;
            try {
                const chords = [523.25, 659.25, 783.99]; // C major chord
                chords.forEach((freq, idx) => {
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(freq, audioCtx.currentTime + (idx * 0.1));
                    gain.gain.setValueAtTime(0, audioCtx.currentTime + (idx * 0.1));
                    gain.gain.linearRampToValueAtTime(0.1, audioCtx.currentTime + (idx * 0.1) + 0.1);
                    gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + (idx * 0.1) + 1);
                    osc.connect(gain);
                    gain.connect(audioCtx.destination);
                    osc.start(audioCtx.currentTime + (idx * 0.1));
                    osc.stop(audioCtx.currentTime + (idx * 0.1) + 1);
                });
            } catch (e) {}
        }

        function playEscapeSound() {
            if(!audioCtx) return;
            try {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(800, audioCtx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(1500, audioCtx.currentTime + 0.1);
                gain.gain.setValueAtTime(0.05, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + 0.1);
            } catch (e) {}
        }

        function playTypeSound() {
            if(!audioCtx) return;
            try {
  