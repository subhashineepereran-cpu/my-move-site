# my-move-site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cinema Magic - Watch Movies</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div id="splash-screen">
        <h1 class="netflix-animation">CINEMA</h1>
        <p class="tap-hint">Sound එක ඇසීමට Screen එක මත එක පාරක් Click කරන්න</p>
    </div>

    <div id="main-content" class="hidden">
        <header>
            <div class="logo">CINEMA</div>
            <nav>
                <a href="#" class="active">Home</a>
                <a href="#">Movies</a>
                <a href="#">TV Shows</a>
                <a href="#">My List</a>
            </nav>
        </header>
        
        <main>
            <section class="hero-banner">
                <div class="hero-details">
                    <span class="trending-badge">Trending #1</span>
                    <h1>Stranger Things</h1>
                    <p>ගුප්ත අභිරහස්, අද්භූත බලවේග සහ රහස් පරීක්ෂණ රැසකින් පිරුණු ලොවක්. කුඩා පිරිමි ළමයෙකුගේ අතුරුදන් වීමත් සමඟ මුළු නගරයම උඩුයටිකුරු වන හැටි නරඹන්න.</p>
                    <div class="hero-buttons">
                        <button class="btn play-btn">▶ Play</button>
                        <button class="btn info-btn">ℹ More Info</button>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <script src="script.js"></script>
</body>
</html>/* පොදු සැකසුම් */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    background-color: #111;
    color: #fff;
    font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
    overflow: hidden; /* Intro එක යනකන් සයිට් එක Scroll කරන්න බැරි වීමට */
}

/* --- Intro Splash Screen Styles --- */
#splash-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: #000;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 9999;
    transition: opacity 1s ease-out; /* Fade out වන කාලය */
}

.netflix-animation {
    font-size: 5rem;
    color: #E50914; /* Netflix රතු පාට */
    letter-spacing: 4px;
    font-weight: 900;
    text-transform: uppercase;
    opacity: 0;
    transform: scale(0.5);
    animation: zoomIn 3.5s forwards ease-in-out;
}

.tap-hint {
    color: #444;
    font-size: 0.85rem;
    margin-top: 20px;
    letter-spacing: 1px;
    animation: pulse 1.5s infinite;
}

/* Animations */
@keyframes zoomIn {
    0% { transform: scale(0.6); opacity: 0; }
    20% { opacity: 1; }
    100% { transform: scale(1.2); opacity: 1; letter-spacing: 12px; }
}

@keyframes pulse {
    0% { opacity: 0.3; }
    50% { opacity: 1; }
    100% { opacity: 0.3; }
}

/* --- Main Content Styles --- */
.hidden {
    display: none !important;
}

#main-content {
    animation: fadeIn 1.2s ease-in;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

/* Navigation Bar */
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 4%;
    background: linear-gradient(to bottom, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0) 100%);
    position: absolute;
    width: 100%;
    top: 0;
    z-index: 10;
}

header .logo {
    color: #E50914;
    font-size: 1.8rem;
    font-weight: bold;
    letter-spacing: 1px;
}

header nav a {
    color: #e5e5e5;
    text-decoration: none;
    margin-left: 20px;
    font-size: 0.95rem;
    transition: color 0.3s;
}

header nav a:hover, header nav a.active {
    color: #fff;
    font-weight: bold;
}

/* Movie Banner (Hero Section) */
.hero-banner {
    height: 100vh;
    background: linear-gradient(to rgba(0,0,0,0.2), rgba(17,17,17,1)), 
                url('https://images.unsplash.com/photo-1626814026160-2237a95fc5a0?q=80&w=1600') no-repeat center center/cover;
    display: flex;
    align-items: center;
    padding: 0 4%;
}

.hero-details {
    max-width: 600px;
}

.trending-badge {
    background-color: #E50914;
    padding: 4px 8px;
    font-size: 0.8rem;
    font-weight: bold;
    border-radius: 4px;
    display: inline-block;
    margin-bottom: 15px;
}

.hero-details h1 {
    font-size: 3.5rem;
    margin-bottom: 15px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.6);
}

.hero-details p {
    font-size: 1.1rem;
    line-height: 1.5;
    color: #cccccc;
    margin-bottom: 25px;
}

.hero-buttons {
    display: flex;
    gap: 15px;
}

.btn {
    padding: 12px 26px;
    font-size: 1rem;
    font-weight: bold;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: opacity 0.2s;
}

.btn:hover { opacity: 0.85; }
.play-btn { background-color: #fff; color: #000; }
.info-btn { background-color: rgba(109, 109, 110, 0.7); color: #fff; }

/* --- 📱 Mobile & Tablet Responsive Layout --- */
@media (max-width: 768px) {
    .netflix-animation {
        font-size: 2.8rem;
        letter-spacing: 2px;
    }

    @keyframes zoomIn {
        0% { transform: scale(0.7); opacity: 0; }
        20% { opacity: 1; }
        100% { transform: scale(1.1); opacity: 1; letter-spacing: 6px; }
    }

    header {
        flex-direction: column;
        gap: 12px;
        padding: 15px;
    }

    header nav a {
        margin: 0 8px;
        font-size: 0.85rem;
    }

    .hero-banner {
        align-items: flex-end;
        padding-bottom: 60px;
    }

    .hero-details h1 { font-size: 2.2rem; }
    .hero-details p { font-size: 0.95rem; }
}
// Intro එක සඳහා සිනමා ශබ්දයක් (Cinematic Sound Hook)
const introSound = new Audio('https://assets.mixkit.co/active_storage/sfx/2869/2869-84.wav'); 

// User මුලින්ම Screen එක උඩ කොහේ හෝ Click කල සැනින් සද්දය ප්ලේ වේ
document.addEventListener('click', () => {
    introSound.play().catch(err => console.log("Sound Autoplay block වී ඇත:", err));
}, { once: true });

// තත්පර 5කින් Splash Screen එක ඉවත් කර සයිට් එක පෙන්වීම
setTimeout(() => {
    const splash = document.getElementById('splash-screen');
    const mainContent = document.getElementById('main-content');

    if (splash) {
        splash.style.opacity = '0'; // Fade out ආරම්භය
    }

    // Fade out එක ඉවර වීමට තත්පර 1ක් දී සම්පූර්ණයෙන්ම අයින් කිරීම
    setTimeout(() => {
        if (splash) splash.classList.add('hidden');
        if (mainContent) mainContent.classList.remove('hidden');
        document.body.style.overflow = 'auto'; // සයිට් එක Scroll කිරීමට ඉඩ දීම
    }, 1000);

}, 5000); // තත්පර 5 කාලය (5000ms)
