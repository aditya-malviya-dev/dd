<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VAAS Connections</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
         :root {
            --bg: #10121a;
            --surface: #1a1d29;
            --surface-2: #232739;
            --border: #2c3145;
            --text: #e9ebf3;
            --text-muted: #8891ac;
            --mint: #6ee7b7;
            --amber: #fbbf24;
            --indigo: #8b93f8;
            --rose: #fb7185;
        }
        
        * {
            box-sizing: border-box;
        }
        
        html,
        body {
            margin: 0;
            padding: 0;
        }
        
        body {
            background: radial-gradient(circle at 15% 0%, rgba(139, 147, 248, 0.10), transparent 45%), radial-gradient(circle at 85% 10%, rgba(110, 231, 183, 0.08), transparent 40%), var(--bg);
            color: var(--text);
            font-family: 'Inter', sans-serif;
            min-height: 100vh;
        }
        
         ::selection {
            background: var(--mint);
            color: #0a0c12;
        }
        
        .mono {
            font-family: 'JetBrains Mono', monospace;
        }
        
        .display {
            font-family: 'Space Grotesk', sans-serif;
        }
        /* ---------- HEADER ---------- */
        
        header {
            position: sticky;
            top: 0;
            z-index: 50;
            background: rgba(16, 18, 26, 0.88);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border);
            padding: 14px 24px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
            flex-wrap: wrap;
        }
        
        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .brand-mark {
            width: 38px;
            height: 38px;
            border-radius: 10px;
            background: linear-gradient(135deg, var(--mint), var(--indigo));
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Space Grotesk';
            font-weight: 700;
            color: #0a0c12;
            font-size: 15px;
            flex-shrink: 0;
        }
        
        .brand h1 {
            font-family: 'Space Grotesk';
            font-size: 19px;
            margin: 0;
            letter-spacing: 0.2px;
        }
        
        .brand span {
            display: block;
            font-size: 11px;
            color: var(--text-muted);
            font-family: 'JetBrains Mono';
            margin-top: 1px;
        }
        
        nav {
            display: flex;
            gap: 4px;
            background: var(--surface);
            padding: 4px;
            border-radius: 12px;
            border: 1px solid var(--border);
            flex-wrap: wrap;
        }
        
        nav button {
            background: transparent;
            border: none;
            color: var(--text-muted);
            padding: 8px 14px;
            border-radius: 9px;
            font-family: 'Inter';
            font-weight: 600;
            font-size: 13.5px;
            cursor: pointer;
            transition: all .15s ease;
        }
        
        nav button:hover {
            color: var(--text);
        }
        
        nav button.active {
            background: var(--surface-2);
            color: var(--mint);
        }
        
        .whoami {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 12.5px;
            color: var(--text-muted);
        }
        
        .whoami select {
            background: var(--surface-2);
            color: var(--text);
            border: 1px solid var(--border);
            padding: 7px 10px;
            border-radius: 8px;
            font-family: 'JetBrains Mono';
            font-size: 12.5px;
            cursor: pointer;
        }
        
        main {
            max-width: 1180px;
            margin: 0 auto;
            padding: 28px 24px 80px;
        }
        
        .view {
            display: none;
        }
        
        .view.active {
            display: block;
            animation: fade .35s ease;
        }
        
        @keyframes fade {
            from {
                opacity: 0;
                transform: translateY(6px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .section-head {
            margin-bottom: 22px;
        }
        
        .eyebrow {
            font-family: 'JetBrains Mono';
            font-size: 11.5px;
            color: var(--mint);
            letter-spacing: 1px;
            text-transform: uppercase;
            margin: 0 0 6px;
        }
        
        .section-head h2 {
            font-family: 'Space Grotesk';
            font-size: 26px;
            margin: 0 0 6px;
        }
        
        .section-head p {
            color: var(--text-muted);
            margin: 0;
            font-size: 14.5px;
            max-width: 640px;
        }
        /* ---------- TEAM CARDS ---------- */
        
        .team-block {
            margin-bottom: 30px;
        }
        
        .team-block h3 {
            font-family: 'JetBrains Mono';
            font-size: 12px;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin: 0 0 12px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .team-block h3::after {
            content: '';
            flex: 1;
            height: 1px;
            background: var(--border);
        }
        
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
            gap: 14px;
        }
        
        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 14px;
            padding: 16px;
            position: relative;
            overflow: hidden;
            transition: border-color .15s ease, transform .15s ease;
        }
        
        .card:hover {
            border-color: #3a4060;
            transform: translateY(-2px);
        }
        
        .card.me {
            border-color: var(--mint);
        }
        
        .card.me::before {
            content: 'YOU';
            position: absolute;
            top: 10px;
            right: 10px;
            font-family: 'JetBrains Mono';
            font-size: 9.5px;
            color: #0a0c12;
            background: var(--mint);
            padding: 2px 6px;
            border-radius: 5px;
            font-weight: 700;
            letter-spacing: 0.5px;
        }
        
        .card-top {
            display: flex;
            gap: 12px;
            align-items: flex-start;
        }
        
        .avatar {
            width: 46px;
            height: 46px;
            border-radius: 10px;
            flex-shrink: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Space Grotesk';
            font-weight: 700;
            font-size: 16px;
            color: #0a0c12;
        }
        
        .card-name {
            font-family: 'Space Grotesk';
            font-weight: 600;
            font-size: 15.5px;
            margin: 0;
        }
        
        .nickname {
            font-family: 'JetBrains Mono';
            font-size: 11px;
            color: var(--indigo);
            margin-top: 3px;
            display: inline-block;
        }
        
        .admin-tag {
            font-family: 'JetBrains Mono';
            font-size: 9.5px;
            color: var(--amber);
            border: 1px solid rgba(251, 191, 36, 0.4);
            padding: 1px 6px;
            border-radius: 5px;
            margin-top: 6px;
            display: inline-block;
        }
        
        .career-row {
            margin-top: 12px;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        
        .career-pill {
            font-size: 12px;
            background: var(--surface-2);
            border: 1px solid var(--border);
            color: var(--text);
            padding: 5px 10px;
            border-radius: 999px;
            flex: 1;
            cursor: text;
        }
        
        .career-pill:focus {
            outline: 1.5px solid var(--mint);
            border-color: var(--mint);
        }
        
        .progress-row {
            margin-top: 12px;
        }
        
        .progress-label {
            display: flex;
            justify-content: space-between;
            font-size: 10.5px;
            color: var(--text-muted);
            font-family: 'JetBrains Mono';
            margin-bottom: 4px;
        }
        
        .bar {
            height: 6px;
            background: var(--surface-2);
            border-radius: 99px;
            overflow: hidden;
        }
        
        .bar-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--mint), var(--indigo));
            border-radius: 99px;
            transition: width .4s ease;
        }
        
        .card-btn {
            margin-top: 12px;
            width: 100%;
            padding: 8px;
            border-radius: 8px;
            border: 1px solid var(--border);
            background: var(--surface-2);
            color: var(--text);
            font-family: 'Inter';
            font-weight: 600;
            font-size: 12.5px;
            cursor: pointer;
        }
        
        .card-btn:hover {
            border-color: var(--mint);
            color: var(--mint);
        }
        /* ---------- CARD SURFACE ---------- */
        
        .panel {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 20px;
        }
        /* ---------- TARGETS ---------- */
        
        .target-form {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 22px;
        }
        
        select,
        input[type=text],
        textarea {
            background: var(--surface-2);
            border: 1px solid var(--border);
            color: var(--text);
            padding: 10px 12px;
            border-radius: 9px;
            font-family: 'Inter';
            font-size: 13.5px;
        }
        
        select:focus,
        input:focus,
        textarea:focus {
            outline: 1.5px solid var(--mint);
            border-color: var(--mint);
        }
        
        .target-form select {
            min-width: 170px;
        }
        
        .target-form input[type=text] {
            flex: 1;
            min-width: 220px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--mint), #4fd1a5);
            color: #0a0c12;
            border: none;
            padding: 10px 18px;
            border-radius: 9px;
            font-family: 'Inter';
            font-weight: 700;
            font-size: 13.5px;
            cursor: pointer;
        }
        
        .btn-primary:hover {
            filter: brightness(1.08);
        }
        
        .btn-primary:disabled {
            opacity: .5;
            cursor: not-allowed;
        }
        
        .day-group {
            margin-bottom: 18px;
        }
        
        .day-label {
            font-family: 'JetBrains Mono';
            font-size: 11.5px;
            color: var(--text-muted);
            text-transform: uppercase;
            margin-bottom: 8px;
            letter-spacing: 0.5px;
        }
        
        .target-item {
            display: flex;
            align-items: flex-start;
            gap: 12px;
            padding: 11px 12px;
            background: var(--surface-2);
            border-radius: 10px;
            border: 1px solid var(--border);
            margin-bottom: 8px;
        }
        
        .target-item input[type=checkbox] {
            margin-top: 3px;
            accent-color: var(--mint);
            width: 16px;
            height: 16px;
            cursor: pointer;
            flex-shrink: 0;
        }
        
        .target-item.done .t-text {
            text-decoration: line-through;
            color: var(--text-muted);
        }
        
        .t-who {
            font-family: 'JetBrains Mono';
            font-size: 11px;
            color: var(--indigo);
            margin-bottom: 2px;
        }
        
        .t-text {
            font-size: 14px;
        }
        
        .empty {
            color: var(--text-muted);
            font-size: 13.5px;
            font-style: italic;
            padding: 14px 0;
        }
        /* ---------- DASHBOARD ---------- */
        
        .dash-select-row {
            display: flex;
            align-items: center;
            gap: 14px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        
        .dash-nick {
            font-family: 'JetBrains Mono';
            color: var(--indigo);
            font-size: 13px;
        }
        
        .dash-progress-wrap {
            flex: 1;
            min-width: 200px;
        }
        
        .skill-group {
            margin-bottom: 20px;
        }
        
        .skill-group h4 {
            font-family: 'JetBrains Mono';
            font-size: 11.5px;
            color: var(--amber);
            text-transform: uppercase;
            letter-spacing: 0.8px;
            margin: 0 0 10px;
        }
        
        .skill-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
            gap: 8px;
        }
        
        .skill-item {
            display: flex;
            align-items: center;
            gap: 9px;
            background: var(--surface-2);
            border: 1px solid var(--border);
            padding: 9px 11px;
            border-radius: 9px;
            cursor: pointer;
            font-size: 13.5px;
            transition: border-color .15s;
        }
        
        .skill-item:hover {
            border-color: #3a4060;
        }
        
        .skill-item input {
            accent-color: var(--mint);
            width: 15px;
            height: 15px;
            cursor: pointer;
        }
        
        .skill-item.checked {
            border-color: var(--mint);
            background: rgba(110, 231, 183, 0.06);
        }
        
        .skill-item.checked span {
            color: var(--mint);
        }
        /* ---------- CHAT ---------- */
        
        .chat-wrap {
            display: flex;
            flex-direction: column;
            height: 520px;
        }
        
        .chat-log {
            flex: 1;
            overflow-y: auto;
            padding: 6px 4px 14px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .msg {
            max-width: 72%;
            padding: 9px 13px;
            border-radius: 12px;
            background: var(--surface-2);
            border: 1px solid var(--border);
            align-self: flex-start;
        }
        
        .msg.mine {
            align-self: flex-end;
            background: rgba(110, 231, 183, 0.10);
            border-color: rgba(110, 231, 183, 0.35);
        }
        
        .msg-meta {
            font-family: 'JetBrains Mono';
            font-size: 10.5px;
            color: var(--indigo);
            margin-bottom: 3px;
            display: flex;
            gap: 8px;
        }
        
        .msg-meta .time {
            color: var(--text-muted);
        }
        
        .msg-text {
            font-size: 14px;
            line-height: 1.4;
            word-wrap: break-word;
        }
        
        .chat-input-row {
            display: flex;
            gap: 10px;
            margin-top: 10px;
            border-top: 1px solid var(--border);
            padding-top: 14px;
        }
        
        .chat-input-row input[type=text] {
            flex: 1;
        }
        
        .chat-input-row select {
            width: 150px;
        }
        /* ---------- MOTIVATION ---------- */
        
        .quote-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
            gap: 14px;
            margin-bottom: 26px;
        }
        
        .quote-card {
            background: linear-gradient(160deg, var(--surface), var(--surface-2));
            border: 1px solid var(--border);
            border-radius: 14px;
            padding: 18px;
            position: relative;
        }
        
        .quote-card::before {
            content: '"';
            font-family: 'Space Grotesk';
            font-size: 42px;
            color: var(--mint);
            opacity: .35;
            line-height: 1;
            position: absolute;
            top: 6px;
            left: 12px;
        }
        
        .quote-text {
            font-family: 'Space Grotesk';
            font-size: 15px;
            margin: 20px 0 10px;
            line-height: 1.4;
        }
        
        .quote-tag {
            font-family: 'JetBrains Mono';
            font-size: 10.5px;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .note-form {
            display: flex;
            gap: 10px;
            margin-bottom: 16px;
            flex-wrap: wrap;
        }
        
        .note-form select {
            min-width: 160px;
        }
        
        .note-form input {
            flex: 1;
            min-width: 220px;
        }
        
        .notes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 12px;
        }
        
        .note-card {
            background: var(--surface-2);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 14px;
            border-left: 3px solid var(--amber);
        }
        
        .note-card p {
            margin: 0 0 8px;
            font-size: 13.5px;
            line-height: 1.4;
        }
        
        .note-card .t-who {
            margin-bottom: 0;
        }
        
         ::-webkit-scrollbar {
            width: 8px;
        }
        
         ::-webkit-scrollbar-track {
            background: transparent;
        }
        
         ::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 8px;
        }
        
        .loading-line {
            color: var(--text-muted);
            font-size: 13px;
            font-family: 'JetBrains Mono';
            padding: 20px 0;
        }
        
        @media (max-width:640px) {
            header {
                padding: 12px 14px;
            }
            main {
                padding: 20px 14px 60px;
            }
            .chat-wrap {
                height: 420px;
            }
        }
    </style>
