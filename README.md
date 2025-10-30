<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MR-TAN - Solar System Tech Stack</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0e27;
            color: #00ff00;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .header {
            text-align: center;
            padding: 40px 20px;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            border-bottom: 2px solid #00ff00;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 3px solid #00ff00;
            box-shadow: 0 0 30px rgba(0, 255, 0, 0.5);
            margin-bottom: 20px;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        h1 {
            font-size: 3em;
            margin: 20px 0;
            text-shadow: 0 0 20px #00ff00;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 10px #00ff00, 0 0 20px #00ff00; }
            to { text-shadow: 0 0 20px #00ff00, 0 0 40px #00ff00, 0 0 60px #00ff00; }
        }

        .typing-text {
            font-size: 1.2em;
            color: #00ff00;
            margin: 10px 0;
        }

        .solar-system-container {
            position: relative;
            width: 100%;
            min-height: 800px;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 50px 20px;
            background: radial-gradient(ellipse at center, #1a1a2e 0%, #0a0e27 70%);
        }

        .solar-system {
            position: relative;
            width: 700px;
            height: 700px;
        }

        .sun {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, #306998, #FFD43B);
            border-radius: 50%;
            box-shadow: 0 0 60px rgba(255, 212, 59, 0.8), 0 0 100px rgba(48, 105, 152, 0.6);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            animation: sunPulse 3s ease-in-out infinite;
        }

        @keyframes sunPulse {
            0%, 100% { transform: translate(-50%, -50%) scale(1); }
            50% { transform: translate(-50%, -50%) scale(1.1); }
        }

        .sun img {
            width: 90px;
            height: 90px;
            filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.8));
        }

        .orbit {
            position: absolute;
            top: 50%;
            left: 50%;
            border: 2px solid rgba(0, 255, 0, 0.2);
            border-radius: 50%;
            transform: translate(-50%, -50%);
        }

        .orbit-1 { width: 200px; height: 200px; animation: rotate 10s linear infinite; }
        .orbit-2 { width: 300px; height: 300px; animation: rotate 15s linear infinite; }
        .orbit-3 { width: 400px; height: 400px; animation: rotate 20s linear infinite; }
        .orbit-4 { width: 500px; height: 500px; animation: rotate 25s linear infinite; }
        .orbit-5 { width: 600px; height: 600px; animation: rotate 30s linear infinite; }

        @keyframes rotate {
            from { transform: translate(-50%, -50%) rotate(0deg); }
            to { transform: translate(-50%, -50%) rotate(360deg); }
        }

        .planet {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 60px;
            background: rgba(0, 20, 40, 0.8);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
            transition: all 0.3s ease;
            border: 2px solid rgba(0, 255, 0, 0.5);
        }

        .planet:hover {
            transform: translateX(-50%) scale(1.3);
            box-shadow: 0 0 40px rgba(0, 255, 0, 0.9);
            z-index: 100;
        }

        .planet img {
            width: 40px;
            height: 40px;
            filter: drop-shadow(0 0 5px rgba(0, 255, 0, 0.5));
        }

        .planet-label {
            position: absolute;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
            color: #00ff00;
            font-size: 0.8em;
            white-space: nowrap;
            opacity: 0;
            transition: opacity 0.3s;
            text-shadow: 0 0 10px #00ff00;
        }

        .planet:hover .planet-label {
            opacity: 1;
        }

        .content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .section {
            background: rgba(26, 26, 46, 0.8);
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.3);
        }

        .section h2 {
            color: #00ff00;
            margin-bottom: 20px;
            font-size: 2em;
            text-shadow: 0 0 10px #00ff00;
        }

        .code-block {
            background: #000;
            border: 1px solid #00ff00;
            border-radius: 5px;
            padding: 20px;
            margin: 15px 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
            color: #00ff00;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .stat-card {
            background: rgba(0, 0, 0, 0.5);
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .social-links a {
            background: rgba(0, 255, 0, 0.1);
            border: 2px solid #00ff00;
            color: #00ff00;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: rgba(0, 255, 0, 0.3);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
            transform: translateY(-3px);
        }

        .terminal {
            background: #000;
            border: 2px solid #00ff00;
            border-radius: 5px;
            padding: 20px;
            margin: 20px 0;
        }

        .terminal-line {
            color: #00ff00;
            margin: 5px 0;
            font-family: 'Courier New', monospace;
        }

        .cursor {
            display: inline-block;
            width: 10px;
            height: 20px;
            background: #00ff00;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        @media (max-width: 768px) {
            .solar-system {
                width: 350px;
                height: 350px;
            }
            .orbit-1 { width: 100px; height: 100px; }
            .orbit-2 { width: 150px; height: 150px; }
            .orbit-3 { width: 200px; height: 200px; }
            .orbit-4 { width: 250px; height: 250px; }
            .orbit-5 { width: 300px; height: 300px; }
            .sun { width: 80px; height: 80px; }
            .sun img { width: 60px; height: 60px; }
            .planet { width: 40px; height: 40px; }
            .planet img { width: 30px; height: 30px; }
        }
    </style>
</head>
<body>
    <div class="header">
        <img src="https://i.postimg.cc/X7H4Dr5Z/1000009494.webp" alt="MR-TAN" class="profile-img">
        <h1>💀 MR-TAN 💀</h1>
        <div class="typing-text" id="typing"></div>
        <p style="margin-top: 10px;">🇧🇩 Bangladesh | Death Cyber Army</p>
    </div>

    <div class="solar-system-container">
        <h2 style="position: absolute; top: 20px; color: #00ff00; text-shadow: 0 0 20px #00ff00;">🌟 Tech Stack Solar System 🌟</h2>
        <div class="solar-system">
            <!-- Sun (Python) -->
            <div class="sun">
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python">
            </div>

            <!-- Orbit 1 - Bash -->
            <div class="orbit orbit-1">
                <div class="planet">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" alt="Bash">
                    <div class="planet-label">Bash</div>
                </div>
            </div>

            <!-- Orbit 2 - Linux -->
            <div class="orbit orbit-2">
                <div class="planet">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" alt="Linux">
                    <div class="planet-label">Linux</div>
                </div>
            </div>

            <!-- Orbit 3 - Git -->
            <div class="orbit orbit-3">
                <div class="planet">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git">
                    <div class="planet-label">Git</div>
                </div>
            </div>

            <!-- Orbit 4 - HTML5 -->
            <div class="orbit orbit-4">
                <div class="planet">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5">
                    <div class="planet-label">HTML5</div>
                </div>
            </div>

            <!-- Orbit 5 - CSS3 -->
            <div class="orbit orbit-5">
                <div class="planet">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3">
                    <div class="planet-label">CSS3</div>
                </div>
            </div>
        </div>
    </div>

    <div class="content">
        <div class="section">
            <h2>🎯 About Me</h2>
            <div class="terminal">
                <div class="terminal-line">$ whoami</div>
                <div class="terminal-line">> MR-TAN - Cybersecurity Enthusiast & Python Developer</div>
                <div class="terminal-line">$ cat mission.txt</div>
                <div class="terminal-line">> Leading Death Cyber Army</div>
                <div class="terminal-line">> Building bots, tools & automation</div>
                <div class="terminal-line">> Exploring cybersecurity frontiers</div>
                <div class="terminal-line">$ <span class="cursor"></span></div>
            </div>
        </div>

        <div class="section">
            <h2>🔥 Current Operations</h2>
            <div class="code-block">
<pre>class MrTan:
    def __init__(self):
        self.name = "MR-TAN"
        self.role = "Cybersecurity Researcher"
        self.team = "Death Cyber Army"
        self.skills = {
            'Python': '100%',
            'Cybersecurity': '90%',
            'Bot Development': '95%',
            'Linux': '85%',
            'Automation': '90%'
        }
    
    def current_projects(self):
        return [
            "Telegram Bots 🤖",
            "Automation Tools ⚡",
            "Security Research 🔒",
            "Team Leadership 👥"
        ]

warrior = MrTan()
print(warrior.current_projects())</pre>
            </div>
        </div>

        <div class="section">
            <h2>📡 Connect With Me</h2>
            <div class="social-links">
                <a href="https://www.facebook.com/MrT4N.Official" target="_blank">📘 Facebook</a>
                <a href="https://t.me/MrTan_official" target="_blank">✈️ Telegram</a>
                <a href="https://www.instagram.com/mrtan_0fficial" target="_blank">📸 Instagram</a>
                <a href="https://www.youtube.com/@MrTan_official" target="_blank">▶️ YouTube</a>
            </div>
        </div>

        <div class="section">
            <h2>💻 System Information</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>🖥️ Workstation Alpha</h3>
                    <p>OS: Windows 10 Pro</p>
                    <p>CPU: Intel Core i3</p>
                    <p>Status: 🟢 Online</p>
                </div>
                <div class="stat-card">
                    <h3>📱 Device Beta</h3>
                    <p>OS: Android 9</p>
                    <p>CPU: MTK MT6761</p>
                    <p>Status: 🟢 Online</p>
                </div>
                <div class="stat-card">
                    <h3>📱 Device Gamma</h3>
                    <p>OS: Android 14</p>
                    <p>CPU: MediaTek Helio G85</p>
                    <p>Status: 🟢 Online</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>⚡ Fun Fact</h2>
            <div class="terminal">
                <div class="terminal-line" id="funFact"></div>
            </div>
        </div>

        <div class="section" style="text-align: center;">
            <h2>💰 Support The Mission</h2>
            <a href="https://buymeacoffee.com/mrtan_official" target="_blank" style="display: inline-block; margin: 20px 0;">
                <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="60" alt="Buy Me A Coffee">
            </a>
        </div>
    </div>

    <div style="text-align: center; padding: 40px 20px; background: rgba(0, 0, 0, 0.5); border-top: 2px solid #00ff00;">
        <h2 style="color: #00ff00; text-shadow: 0 0 20px #00ff00;">💀 DEATH CYBER ARMY 💀</h2>
        <p style="color: #00ff00; margin: 10px 0;">Code. Hack. Repeat.</p>
        <p style="color: #00ff00;">Thanks for visiting! Stay curious, stay coding! ⚡</p>
    </div>

    <script>
        // Typing animation
        const texts = [
            "Ethical Hacker 🔐",
            "Python Developer 🐍",
            "Bot Creator 🤖",
            "Cybersecurity Researcher 💀",
            "Death Cyber Army ⚡"
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Fun facts
        const funFacts = [
            "💡 I debug with print() statements like a pro 😎",
            "☕ Coffee + Code = Magic 💻",
            "😅 I'm funny... sometimes",
            "💤 Sleep is just a process I terminate",
            "🐍 In Python we trust"
        ];
        
        document.getElementById('funFact').textContent = funFacts[Math.floor(Math.random() * funFacts.length)];
    </script>
</body>
</html>
