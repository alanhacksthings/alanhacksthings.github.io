---
layout: null
permalink: /
# This front matter ensures Jekyll processes Liquid on GitHub Pages
---
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>AlanHacks — adventures in hacking (and sometimes sushi)</title>
  <meta name="description" content="Pentesting write-ups, WAF research, HTB walkthroughs, and practical security notes by Alan." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;700&family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b0f0c;           /* near-black */
      --bg-soft:#101513;      /* slightly lighter for cards */
      --text:#e6e6e6;         /* off-white for comfortable reading */
      --muted:#a9b2ac;        /* secondary text */
      --accent:#9cff57;       /* hacker green */
      --accent-dim:#58e06e;   
      --edge:#1c2a22;         /* separators */
      --link:#9cff57;
      --shadow:0 10px 30px rgba(0,0,0,.35);
      --radius:16px;
      --maxw:1024px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; background:var(--bg);
      color:var(--text);
      font-family:"Inter", system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      line-height:1.7;
      background-image: radial-gradient(transparent 0, transparent 98%, rgba(156,255,87,.07) 99%),
                        radial-gradient(transparent 0, transparent 98%, rgba(156,255,87,.05) 99%);
      background-size: 18px 18px, 36px 36px; /* subtle grid */
      background-position: 0 0, 9px 9px;
    }
    a{color:var(--link); text-decoration:none}
    a:hover{text-decoration:underline}
    .wrap{max-width:var(--maxw); margin:0 auto; padding:24px}

    /* Header / Brand */
    header{position:sticky; top:0; backdrop-filter:saturate(140%) blur(6px); background:rgba(11,15,12,.65); border-bottom:1px solid var(--edge); z-index:10}
    .brand{display:flex; align-items:center; gap:14px}
    .brand-title{font-family:"Fira Code", monospace; font-weight:700; font-size:24px; color:var(--accent)}
    .brand-sub{color:var(--muted); font-size:14px}

    /* Nav */
    nav{margin-top:8px}
    .nav{display:flex; gap:18px; flex-wrap:wrap}
    .nav a{font-family:"Fira Code", monospace; font-size:15px; padding:8px 12px; border-radius:999px; border:1px solid var(--edge)}
    .nav a[aria-current="page"], .nav a:hover{background:var(--bg-soft); box-shadow:var(--shadow)}

    /* Hero */
    .hero{padding:64px 0 24px}
    .type{font-family:"Fira Code", monospace; color:var(--accent); font-size:14px; letter-spacing:.02em; opacity:.9}
    h1{font-size:40px; line-height:1.15; margin:12px 0 10px}
    .lead{font-size:18px; color:var(--muted)}
    .btns{margin-top:20px; display:flex; gap:12px; flex-wrap:wrap}
    .btn{display:inline-block; padding:10px 14px; border-radius:10px; border:1px solid var(--edge)}
    .btn.primary{background:var(--accent); color:#0a0e0b; font-weight:700}
    .btn.primary:hover{filter:saturate(110%)}

    /* Cards Grid */
    .grid{display:grid; gap:16px; grid-template-columns:repeat(12,1fr)}
    .card{grid-column:span 12; background:linear-gradient(180deg, rgba(24,35,29,.6), rgba(16,21,19,.6)); border:1px solid var(--edge); border-radius:var(--radius); padding:18px; box-shadow:var(--shadow)}
    .card h3{margin:0 0 6px; font-size:20px}
    .card .meta{color:var(--muted); font-size:14px}
    .card .excerpt{margin:8px 0 0}

    @media(min-width:740px){
      .card.span-6{grid-column:span 6}
      .card.span-4{grid-column:span 4}
      .card.span-8{grid-column:span 8}
    }

    /* Sections */
    section{margin:28px 0 36px}
    .sec-head{display:flex; align-items:baseline; justify-content:space-between; gap:12px; margin-bottom:10px}
    .sec-head h2{margin:0; font-size:22px}
    .see-all{font-size:14px}

    /* Footer */
    footer{border-top:1px solid var(--edge); margin-top:36px; padding:22px 0; color:var(--muted); font-size:14px}

    /* Tiny typewriter flair */
    .cursor{display:inline-block; width:10px; height:1.2em; vertical-align:-.2em; background:var(--accent); animation:blink 1s steps(1,end) infinite}
    @keyframes blink{50%{opacity:0}}
  </style>
</head>
<body>
  <header>
    <div class="wrap">
      <div class="brand">
        <div class="brand-title">./ AlanHacks</div>
        <div class="brand-sub">adventures in hacking (and sometimes sushi)</div>
      </div>
      <nav aria-label="Primary">
        <div class="nav">
          <a href="/" aria-current="page">Home</a>
          <a href="/about/">About</a>
          <a href="/walkthroughs/">Walkthroughs</a>
          <a href="/blog/">Blog</a>
          <a href="/learn/">Learn</a>
        </div>
      </nav>
    </div>
  </header>

  <main class="wrap">
    <!-- Hero / Intro -->
    <section class="hero">
      <div class="type">$ echo "welcome"<span class="cursor" aria-hidden="true"></span></div>
      <h1>Greetings, one and all!</h1>
      <p class="lead">I'm Alan — an orchestra-conductor-turned-penetration tester. I document practical security research, WAF experiments, hands-on HTB write-ups, and notes you can actually use.</p>
      <div class="btns">
        <a class="btn primary" href="/blog/">Browse latest posts</a>
        <a class="btn" href="/walkthroughs/">Featured walkthroughs</a>
      </div>
    </section>

    <!-- Latest Posts -->
    <section>
      <div class="sec-head">
        <h2>Latest posts</h2>
        <a class="see-all" href="/blog/">See all →</a>
      </div>
      <div class="grid">
        {% assign posts_exist = site.posts | size %}
        {% if posts_exist > 0 %}
          {% for post in site.posts limit:4 %}
            <article class="card span-6">
              <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
              <div class="meta">{{ post.date | date: "%b %d, %Y" }} • {% if post.read_time %}{{ post.read_time }} min read{% endif %}</div>
              <p class="excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</p>
            </article>
          {% endfor %}
        {% else %}
          <div class="card">No posts yet — stay tuned for deep dives and write-ups.</div>
        {% endif %}
      </div>
    </section>

    <!-- Featured Walkthrough (auto-picks the most recent tagged post) -->
    <section>
      <div class="sec-head">
        <h2>Featured walkthrough</h2>
        <a class="see-all" href="/walkthroughs/">Browse all →</a>
      </div>
      {% assign w_posts = site.posts | where_exp: "p", "p.tags contains 'walkthrough'" %}
      {% if w_posts and w_posts.size > 0 %}
        {% assign feat = w_posts | sort: 'date' | last %}
        <article class="card">
          <h3><a href="{{ feat.url | relative_url }}">{{ feat.title }}</a></h3>
          <div class="meta">{{ feat.date | date: "%b %d, %Y" }} • Walkthrough</div>
          <p class="excerpt">{{ feat.excerpt | strip_html | truncate: 220 }}</p>
        </article>
      {% else %}
        <div class="card">Tag any post with <code>walkthrough</code> to spotlight it here.</div>
      {% endif %}
    </section>

    <!-- Quick Links / Resources -->
    <section>
      <div class="sec-head">
        <h2>Resources</h2>
      </div>
      <div class="grid">
        <a class="card span-4" href="/learn/#waf-notes"><h3>WAF notes</h3><p class="excerpt">Testing and bypass experiments on Azure WAF, Cloudflare, and ModSecurity.</p></a>
        <a class="card span-4" href="/learn/#cheatsheets"><h3>Cheat sheets</h3><p class="excerpt">One-liners, payloads, and command breakdowns I actually use.</p></a>
        <a class="card span-4" href="/learn/#tools"><h3>Tools & PoCs</h3><p class="excerpt">Small utilities, PoCs, and scripts from blog posts.</p></a>
      </div>
    </section>
  </main>

  <footer>
    <div class="wrap">
      <div>© {{ site.time | date: "%Y" }} AlanHacks — Built with Jekyll on GitHub Pages.</div>
      <div>言語：日本語も勉強中です。いつでも連取…いや連絡歓迎です！</div>
    </div>
  </footer>
</body>
</html>
