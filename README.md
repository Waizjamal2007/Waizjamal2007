<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Waiz Jamal Ashraf · NexoraWeb</title>

    <!-- Fonts & Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />

    <style>
        /* RESET & BASE – dark hacker/developer vibe */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0b0d15;
            background-image: radial-gradient(circle at 10% 20%, #131724 0%, #07090e 90%);
            font-family: 'Space Grotesk', sans-serif;
            color: #d0d9f0;
            min-height: 100vh;
            padding: 2rem 1rem;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* glitchy scanline overlay (subtle) */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(0deg,
                    rgba(0, 255, 200, 0.02) 0px,
                    rgba(0, 255, 200, 0.02) 2px,
                    transparent 2px,
                    transparent 6px);
            pointer-events: none;
            z-index: 999;
        }

        .container {
            max-width: 1100px;
            width: 100%;
            position: relative;
        }

        /* ----- TYPOGRAPHY & GLITCH ----- */
        .glow-text {
            text-shadow: 0 0 8px rgba(0, 255, 200, 0.3), 0 0 20px rgba(0, 255, 200, 0.1);
        }

        .terminal-prompt {
            font-family: 'Share Tech Mono', monospace;
            color: #7bffd6;
            letter-spacing: 0.5px;
        }

        .tag {
            display: inline-block;
            background: rgba(0, 255, 200, 0.08);
            border: 1px solid rgba(0, 255, 200, 0.2);
            border-radius: 30px;
            padding: 0.2rem 1rem;
            font-size: 0.75rem;
            font-weight: 600;
            color: #8effe0;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .section-title {
            font-size: 1.8rem;
            font-weight: 600;
            color: #d0f0ff;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            margin-bottom: 1.8rem;
            border-bottom: 1px solid rgba(0, 255, 200, 0.15);
            padding-bottom: 0.6rem;
        }
        .section-title i {
            color: #3affd0;
            font-size: 1.6rem;
        }

        /* ----- CARDS / BOXES (hacker style) ----- */
        .glass-panel {
            background: rgba(12, 18, 30, 0.7);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border: 1px solid rgba(0, 255, 200, 0.12);
            border-radius: 28px;
            padding: 2rem 1.8rem;
            box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.8), inset 0 0 30px rgba(0, 255, 200, 0.02);
            transition: 0.2s ease;
        }

        .glass-panel:hover {
            border-color: rgba(0, 255, 200, 0.3);
            box-shadow: 0 20px 50px -10px rgba(0, 255, 200, 0.05);
        }

        /* ----- HEADER (hacker + dev) ----- */
        .header-wrap {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 3rem;
        }

        .brand h1 {
            font-size: 2.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, #9afff0, #3affd0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -0.5px;
            line-height: 1.2;
        }

        .brand .sub {
            font-family: 'Share Tech Mono', monospace;
            color: #7aa9b0;
            font-size: 0.9rem;
            letter-spacing: 2px;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            flex-wrap: wrap;
        }
        .brand .sub i {
            color: #3affd0;
        }

        .badge-group {
            display: flex;
            gap: 0.8rem;
            flex-wrap: wrap;
        }
        .badge-group .badge {
            background: #131d2a;
            border: 1px solid #2b4a55;
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 600;
            color: #b5e6e0;
            letter-spacing: 0.3px;
        }
        .badge-group .badge i {
            margin-right: 6px;
            color: #3affd0;
        }

        /* QUOTE (prominent) */
        .quote-block {
            background: rgba(0, 255, 200, 0.02);
            border-left: 4px solid #3affd0;
            padding: 1.5rem 2rem;
            margin: 2rem 0 2.5rem 0;
            border-radius: 0 20px 20px 0;
            font-family: 'Share Tech Mono', monospace;
            font-size: 1.1rem;
            line-height: 1.6;
            color: #b4e6e0;
            box-shadow: 0 0 30px rgba(0, 255, 200, 0.02);
        }
        .quote-block i {
            color: #3affd0;
            margin-right: 10px;
        }
        .quote-author {
            margin-top: 0.5rem;
            font-size: 0.9rem;
            color: #74b8b0;
            letter-spacing: 1px;
        }

        /* SKILLS (bars + tags) */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
            gap: 1rem 1.2rem;
            margin-top: 0.5rem;
        }

        .skill-item {
            display: flex;
            flex-direction: column;
            gap: 0.2rem;
        }
        .skill-item .skill-label {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            font-weight: 500;
            color: #b0d0d0;
        }
        .skill-item .skill-label span:last-child {
            color: #7bffd6;
            font-family: 'Share Tech Mono', monospace;
        }

        .progress-bar-bg {
            width: 100%;
            height: 6px;
            background: #1a2636;
            border-radius: 20px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            border-radius: 20px;
            background: linear-gradient(90deg, #2cd4b0, #3affd0);
            width: 0%;
            box-shadow: 0 0 12px #3affd050;
        }

        /* special tag for "hacker" tools */
        .hacker-tag {
            display: inline-block;
            background: rgba(255, 70, 130, 0.08);
            border: 1px solid rgba(255, 70, 130, 0.25);
            border-radius: 40px;
            padding: 0.1rem 0.9rem;
            font-size: 0.65rem;
            font-weight: 600;
            color: #ff8aa0;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            margin: 0.2rem 0.2rem 0 0;
        }

        /* extra hacker/dev quote row */
        .hacker-row {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 1.5rem 2.5rem;
            margin: 2rem 0 1rem;
            font-family: 'Share Tech Mono', monospace;
            border-top: 1px dashed rgba(0, 255, 200, 0.1);
            padding-top: 1.8rem;
        }
        .hacker-row i {
            color: #3affd0;
            width: 1.6rem;
        }

        .footer-note {
            margin-top: 3rem;
            text-align: right;
            font-family: 'Share Tech Mono', monospace;
            font-size: 0.85rem;
            color: #3e6868;
            border-top: 1px solid rgba(0, 255, 200, 0.05);
            padding-top: 1.5rem;
            letter-spacing: 1px;
        }
        .footer-note strong {
            color: #7bffd6;
            font-weight: 500;
        }

        /* responsiveness */
        @media (max-width: 700px) {
            .brand h1 {
                font-size: 2.2rem;
            }
            .header-wrap {
                flex-direction: column;
                align-items: flex-start;
                gap: 1.2rem;
            }
            .quote-block {
                font-size: 0.95rem;
                padding: 1.2rem;
            }
            .skills-grid {
                grid-template-columns: 1fr 1fr;
            }
        }
        @media (max-width: 450px) {
            .skills-grid {
                grid-template-columns: 1fr;
            }
            .glass-panel {
                padding: 1.5rem 1rem;
            }
        }

        /* blinking cursor effect (extra) */
        .cursor-blink {
            display: inline-block;
            width: 10px;
            height: 2px;
            background: #3affd0;
            animation: blink 1s step-end infinite;
            margin-left: 8px;
        }
        @keyframes blink {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- HEADER with hacker/dev style -->
        <div class="header-wrap">
            <div class="brand">
                <h1>
                    <span class="glow-text">⧩ Waiz Jamal Ashraf</span>
                    <span style="font-size: 1.8rem; color: #3affd0;">|</span>
                    <span style="font-size: 1.6rem; background: linear-gradient(145deg, #b0f0e8, #3affd0); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">NexoraWeb</span>
                </h1>
                <div class="sub">
                    <i class="fas fa-terminal"></i> founder · lead architect
                    <span style="color: #4f7a7a;">|</span>
                    <i class="fas fa-skull"></i> hacker mindset
                    <span style="color: #4f7a7a;">|</span>
                    <i class="fas fa-code"></i> full-stack dev
                    <span class="cursor-blink"></span>
                </div>
            </div>
            <div class="badge-group">
                <span class="badge"><i class="fas fa-shield-alt"></i> Kali · nmap · mitm</span>
                <span class="badge"><i class="fas fa-brain"></i> AI Web Builder</span>
                <span class="badge"><i class="fas fa-cubes"></i> SAAS ecosystem</span>
            </div>
        </div>

        <!-- QUOTE (favorite) -->
        <div class="quote-block">
            <i class="fas fa-quote-left"></i>
            <span>
                the problem is far more greater than you think, it is not poverty or lack of direction, but the lack of will.
                if i do not change the mindset, the problem is me!
            </span>
            <div class="quote-author">
                <i class="fas fa-code-branch"></i> Waiz Jamal Ashraf · NexoraWeb
            </div>
        </div>

        <!-- about + hacker/dev one-liner -->
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; margin-bottom: 2rem;">
            <div style="display: flex; gap: 0.5rem; flex-wrap: wrap;">
                <span class="tag"><i class="fas fa-bolt"></i> full-stack</span>
                <span class="tag"><i class="fas fa-robot"></i> AI / automation</span>
                <span class="tag"><i class="fas fa-user-secret"></i> pentest · spoof</span>
                <span class="tag"><i class="fas fa-cloud"></i> deployment · cPanel</span>
            </div>
            <div style="font-family: 'Share Tech Mono', monospace; color: #5b9490; font-size: 0.8rem;">
                <i class="fas fa-arrow-right" style="color: #3affd0;"></i> today it is them, tomorrow it will be me.
            </div>
        </div>

        <!-- SKILLS (with progress bars & hacker tags) -->
        <div class="glass-panel" style="margin-bottom: 2.5rem;">
            <div class="section-title">
                <i class="fas fa-microchip"></i>  skills · arsenal
                <span style="margin-left: auto; font-size: 0.7rem; background: #131d2a; padding: 0.2rem 1.2rem; border-radius: 40px; border: 1px solid #1f3e44; font-weight: 400;">
                    <i class="fas fa-terminal"></i> dev + hack
                </span>
            </div>

            <div class="skills-grid">
                <!-- Hardcoded skills with values (matching the list) -->
                <div class="skill-item"><div class="skill-label"><span>HTML</span><span>70%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:70%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>CSS</span><span>65%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:65%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>JavaScript</span><span>85%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:85%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Bootstrap</span><span>65%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:65%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Laravel</span><span>88%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:88%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Excel</span><span>75%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:75%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>MySQL</span><span>50%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:50%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>PHP</span><span>60%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:60%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>ASP.NET Core</span><span>55%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:55%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Entity Framework</span><span>72%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:72%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>API Integration</span><span>90%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:90%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>cPanel / Live</span><span>58%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:58%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Angular</span><span>60%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:60%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>TypeScript</span><span>62%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:62%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>C#</span><span>55%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:55%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Python</span><span>75%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:75%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>React</span><span>85%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:85%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>MongoDB (Atlas)</span><span>50%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:50%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>Node.js</span><span>65%</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:65%"></div></div></div>
                <div class="skill-item"><div class="skill-label"><span>C++</span><span>—</span></div><div class="progress-bar-bg"><div class="progress-fill" style="width:40%"></div></div></div>
            </div>

            <!-- hacker/kali extra row (displayed as tags) -->
            <div style="margin-top: 1.8rem; display: flex; flex-wrap: wrap; gap: 0.6rem 1rem; border-top: 1px solid rgba(0,255,200,0.05); padding-top: 1.5rem;">
                <span class="hacker-tag"><i class="fas fa-skull"></i> Kali Linux</span>
                <span class="hacker-tag"><i class="fas fa-network-wired"></i> nmap</span>
                <span class="hacker-tag"><i class="fas fa-user-secret"></i> network spoofing</span>
                <span class="hacker-tag"><i class="fas fa-bolt"></i> DDoS (simulation)</span>
                <span class="hacker-tag"><i class="fas fa-map-pin"></i> IP founding</span>
                <span class="hacker-tag"><i class="fas fa-fish"></i> zphisher</span>
                <span class="hacker-tag"><i class="fas fa-globe"></i> Tor browser</span>
                <span class="hacker-tag"><i class="fas fa-exchange-alt"></i> mitm</span>
                <span class="hacker-tag"><i class="fas fa-bug"></i> APK bug file</span>
            </div>
        </div>

        <!-- extra hacker/dev row: founder + mindset -->
        <div class="hacker-row">
            <span><i class="fas fa-flag"></i> founder · NexoraWeb (start-up 2025)</span>
            <span><i class="fas fa-cogs"></i> SAAS ecosystem · AI web builder · theme marketplace</span>
            <span><i class="fas fa-code"></i> 100% architecture · UI/UX · deployment</span>
            <span style="color: #3affd0;"><i class="fas fa-quote-right"></i> “the lack of will is the only failure”</span>
        </div>

        <!-- extra line: today / tomorrow (the quote from description) -->
        <div style="font-family: 'Share Tech Mono', monospace; text-align: center; margin: 1.8rem 0 0.8rem; color: #5f9390; font-size: 0.95rem; border: 1px dashed rgba(0,255,200,0.1); padding: 0.8rem; border-radius: 60px; background: rgba(0,255,200,0.02);">
            <i class="fas fa-forward" style="color: #3affd0; margin-right: 12px;"></i>
            today it is them, tomorrow it will be me.
            <i class="fas fa-backward" style="color: #3affd0; margin-left: 12px;"></i>
        </div>

        <!-- footer (no "made with love" – just founder signature) -->
        <div class="footer-note">
            <i class="fas fa-terminal" style="color: #3affd0; margin-right: 8px;"></i>
            Waiz Jamal Ashraf  <span style="color: #3e6868;">|</span>  Founder Of NexoraWeb
            <span style="display: inline-block; margin-left: 1.5rem; color: #3e6868; font-size: 0.7rem;">
                <i class="fas fa-shield-halved"></i>  hacker · developer · builder
            </span>
        </div>

    </div>
    <!-- end container -->

</body>
</html>