</head>

<body>

    <header>
        <div class="brand">
            <div class="brand-mark">V/S</div>
            <div>
                <h1>VAAS Connections</h1>
                <span>16 builders &middot; 1 team</span>
            </div>
        </div>
        <nav id="tabNav">
            <button data-view="team" class="active">Team</button>
            <button data-view="targets">Daily Targets</button>
            <button data-view="dashboard">Skill Dashboard</button>
            <button data-view="chat">Chat</button>
            <button data-view="motivation">Motivation</button>
        </nav>
        <div class="whoami">
            <span>You are</span>
            <select id="whoamiSelect"></select>
        </div>
    </header>

    <main>

        <!-- TEAM VIEW -->
        <section class="view active" id="view-team">
            <div class="section-head">
                <p class="eyebrow">Roster</p>
                <h2>Who's building</h2>
                <p>Every member gets a callsign, a dream career tag, and a live progress bar pulled from their skill dashboard. Tap a career tag to edit it.</p>
            </div>
            <div class="team-block">
                <h3>Admins</h3>
                <div class="grid" id="adminGrid"></div>
            </div>
            <div class="team-block">
                <h3>Members</h3>
                <div class="grid" id="memberGrid"></div>
            </div>
        </section>

        <!-- TARGETS VIEW -->
        <section class="view" id="view-targets">
            <div class="section-head">
                <p class="eyebrow">Daily log</p>
                <h2>Today's targets</h2>
                <p>Post what you're tackling today. Tick it off once it's done — everyone can see the whole team's momentum here.</p>
            </div>
            <div class="panel">
                <div class="target-form">
                    <select id="targetWho"></select>
                    <input type="text" id="targetInput" placeholder="e.g. Finish CSS flexbox module + 2 LeetCode easy">
                    <button class="btn-primary" id="targetSubmit">Add target</button>
                </div>
                <div id="targetFeed">
                    <div class="loading-line">loading targets…</div>
                </div>
            </div>
        </section>

        <!-- DASHBOARD VIEW -->
        <section class="view" id="view-dashboard">
            <div class="section-head">
                <p class="eyebrow">Skill tracker</p>
                <h2>Per-member dashboard</h2>
                <p>Check off every skill as you learn it. This is exactly what powers the progress bar on the Team page.</p>
            </div>
            <div class="panel">
                <div class="dash-select-row">
                    <select id="dashWho"></select>
                    <span class="dash-nick mono" id="dashNick"></span>
                    <div class="dash-progress-wrap">
                        <div class="progress-label"><span id="dashProgressLabel">0 / 0 skills</span><span id="dashProgressPct">0%</span></div>
                        <div class="bar">
                            <div class="bar-fill" id="dashProgressBar" style="width:0%"></div>
                        </div>
                    </div>
                </div>
                <div id="dashGroups">
                    <div class="loading-line">loading skills…</div>
                </div>
            </div>
        </section>

        <!-- CHAT VIEW -->
        <section class="view" id="view-chat">
            <div class="section-head">
                <p class="eyebrow">Team chat</p>
                <h2>Say something</h2>
                <p>Shared with all 16 of you. Refreshes automatically.</p>
            </div>
            <div class="panel chat-wrap">
                <div class="chat-log" id="chatLog">
                    <div class="loading-line">loading messages…</div>
                </div>
                <div class="chat-input-row">
                    <select id="chatWho"></select>
                    <input type="text" id="chatInput" placeholder="Type a message…">
                    <button class="btn-primary" id="chatSend">Send</button>
                </div>
            </div>
        </section>

        <!-- MOTIVATION VIEW -->
        <section class="view" id="view-motivation">
            <div class="section-head">
                <p class="eyebrow">Fuel</p>
                <h2>Motivational thoughts</h2>
                <p>Some lines to keep you going, plus a shared board for anything the team wants to add.</p>
            </div>
            <div class="quote-grid" id="quoteGrid"></div>

            <div class="panel">
                <h3 style="font-family:'Space Grotesk'; font-size:16px; margin:0 0 14px;">Drop a note for the team</h3>
                <div class="note-form">
                    <select id="noteWho"></select>
                    <input type="text" id="noteInput" placeholder="Something that's keeping you motivated…">
                    <button class="btn-primary" id="noteSubmit">Post</button>
                </div>
                <div class="notes-grid" id="notesGrid">
                    <div class="loading-line">loading notes…</div>
                </div>
            </div>
        </section>

    </main>

    <script type="module">

        import { initializeApp } from "firebase/app";
        import { getAnalytics } from "firebase/analytics"; 

        const firebaseConfig = {
        apiKey: "AIzaSyCChGx74Uq0oCfMGYSjZoJ2NEaGIMG413g",
        authDomain: "aditya-6415c.firebaseapp.com",
        projectId: "aditya-6415c",
        storageBucket: "aditya-6415c.firebasestorage.app",
        messagingSenderId: "843792151532",
        appId: "1:843792151532:web:a82c2d136a965180b886c9",
        measurementId: "G-0X0ELSLZRL"
        };

        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const analytics = getAnalytics(app);
    
        (function() {

                const TEAM = [{
                    name: "Vanshika Sharma",
                    nickname: "The Architect",
                    role: "admin",
                    career: "Full-Stack Architect"
                }, {
                    name: "Ansh Jain",
                    nickname: "The Strategist",
                    role: "admin",
                    career: "Product Manager"
                }, {
                    name: "Aditya Malviya",
                    nickname: "The Debugger",
                    role: "admin",
                    career: "Backend Engineer"
                }, {
                    name: "Sanchee Gyanchandani",
                    nickname: "The Visionary",
                    role: "admin",
                    career: "AI Researcher"
                }, {
                    name: "Vaishnavi",
                    nickname: "The Pixel Perfectionist",
                    role: "member",
                    career: "UI/UX Designer"
                }, {
                    name: "Aman",
                    nickname: "The Code Whisperer",
                    role: "member",
                    career: "Software Engineer"
                }, {
                    name: "Keerthana",
                    nickname: "The Logic Queen",
                    role: "member",
                    career: "Data Scientist"
                }, {
                    name: "Vedant",
                    nickname: "The Algorithm Ace",
                    role: "member",
                    career: "Competitive Programmer"
                }, {
                    name: "Reya",
                    nickname: "The UI Enchantress",
                    role: "member",
                    career: "Frontend Developer"
                }, {
                    name: "Vivaan",
                    nickname: "The Byte Master",
                    role: "member",
                    career: "Systems Engineer"
                }, {
                    name: "Daksh",
                    nickname: "The Syntax Sniper",
                    role: "member",
                    career: "Cybersecurity Analyst"
                }, {
                    name: "Prachiti",
                    nickname: "The Data Diva",
                    role: "member",
                    career: "Data Analyst"
                }, {
                    name: "Nandini",
                    nickname: "The Bug Hunter",
                    role: "member",
                    career: "QA / Test Engineer"
                }, {
                    name: "Azaan",
                    nickname: "The Stack Overflow Surfer",
                    role: "member",
                    career: "Cloud Engineer"
                }, {
                    name: "Sahil",
                    nickname: "The Terminal Titan",
                    role: "member",
                    career: "DevOps Engineer"
                }, {
                    name: "Shubhi",
                    nickname: "The Function Fixer",
                    role: "member",
                    career: "Mobile App Developer"
                }, ];

                const SKILL_GROUPS = [{
                    group: "Foundations",
                    items: ["HTML", "CSS", "JavaScript", "Git & GitHub"]
                }, {
                    group: "Languages",
                    items: ["Python", "C++", "Java"]
                }, {
                    group: "Web Development",
                    items: ["React.js", "Node.js", "REST APIs"]
                }, {
                    group: "CS Core",
                    items: ["Data Structures & Algorithms", "DBMS", "Operating Systems", "Computer Networks"]
                }, {
                    group: "Extras",
                    items: ["SQL", "System Design Basics", "Competitive Programming"]
                }, ];
                const ALL_SKILLS = SKILL_GROUPS.flatMap(g => g.items);

                const QUOTES = [{
                    text: "Every bug you squash today is a shortcut you build for tomorrow.",
                    tag: "on debugging"
                }, {
                    text: "Consistency compiles. One target a day builds the whole project.",
                    tag: "on momentum"
                }, {
                    text: "You don't need to know everything — you need to know what to Google next.",
                    tag: "on learning"
                }, {
                    text: "Nobody ships perfect code on the first commit. Push, then polish.",
                    tag: "on shipping"
                }, {
                    text: "Your dream career is just today's checklist, repeated for a year.",
                    tag: "on goals"
                }, {
                    text: "Stuck for an hour? Ask the team. That's what VAAS Connections is for.",
                    tag: "on teamwork"
                }, ];

                const AVATAR_GRADIENTS = [
                    ["#6ee7b7", "#3b82f6"],
                    ["#fbbf24", "#fb7185"],
                    ["#8b93f8", "#6ee7b7"],
                    ["#fb7185", "#fbbf24"],
                    ["#38bdf8", "#8b93f8"],
                    ["#34d399", "#059669"],
                ];

                function gradientFor(name) {
                    let h = 0;
                    for (let i = 0; i < name.length; i++) h = (h * 31 + name.charCodeAt(i)) >>> 0;
                    const [a, b] = AVATAR_GRADIENTS[h % AVATAR_GRADIENTS.length];
                    return `linear-gradient(135deg, ${a}, ${b})`;
                }

                function initials(name) {
                    return name.split(' ').map(w => w[0]).join('').slice(0, 2).toUpperCase();
                }

                function slug(name) {
                    return name.toLowerCase().replace(/[^a-z]+/g, '-');
                }

                function escapeHtml(s) {
                    const d = document.createElement('div');
                    d.innerText = s;
                    return d.innerHTML;
                }

                function timeStr(ts) {
                    const d = new Date(ts);
                    return d.toLocaleTimeString([], {
                        hour: '2-digit',
                        minute: '2-digit'
                    });
                }

                function dateStr(ts) {
                    const d = new Date(ts);
                    const today = new Date();
                    const isToday = d.toDateString() === today.toDateString();
                    if (isToday) return 'Today';
                    return d.toLocaleDateString([], {
                        weekday: 'short',
                        month: 'short',
                        day: 'numeric'
                    });
                }

                let currentUser = TEAM[4].name; // default to first member

                // ---------- storage helpers ----------
                // ---------- storage helpers (FIXED using LocalStorage) ----------
                async function getJSON(key, fallback, shared) {
                    try {
                        const value = localStorage.getItem(key);
                        if (!value) return fallback;
                        return JSON.parse(value);
                    } catch (e) {
                        return fallback;
                    }
                }
                async function setJSON(key, value, shared) {
                    try {
                        localStorage.setItem(key, JSON.stringify(value));
                        return true;
                    } catch (e) {
                        console.error('storage set failed', key, e);
                        return false;
                    }
                }

                // ---------- populate all "who" selects ----------
                function buildSelectOptions() {
                    return TEAM.map(m => `<option value="${escapeHtml(m.name)}">${escapeHtml(m.name)}${m.role==='admin' ? ' (admin)' : ''}</option>`).join('');
                }
                document.querySelectorAll('#whoamiSelect, #targetWho, #dashWho, #chatWho, #noteWho').forEach(sel => {
                    sel.innerHTML = buildSelectOptions();
                });
                document.getElementById('whoamiSelect').value = currentUser;
                document.getElementById('targetWho').value = currentUser;
                document.getElementById('dashWho').value = currentUser;
                document.getElementById('chatWho').value = currentUser;
                document.getElementById('noteWho').value = currentUser;

                document.getElementById('whoamiSelect').addEventListener('change', e => {
                    currentUser = e.target.value;
                    ['targetWho', 'dashWho', 'chatWho', 'noteWho'].forEach(id => {
                        document.getElementById(id).value = currentUser;
                    });
                    renderTeam();
                    if (document.getElementById('view-dashboard').classList.contains('active')) loadDashboard();
                });

                // ---------- nav ----------
                document.getElementById('tabNav').addEventListener('click', e => {
                    const btn = e.target.closest('button[data-view]');
                    if (!btn) return;
                    document.querySelectorAll('#tabNav button').forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
                    document.getElementById('view-' + btn.dataset.view).classList.add('active');
                    if (btn.dataset.view === 'targets') loadTargets();
                    if (btn.dataset.view === 'dashboard') loadDashboard();
                    if (btn.dataset.view === 'chat') loadChat();
                    if (btn.dataset.view === 'motivation') loadNotes();
                });

                // ---------- TEAM VIEW ----------
                async function computeProgress(name) {
                    const data = await getJSON('skills:' + slug(name), {}, true);
                    const checked = ALL_SKILLS.filter(s => data[s]).length;
                    return {
                        checked,
                        total: ALL_SKILLS.length
                    };
                }

                function cardHTML(m, progress, career) {
                    const pct = Math.round((progress.checked / progress.total) * 100);
                    return `
      <div class="card ${m.name===currentUser ? 'me':''}" data-name="${escapeHtml(m.name)}">
        <div class="card-top">
          <div class="avatar" style="background:${gradientFor(m.name)}">${initials(m.name)}</div>
          <div>
            <p class="card-name">${escapeHtml(m.name)}</p>
            <span class="nickname">#${slug(m.nickname)}</span><br>
            ${m.role==='admin' ? '<span class="admin-tag">ADMIN</span>' : ''}
          </div>
        </div>
        <div class="career-row">
          <div class="career-pill mono" contenteditable="true" data-role="career" data-name="${escapeHtml(m.name)}">${escapeHtml(career)}</div>
        </div>
        <div class="progress-row">
          <div class="progress-label"><span>skills</span><span>${progress.checked}/${progress.total}</span></div>
          <div class="bar"><div class="bar-fill" style="width:${pct}%"></div></div>
        </div>
        <button class="card-btn" data-role="viewdash" data-name="${escapeHtml(m.name)}">Open dashboard →</button>
      </div>`;
                }

                async function renderTeam() {
                    const admins = TEAM.filter(m => m.role === 'admin');
                    const members = TEAM.filter(m => m.role === 'member');
                    const careers = await getJSON('careers', {}, true);

                    const [adminCards, memberCards] = await Promise.all([
                        Promise.all(admins.map(async m => cardHTML(m, await computeProgress(m.name), careers[m.name] || m.career))),
                        Promise.all(members.map(async m => cardHTML(m, await computeProgress(m.name), careers[m.name] || m.career))),
                    ]);
                    document.getElementById('adminGrid').innerHTML = adminCards.join('');
                    document.getElementById('memberGrid').innerHTML = memberCards.join('');
                }

                document.getElementById('view-team').addEventListener('click', e => {
                    const btn = e.target.closest('[data-role="viewdash"]');
                    if (btn) {
                        document.getElementById('dashWho').value = btn.dataset.name;
                        document.querySelectorAll('#tabNav button').forEach(b => b.classList.remove('active'));
                        document.querySelector('#tabNav button[data-view="dashboard"]').classList.add('active');
                        document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
                        document.getElementById('view-dashboard').classList.add('active');
                        loadDashboard();
                    }
                });
                document.getElementById('view-team').addEventListener('blur', async e => {
                    const el = e.target.closest('[data-role="career"]');
                    if (!el) return;
                    const careers = await getJSON('careers', {}, true);
                    careers[el.dataset.name] = el.innerText.trim();
                    await setJSON('careers', careers, true);
                }, true);

                // ---------- TARGETS VIEW ----------
                async function loadTargets() {
                    const list = await getJSON('targets', [], true);
                    renderTargets(list);
                }

                function renderTargets(list) {
                    const el = document.getElementById('targetFeed');
                    if (list.length === 0) {
                        el.innerHTML = '<div class="empty">No targets posted yet. Be the first today.</div>';
                        return;
                    }
                    const sorted = [...list].sort((a, b) => b.ts - a.ts);
                    const groups = {};
                    sorted.forEach(t => {
                        const d = dateStr(t.ts);
                        groups[d] = groups[d] || [];
                        groups[d].push(t);
                    });
                    el.innerHTML = Object.entries(groups).map(([day, items]) => `
      <div class="day-group">
        <div class="day-label">${day}</div>
        ${items.map(t=>`
          <div class="target-item ${t.done ? 'done':''}" data-id="${t.id}">
            <input type="checkbox" ${t.done?'checked':''} data-role="toggle-target" data-id="${t.id}">
            <div>
              <div class="t-who">${escapeHtml(t.name)}</div>
              <div class="t-text">${escapeHtml(t.text)}</div>
            </div>
          </div>`).join('')}
      </div>`).join('');
  }
  document.getElementById('targetSubmit').addEventListener('click', async ()=>{
    const who = document.getElementById('targetWho').value;
    const input = document.getElementById('targetInput');
    const text = input.value.trim();
    if(!text) return;
    const btn = document.getElementById('targetSubmit');
    btn.disabled = true;
    const list = await getJSON('targets', [], true);
    list.push({id: Date.now()+'-'+Math.random().toString(36).slice(2,7), name: who, text, ts: Date.now(), done:false});
    await setJSON('targets', list, true);
    input.value = '';
    btn.disabled = false;
    renderTargets(list);
  });
  document.getElementById('targetInput').addEventListener('keydown', e=>{
    if(e.key === 'Enter') document.getElementById('targetSubmit').click();
  });
  document.getElementById('targetFeed').addEventListener('change', async e=>{
    const cb = e.target.closest('[data-role="toggle-target"]');
    if(!cb) return;
    const list = await getJSON('targets', [], true);
    const item = list.find(t=>t.id === cb.dataset.id);
    if(item){ item.done = cb.checked; await setJSON('targets', list, true); renderTargets(list); }
  });

  // ---------- DASHBOARD VIEW ----------
  async function loadDashboard(){
    const who = document.getElementById('dashWho').value;
    const member = TEAM.find(m=>m.name===who);
    document.getElementById('dashNick').innerText = '#' + slug(member.nickname);
    const data = await getJSON('skills:' + slug(who), {}, true);

    const checked = ALL_SKILLS.filter(s=>data[s]).length;
    const total = ALL_SKILLS.length;
    updateDashProgress(checked, total);

    document.getElementById('dashGroups').innerHTML = SKILL_GROUPS.map(g=>`
      <div class="skill-group">
        <h4>${escapeHtml(g.group)}</h4>
        <div class="skill-list">
          ${g.items.map(item=>`
            <label class="skill-item ${data[item] ? 'checked':''}" data-skill="${escapeHtml(item)}">
              <input type="checkbox" ${data[item] ? 'checked':''} data-role="skill-toggle" data-skill="${escapeHtml(item)}">
              <span>${escapeHtml(item)}</span>
            </label>`).join('')}
        </div>
      </div>`).join('');
  }
  function updateDashProgress(checked, total){
    const pct = total ? Math.round((checked/total)*100) : 0;
    document.getElementById('dashProgressLabel').innerText = `${checked} / ${total} skills`;
    document.getElementById('dashProgressPct').innerText = pct + '%';
    document.getElementById('dashProgressBar').style.width = pct + '%';
  }
  document.getElementById('dashWho').addEventListener('change', loadDashboard);
  document.getElementById('dashGroups').addEventListener('change', async e=>{
    const cb = e.target.closest('[data-role="skill-toggle"]');
    if(!cb) return;
    const who = document.getElementById('dashWho').value;
    const key = 'skills:' + slug(who);
    const data = await getJSON(key, {}, true);
    data[cb.dataset.skill] = cb.checked;
    await setJSON(key, data, true);
    cb.closest('.skill-item').classList.toggle('checked', cb.checked);
    const checked = ALL_SKILLS.filter(s=>data[s]).length;
    updateDashProgress(checked, ALL_SKILLS.length);
  });

  // ---------- CHAT VIEW ----------
  let chatPoll = null;
  async function loadChat(){
    const log = await getJSON('chat', [], true);
    renderChat(log);
    if(!chatPoll){
      chatPoll = setInterval(async ()=>{
        if(!document.getElementById('view-chat').classList.contains('active')) return;
        const l = await getJSON('chat', [], true);
        renderChat(l);
      }, 4000);
    }
  }
  function renderChat(log){
    const el = document.getElementById('chatLog');
    if(log.length === 0){ el.innerHTML = '<div class="empty">No messages yet. Say hi 👋</div>'; return; }
    const wasNearBottom = (el.scrollHeight - el.scrollTop - el.clientHeight) < 60;
    el.innerHTML = log.map(m=>{
      const member = TEAM.find(t=>t.name===m.name);
      return `
      <div class="msg ${m.name===currentUser ? 'mine':''}">
        <div class="msg-meta"><span>${escapeHtml(m.name)}${member ? ' · #' + slug(member.nickname) : ''}</span><span class="time">${timeStr(m.ts)}</span></div>
        <div class="msg-text">${escapeHtml(m.text)}</div>
      </div>`;
    }).join('');
    if(wasNearBottom) el.scrollTop = el.scrollHeight;
  }
  document.getElementById('chatSend').addEventListener('click', async ()=>{
    const who = document.getElementById('chatWho').value;
    const input = document.getElementById('chatInput');
    const text = input.value.trim();
    if(!text) return;
    const btn = document.getElementById('chatSend');
    btn.disabled = true;
    const log = await getJSON('chat', [], true);
    log.push({name: who, text, ts: Date.now()});
    await setJSON('chat', log, true);
    input.value = '';
    btn.disabled = false;
    renderChat(log);
    document.getElementById('chatLog').scrollTop = document.getElementById('chatLog').scrollHeight;
  });
  document.getElementById('chatInput').addEventListener('keydown', e=>{
    if(e.key === 'Enter') document.getElementById('chatSend').click();
  });

  // ---------- MOTIVATION VIEW ----------
  function renderQuotes(){
    document.getElementById('quoteGrid').innerHTML = QUOTES.map(q=>`
      <div class="quote-card">
        <p class="quote-text">${escapeHtml(q.text)}</p>
        <span class="quote-tag mono">${escapeHtml(q.tag)}</span>
      </div>`).join('');
  }
  async function loadNotes(){
    const notes = await getJSON('notes', [], true);
    renderNotes(notes);
  }
  function renderNotes(notes){
    const el = document.getElementById('notesGrid');
    if(notes.length === 0){ el.innerHTML = '<div class="empty">No notes yet — post the first spark of motivation.</div>'; return; }
    const sorted = [...notes].sort((a,b)=>b.ts-a.ts);
    el.innerHTML = sorted.map(n=>`
      <div class="note-card">
        <p>${escapeHtml(n.text)}</p>
        <div class="t-who mono">${escapeHtml(n.name)} · ${dateStr(n.ts)}</div>
      </div>`).join('');
  }
  document.getElementById('noteSubmit').addEventListener('click', async ()=>{
    const who = document.getElementById('noteWho').value;
    const input = document.getElementById('noteInput');
    const text = input.value.trim();
    if(!text) return;
    const btn = document.getElementById('noteSubmit');
    btn.disabled = true;
    const notes = await getJSON('notes', [], true);
    notes.push({name: who, text, ts: Date.now()});
    await setJSON('notes', notes, true);
    input.value = '';
    btn.disabled = false;
    renderNotes(notes);
  });
  document.getElementById('noteInput').addEventListener('keydown', e=>{
    if(e.key === 'Enter') document.getElementById('noteSubmit').click();
  });

  // ---------- init ----------
  renderTeam();
  renderQuotes();
})();
    </script>
</body>

</html>
