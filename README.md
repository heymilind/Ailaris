:root {
    --neon-orange: #FF4B02;
    --neon-green: #56FF75;
    --bg-black: #000000;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background-color: var(--bg-black);
    color: var(--neon-green);
    min-height: 100vh;
    overflow: hidden;
}

.press-start-2p-regular {
    font-family: "Press Start 2P", system-ui;
    font-weight: 400;
    font-style: normal;
}

.poppins-bold {
    font-family: "Poppins", sans-serif;
    font-weight: 700;
    font-style: normal;
}

.audiowide-regular {
    font-family: "Audiowide", sans-serif;
    font-weight: 400;
    font-style: normal;
}

.page {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
    display: flex;
    align-items: center;
    justify-content: center;
}

.hidden {
    transform: translateX(100%);
    opacity: 0;
    pointer-events: none;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    position: relative;
    text-align: center;
}

.triangle {
    width: 0;
    height: 0;
    border-left: 25px solid transparent;
    border-right: 25px solid transparent;
    border-bottom: 50px solid var(--neon-orange);
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translateX(-50%);
    animation: float 3s ease-in-out infinite;
}

.hero-text {
    font-size: 2.5rem;
    margin-top: 4rem;
    animation: glitch 1s linear infinite;
}

.typing-text {
    font-size: 2rem;
    position: relative;
}

.typing-text::after {
    content: '|';
    position: absolute;
    right: -10px;
    animation: blink 1s infinite;
}

.trademark-message {
    font-size: 1.5rem;
    line-height: 1.5;
}

.brand {
    color: var(--neon-green);
    font-size: 2rem;
    animation: glowText 2s ease-in-out infinite alternate;
}

.countdown-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    min-height: 70vh;
}

.card {
    background-color: var(--neon-orange);
    border-radius: 20px;
    padding: 2rem;
    width: 80%;
    max-width: 400px;
    animation: float 3s ease-in-out infinite;
}

.card-content {
    color: white;
    text-align: center;
}

.wait-text {
    margin-bottom: 1rem;
    font-size: 1.5rem;
}

.date {
    font-size: 1.8rem;
    letter-spacing: 2px;
}

.trademark-notice {
    font-size: 0.7rem;
    max-width: 80%;
    text-align: center;
    line-height: 1.5;
    margin-top: 2rem;
}

@keyframes float {
    0%, 100% { transform: translateY(0) translateX(-50%); }
    50% { transform: translateY(-20px) translateX(-50%); }
}

@keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
}

@keyframes glitch {
    2%, 64% { transform: translate(2px, 0) skew(0deg); }
    4%, 60% { transform: translate(-2px, 0) skew(0deg); }
    62% { transform: translate(0, 0) skew(5deg); }
}

@keyframes glowText {
    from {
        text-shadow: 0 0 5px var(--neon-green),
                     0 0 10px var(--neon-green),
                     0 0 15px var(--neon-green);
    }
    to {
        text-shadow: 0 0 10px var(--neon-green),
                     0 0 20px var(--neon-green),
                     0 0 30px var(--neon-green);
    }
}

@media (max-width: 768px) {
    .hero-text {
        font-size: 1.8rem;
    }
    
    .typing-text {
        font-size: 1.5rem;
    }
    
    .trademark-message {
        font-size: 1.2rem;
    }
    
    .card {
        width: 90%;
    }
    
    .wait-text {
        font-size: 1.2rem;
    }
    
    .date {
        font-size: 1.5rem;
    }
    
    .trademark-notice {
        font-size: 0.6rem;
    }
}
