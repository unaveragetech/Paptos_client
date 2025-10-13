
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>PAPTOS Client — Lotus Clan</title>
  <meta name="description" content="Paptos: a next‑generation Fabric client blending performance, polish, and PvP utilities. Born from ThunderHack. Built by Lotus Clan." />

  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg-0: #0b0e13;
      --bg-1: #0f141b;
      --bg-glass: rgba(255, 255, 255, 0.06);
      --txt: #eaf0ff;
      --muted: #a6b0c3;
      --accent-1: #9b5cff; /* lotus violet */
      --accent-2: #22e3a4; /* neon mint */
      --accent-3: #ff5c97; /* electric pink */
      --glow: 0 0 24px rgba(155, 92, 255, 0.35), 0 0 12px rgba(34, 227, 164, 0.25);
      --radius: 14px;
      --radius-sm: 10px;
      --shadow: 0 20px 40px rgba(0, 0, 0, 0.45);
    }

    * { box-sizing: border-box; }
    html, body {
      background: radial-gradient(1200px 600px at 10% 10%, #0d1220 0%, var(--bg-0) 60%) fixed;
      color: var(--txt);
      margin: 0;
      font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    }

    .grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 24px;
      max-width: 1080px;
      padding: 36px 20px 100px;
      margin: 0 auto;
    }

    header.hero {
      position: relative;
      overflow: hidden;
      border-radius: var(--radius);
      padding: 36px;
      background:
        linear-gradient(145deg, rgba(155,92,255,0.16), rgba(34,227,164,0.12)),
        linear-gradient(0deg, var(--bg-glass), var(--bg-glass));
      box-shadow: var(--shadow);
    }

    .hero::after {
      content: "";
      position: absolute;
      inset: -40% -20% auto auto;
      width: 520px; height: 520px;
      background: radial-gradient(closest-side, rgba(155,92,255,0.25), transparent 70%);
      filter: blur(20px);
      transform: rotate(15deg);
      pointer-events: none;
    }

    .brandline {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 10px;
      font-weight: 700;
      letter-spacing: 0.4px;
      text-transform: uppercase;
      color: var(--muted);
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 12px;
      background: rgba(155,92,255,0.15);
      border: 1px solid rgba(155,92,255,0.35);
      color: #ddc9ff;
    }

    .title {
      display: flex;
      align-items: baseline;
      gap: 12px;
      margin: 10px 0 12px;
    }

    h1 {
      font-family: Orbitron, Inter, sans-serif;
      font-weight: 700;
      font-size: 36px;
      margin: 0;
      letter-spacing: 0.6px;
      text-shadow: var(--glow);
    }
    .subtitle {
      color: var(--muted);
      font-weight: 600;
    }

    .meta {
      display: flex;
      flex-wrap: wrap;
      gap: 10px 14px;
      margin-top: 14px;
      color: var(--muted);
    }
    .meta span {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 10px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(255,255,255,0.04);
      font-size: 13px;
    }

    .section {
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.02));
      border: 1px solid rgba(255,255,255,0.08);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .section header {
      padding: 20px 24px;
      border-bottom: 1px solid rgba(255,255,255,0.06);
      background:
        linear-gradient(90deg, rgba(155,92,255,0.12), rgba(34,227,164,0.07)),
        linear-gradient(0deg, rgba(255,255,255,0.02), rgba(255,255,255,0.02));
    }
    .section h2 {
      font-family: Orbitron, Inter, sans-serif;
      font-size: 22px;
      margin: 0;
      letter-spacing: 0.4px;
    }

    .content {
      padding: 22px 24px 26px;
    }

    .story {
      line-height: 1.6;
      color: #e8ecff;
    }
    .callout {
      margin: 16px 0;
      padding: 14px 16px;
      border-left: 3px solid var(--accent-2);
      background: rgba(34,227,164,0.07);
      border-radius: var(--radius-sm);
      color: #d9fff0;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 18px;
    }
    @media (max-width: 820px) {
      .features { grid-template-columns: 1fr; }
    }

    .card {
      border-radius: var(--radius-sm);
      padding: 16px 16px 18px;
      background: linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.03));
      border: 1px solid rgba(255,255,255,0.08);
    }
    .card h3 {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 18px;
      margin: 0 0 12px;
      font-weight: 800;
      color: #f5f7ff;
    }
    .card ul {
      margin: 0; padding: 0;
      list-style: none;
      display: grid;
      gap: 8px;
    }
    .card li {
      display: grid;
      gap: 6px;
      padding: 8px 10px;
      border-radius: 8px;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.06);
    }
    .li-lead { font-weight: 700; color: #e9edff; }
    .li-desc { color: var(--muted); font-size: 14px; }

    .kv {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 12px;
    }
    @media (max-width: 700px) { .kv { grid-template-columns: 1fr; } }
    .kv .chip {
      padding: 12px 14px;
      border-radius: 12px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      display: grid;
      gap: 6px;
    }
    .chip .k { font-weight: 800; letter-spacing: 0.2px; color: #f6f9ff; }
    .chip .v { color: var(--muted); }

    .steps {
      display: grid;
      gap: 10px;
      counter-reset: step;
    }
    .steps .step {
      position: relative;
      padding: 14px 16px 14px 52px;
      border-radius: 12px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
    }
    .steps .step::before {
      counter-increment: step;
      content: counter(step);
      position: absolute;
      left: 16px; top: 50%;
      transform: translateY(-50%);
      width: 26px; height: 26px;
      display: grid; place-items: center;
      border-radius: 50%;
      font-weight: 800;
      color: #10131a;
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      box-shadow: 0 0 10px rgba(155,92,255,0.35);
    }

    .footer {
      text-align: center;
      color: var(--muted);
      padding: 24px 0 60px;
    }

    /* Micro animations */
    .pulse {
      animation: pulse 2.6s ease-in-out infinite;
    }
    @keyframes pulse {
      0%, 100% { filter: drop-shadow(0 0 0 rgba(155,92,255,0)); }
      50% { filter: drop-shadow(0 0 14px rgba(155,92,255,0.35)); }
    }
    .shine {
      background: linear-gradient(90deg, rgba(255,255,255,0.0), rgba(255,255,255,0.15), rgba(255,255,255,0.0));
      background-size: 200% 100%;
      animation: shine 3.8s ease-in-out infinite;
      border-radius: 8px;
    }
    @keyframes shine {
      0% { background-position: 200% 0; }
      50% { background-position: 100% 0; }
      100% { background-position: 0 0; }
    }

    .emoji {
      font-size: 20px;
      filter: drop-shadow(0 0 8px rgba(255,255,255,0.25));
    }
    .glowline {
      height: 2px;
      background: linear-gradient(90deg, var(--accent-1), var(--accent-2), var(--accent-3));
      filter: blur(0.8px);
      opacity: 0.7;
    }
  </style>
</head>

<body>
  <main class="grid">
    <!-- Hero -->
    <header class="hero">
      <div class="brandline">
        <span class="badge">
          <span class="emoji">🌸</span> Lotus Clan
        </span>
        <span>PAPTOS CLIENT</span>
      </div>

      <div class="title">
        <h1 class="pulse">PAPTOS Client</h1>
        <span class="subtitle">by UnAverageTech / Beelz — Co‑Owner of Lotus Clan</span>
      </div>

      <div class="meta">
        <span>Version: <strong>1.7b2407</strong></span>
        <span>Minecraft: <strong>Fabric 1.21</strong></span>
        <span>Status: <strong>Active Development</strong></span>
      </div>

      <div class="glowline" style="margin-top:18px;"></div>
    </header>

    <!-- Origin Story -->
    <section class="section">
      <header><h2>Origin story</h2></header>
      <div class="content story">
        <p>Before Lotus Clan existed, I was just another player frustrated with the sameness of Minecraft clients. They worked, but they lacked personality — no flash, no identity, nothing that matched my style. So I decided to build my own.</p>
        <p>Four months later, I had a client so niche it was practically unusable on anyone else’s machine. But that was the point — a laboratory to experiment, break things, and learn. Every crash was a lesson. Every rebuild was progress.</p>
        <p>Months later, I drifted back into the chaotic side of Minecraft: anarchy servers. I revisited one I’d played years ago, expecting it to be dead. Instead, it was thriving. That spark reignited something in me.</p>
        <p>I founded a clan called <strong>Anarchy Pipe</strong>. At first, it was a vault for bases and a scratchpad for client feature ideas. Then came the DM that changed everything: “Wanna partner?” That led to co‑owning <strong>Lotus Clan</strong>. Projects grew bolder. Out of that chaos came the Trail Follower Suit… and eventually, the client that carried all those lessons forward: <strong>Paptos</strong>.</p>
        <div class="callout">
          <strong>Thesis:</strong> Paptos isn’t just a tool. It’s a statement—performance and creativity in collision.
        </div>
      </div>
    </section>

    <!-- About -->
    <section class="section">
      <header><h2>About</h2></header>
      <div class="content">
        <p>Paptos is a next‑generation Minecraft enhancement client built on the Fabric platform. It blends performance optimization, visual polish, and combat‑ready utilities into a cohesive ecosystem.</p>
        <p>Born from the foundation of <strong>ThunderHack</strong>, Paptos is reimagined with a modern interface, modular systems, and community‑driven development. It’s not just a client — it’s what Minecraft can feel like when speed meets style.</p>
      </div>
    </section>

    <!-- Key Features -->
    <section class="section">
      <header><h2>Key features</h2></header>
      <div class="content features">
        <div class="card">
          <h3><span class="emoji">🎨</span> Enhanced visual experience</h3>
          <ul>
            <li class="shine">
              <div class="li-lead">Custom shader integration</div>
              <div class="li-desc">Satin API hooks for cinematic lighting and mood.</div>
            </li>
            <li>
              <div class="li-lead">Dynamic UI themes</div>
              <div class="li-desc">Swap between clean minimalism and neon‑flair at runtime.</div>
            </li>
            <li>
              <div class="li-lead">Smooth animations & particles</div>
              <div class="li-desc">Responsive motion cues for clicks, binds, and toggles.</div>
            </li>
            <li>
              <div class="li-lead">Advanced rendering</div>
              <div class="li-desc">Visualize crystal placements, aura ranges, and combat zones.</div>
            </li>
          </ul>
        </div>

        <div class="card">
          <h3><span class="emoji">⚔️</span> Combat systems</h3>
          <ul>
            <li class="shine">
              <div class="li-lead">Crystal Aura</div>
              <div class="li-desc">Predictive targeting for high‑precision PvP engagements.</div>
            </li>
            <li>
              <div class="li-lead">Smart Killaura</div>
              <div class="li-desc">Configurable parameters for adaptive combat behavior.</div>
            </li>
            <li>
              <div class="li-lead">Auto Totem</div>
              <div class="li-desc">Priority‑based survival logic to keep you alive under pressure.</div>
            </li>
            <li>
              <div class="li-lead">HVH‑ready modules</div>
              <div class="li-desc">Purpose‑built tools for high‑stakes duels and testing.</div>
            </li>
          </ul>
        </div>

        <div class="card">
          <h3><span class="emoji">⚡</span> Performance optimization</h3>
          <ul>
            <li class="shine">
              <div class="li-lead">Memory‑efficient design</div>
              <div class="li-desc">Tuned allocations to cut overhead and stutter.</div>
            </li>
            <li>
              <div class="li-lead">Lag reduction systems</div>
              <div class="li-desc">Smarter scheduling for consistent frame pacing.</div>
            </li>
            <li>
              <div class="li-lead">Optimized network handling</div>
              <div class="li-desc">Stable packet flow for reliable gameplay.</div>
            </li>
            <li>
              <div class="li-lead">Background process management</div>
              <div class="li-desc">Keep non‑critical tasks lean to prioritize your session.</div>
            </li>
          </ul>
        </div>

        <div class="card">
          <h3><span class="emoji">🛠️</span> Quality of life</h3>
          <ul>
            <li class="shine">
              <div class="li-lead">Discord RPC</div>
              <div class="li-desc">Showcase your setup and status in real‑time.</div>
            </li>
            <li>
              <div class="li-lead">Secure authentication</div>
              <div class="li-desc">Hardened login flow to protect your account.</div>
            </li>
            <li>
              <div class="li-lead">Regular updates</div>
              <div class="li-desc">Changelogs and feedback loops keep features evolving.</div>
            </li>
            <li>
              <div class="li-lead">Extensive command system</div>
              <div class="li-desc">Customizable prefix and robust CLI for power users.</div>
            </li>
          </ul>
        </div>

        <div class="card">
          <h3><span class="emoji">🔌</span> Addon support</h3>
          <ul>
            <li class="shine">
              <div class="li-lead">Developer‑friendly API</div>
              <div class="li-desc">Compose modules with clean hooks and events.</div>
            </li>
            <li>
              <div class="li-lead">Expandable functionality</div>
              <div class="li-desc">Ship your own features or graft in community tools.</div>
            </li>
            <li>
              <div class="li-lead">Resource sharing</div>
              <div class="li-desc">Collaborate and iterate across the Lotus ecosystem.</div>
            </li>
          </ul>
        </div>
      </div>
    </section>

    <!-- System requirements -->
    <section class="section">
      <header><h2>System requirements</h2></header>
      <div class="content kv">
        <div class="chip">
          <div class="k">Minecraft</div>
          <div class="v">Fabric 1.21</div>
        </div>
        <div class="chip">
          <div class="k">Java</div>
          <div class="v">21 or newer</div>
        </div>
        <div class="chip">
          <div class="k">Required mods</div>
          <div class="v">Fabric API 1.21</div>
        </div>
      </div>
    </section>

    <!-- Installation -->
    <section class="section">
      <header><h2>Installation</h2></header>
      <div class="content steps">
        <div class="step"><strong>Install Fabric 1.21</strong><div class="li-desc">Use the Fabric installer for your Minecraft version.</div></div>
        <div class="step"><strong>Download latest Paptos JAR</strong><div class="li-desc">Grab the current release from your trusted distribution.</div></div>
        <div class="step"><strong>Place in mods folder</strong><div class="li-desc">Drop the JAR into your <code>.minecraft/mods</code> directory.</div></div>
        <div class="step"><strong>Launch with Fabric profile</strong><div class="li-desc">Select Fabric in your launcher and start the game.</div></div>
        <div class="step"><strong>Join community for access code</strong><div class="li-desc">Authenticate to unlock full client features.</div></div>
      </div>
    </section>

    <!-- Basic controls -->
    <section class="section">
      <header><h2>Basic controls</h2></header>
      <div class="content">
        <ul style="list-style:none; padding:0; margin:0; display:grid; gap:10px;">
          <li class="chip">
            <div class="k">Command prefix</div>
            <div class="v">Configurable in settings</div>
          </li>
          <li class="chip">
            <div class="k">Bind modules</div>
            <div class="v">Middle‑click any module in ClickGUI</div>
          </li>
          <li class="chip">
            <div class="k">Toggle modules</div>
            <div class="v">Click in GUI or use assigned keybind</div>
          </li>
        </ul>
      </div>
    </section>

    <!-- Performance recommendations -->
    <section class="section">
      <header><h2>Performance recommendations</h2></header>
      <div class="content">
        <ul style="list-style:none; padding:0; margin:0; display:grid; gap:10px;">
          <li class="chip">
            <div class="k">RAM allocation</div>
            <div class="v">2–4 GB for balanced performance</div>
          </li>
          <li class="chip">
            <div class="k">Shaders</div>
            <div class="v">Use Sodium‑compatible packs for visuals + fps</div>
          </li>
          <li class="chip">
            <div class="k">Storage</div>
            <div class="v">Run on SSD for faster loads and chunking</div>
          </li>
        </ul>
      </div>
    </section>

    <footer class="footer">
      <div style="margin-bottom:10px; opacity:0.8;">Built by Lotus Clan • Powered by Fabric • Inspired by ThunderHack</div>
      <div style="font-weight:800; letter-spacing:0.3px; color:#e9edff;">Make your client a statement.</div>
    </footer>
  </main>
</body>

