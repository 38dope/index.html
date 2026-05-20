[genai-community (1).html](https://github.com/user-attachments/files/28035884/genai-community.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GenAI Community</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Geist:wght@300;400;500&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #fafaf9;
    --surface: #ffffff;
    --border: rgba(0,0,0,0.08);
    --border-mid: rgba(0,0,0,0.12);
    --text-primary: #111110;
    --text-secondary: #6b6b68;
    --text-tertiary: #a8a8a4;
    --accent: #534AB7;
    --accent-bg: #EEEDFE;
    --accent-mid: #AFA9EC;
    --accent-dark: #26215C;
    --accent-border: #CECBF6;
    --green-dot: #1D9E75;
    --font: 'Geist', -apple-system, sans-serif;
    --mono: 'Geist Mono', monospace;
    --radius-sm: 6px;
    --radius-md: 10px;
    --radius-lg: 14px;
    --sidebar-w: 200px;
    --nav-h: 54px;
    --transition: 120ms ease;
  }

  html, body { height: 100%; background: var(--bg); color: var(--text-primary); font-family: var(--font); font-size: 14px; line-height: 1.5; -webkit-font-smoothing: antialiased; }

  a { color: inherit; text-decoration: none; }

  /* ── Layout ── */
  .app { display: flex; flex-direction: column; height: 100vh; }

  /* ── Nav ── */
  nav {
    height: var(--nav-h);
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 24px;
    flex-shrink: 0;
    position: sticky;
    top: 0;
    z-index: 10;
  }

  .nav-brand { display: flex; align-items: center; gap: 9px; }
  .nav-logo {
    width: 20px; height: 20px;
    background: var(--accent);
    border-radius: 5px;
    flex-shrink: 0;
  }
  .nav-name { font-size: 13.5px; font-weight: 500; letter-spacing: -0.2px; }

  .nav-links { display: flex; gap: 24px; }
  .nav-link {
    font-size: 13px;
    color: var(--text-tertiary);
    cursor: pointer;
    transition: color var(--transition);
    padding: 4px 0;
    position: relative;
  }
  .nav-link:hover { color: var(--text-primary); }
  .nav-link.active { color: var(--text-primary); }
  .nav-link.active::after {
    content: '';
    position: absolute;
    bottom: -17px;
    left: 0; right: 0;
    height: 1px;
    background: var(--text-primary);
  }

  .nav-actions { display: flex; align-items: center; gap: 14px; }

  .nav-icon {
    width: 30px; height: 30px;
    display: flex; align-items: center; justify-content: center;
    border-radius: 50%;
    cursor: pointer;
    color: var(--text-tertiary);
    transition: background var(--transition), color var(--transition);
  }
  .nav-icon:hover { background: rgba(0,0,0,0.04); color: var(--text-primary); }
  .nav-icon svg { width: 16px; height: 16px; stroke-width: 1.6; }

  .avatar-sm {
    width: 28px; height: 28px;
    border-radius: 50%;
    background: var(--accent-bg);
    color: #3C3489;
    font-size: 10.5px;
    font-weight: 500;
    display: flex; align-items: center; justify-content: center;
    cursor: pointer;
    flex-shrink: 0;
  }

  /* ── Body ── */
  .body { display: flex; flex: 1; overflow: hidden; }

  /* ── Sidebar ── */
  .sidebar {
    width: var(--sidebar-w);
    flex-shrink: 0;
    background: var(--surface);
    border-right: 1px solid var(--border);
    overflow-y: auto;
    padding: 20px 12px;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .sidebar-label {
    font-size: 10.5px;
    color: var(--text-tertiary);
    padding: 0 8px;
    margin-bottom: 4px;
    margin-top: 14px;
    letter-spacing: 0.2px;
  }
  .sidebar-label:first-child { margin-top: 0; }

  .sidebar-item {
    display: flex; align-items: center; gap: 6px;
    padding: 5px 8px;
    border-radius: var(--radius-sm);
    font-size: 13px;
    color: var(--text-secondary);
    cursor: pointer;
    transition: background var(--transition), color var(--transition);
    white-space: nowrap;
  }
  .sidebar-item:hover { background: rgba(0,0,0,0.04); color: var(--text-primary); }
  .sidebar-item.active { background: var(--accent-bg); color: #3C3489; font-weight: 500; }
  .sidebar-item .hash { color: var(--text-tertiary); font-size: 12px; }
  .sidebar-item.active .hash { color: var(--accent); }

  .sidebar-badge {
    margin-left: auto;
    background: var(--accent);
    color: white;
    font-size: 10px;
    font-weight: 500;
    padding: 1px 6px;
    border-radius: 10px;
    font-family: var(--mono);
  }

  /* ── Feed ── */
  .feed {
    flex: 1;
    overflow-y: auto;
    padding: 28px 36px;
    max-width: 720px;
  }

  /* ── Banner ── */
  .banner {
    background: var(--accent-bg);
    border: 1px solid var(--accent-border);
    border-radius: var(--radius-lg);
    padding: 20px 24px;
    margin-bottom: 28px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
  }
  .banner-eyebrow { font-size: 10.5px; font-weight: 500; color: var(--accent); margin-bottom: 4px; letter-spacing: 0.3px; text-transform: lowercase; }
  .banner-title { font-size: 15px; font-weight: 500; color: var(--accent-dark); margin-bottom: 2px; }
  .banner-sub { font-size: 12.5px; color: var(--accent); margin-bottom: 16px; }
  .banner-btn {
    display: inline-block;
    background: var(--accent);
    color: #fff;
    font-size: 12px;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: var(--radius-sm);
    cursor: pointer;
    border: none;
    font-family: var(--font);
    transition: opacity var(--transition);
  }
  .banner-btn:hover { opacity: 0.88; }
  .banner-icon { color: var(--accent-mid); flex-shrink: 0; }
  .banner-icon svg { width: 42px; height: 42px; stroke-width: 1.2; }

  /* ── Feed header ── */
  .feed-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 16px;
  }
  .feed-title { font-size: 13px; font-weight: 500; }
  .filter-group { display: flex; gap: 4px; }
  .filter-pill {
    font-size: 12px;
    padding: 3px 10px;
    border-radius: 20px;
    background: rgba(0,0,0,0.04);
    color: var(--text-secondary);
    cursor: pointer;
    border: none;
    font-family: var(--font);
    transition: background var(--transition), color var(--transition);
  }
  .filter-pill:hover { background: rgba(0,0,0,0.07); color: var(--text-primary); }
  .filter-pill.active { background: var(--text-primary); color: white; }

  /* ── Posts ── */
  .post {
    padding: 16px 0;
    border-top: 1px solid var(--border);
    cursor: pointer;
    transition: background var(--transition);
  }
  .post:hover { background: rgba(0,0,0,0.01); }
  .post:last-of-type { border-bottom: 1px solid var(--border); }

  .post-inner { display: flex; gap: 12px; }

  .post-avatar {
    width: 30px; height: 30px;
    border-radius: 50%;
    font-size: 10.5px;
    font-weight: 500;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .post-body { flex: 1; min-width: 0; }
  .post-title {
    font-size: 13.5px;
    font-weight: 500;
    color: var(--text-primary);
    margin-bottom: 4px;
    line-height: 1.4;
  }
  .post-excerpt {
    font-size: 12.5px;
    color: var(--text-secondary);
    margin-bottom: 9px;
    line-height: 1.55;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  .post-meta {
    display: flex;
    align-items: center;
    gap: 14px;
    flex-wrap: wrap;
  }
  .meta-item { font-size: 11.5px; color: var(--text-tertiary); display: flex; align-items: center; gap: 4px; }
  .meta-item svg { width: 13px; height: 13px; stroke-width: 1.6; }
  .meta-item:hover { color: var(--text-secondary); }

  .tag {
    font-size: 11px;
    padding: 2px 8px;
    border-radius: 20px;
    font-weight: 500;
  }

  /* ── Compose ── */
  .compose {
    padding: 14px 0;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 10px;
    cursor: text;
  }
  .compose-placeholder {
    font-size: 13px;
    color: var(--text-tertiary);
    flex: 1;
    background: rgba(0,0,0,0.03);
    padding: 8px 12px;
    border-radius: var(--radius-sm);
    border: 1px solid var(--border);
    transition: border-color var(--transition);
    cursor: text;
  }
  .compose-placeholder:hover { border-color: var(--border-mid); }

  /* ── Right panel ── */
  .panel {
    width: 200px;
    flex-shrink: 0;
    border-left: 1px solid var(--border);
    overflow-y: auto;
    padding: 20px 16px;
    background: var(--surface);
  }

  .panel-section { margin-bottom: 24px; }
  .panel-label { font-size: 10.5px; color: var(--text-tertiary); margin-bottom: 10px; letter-spacing: 0.2px; }

  .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .stat-card {
    background: var(--bg);
    border-radius: var(--radius-md);
    padding: 10px 12px;
    text-align: center;
  }
  .stat-number { font-size: 17px; font-weight: 500; color: var(--text-primary); line-height: 1.2; }
  .stat-label { font-size: 10.5px; color: var(--text-tertiary); margin-top: 2px; }

  .member-list { display: flex; flex-direction: column; gap: 10px; }
  .member-item { display: flex; align-items: center; gap: 8px; }
  .member-avatar-wrap { position: relative; flex-shrink: 0; }
  .member-avatar {
    width: 26px; height: 26px;
    border-radius: 50%;
    font-size: 10px; font-weight: 500;
    display: flex; align-items: center; justify-content: center;
  }
  .online-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green-dot);
    border: 1.5px solid var(--surface);
    position: absolute;
    bottom: 0; right: 0;
  }
  .member-info { min-width: 0; }
  .member-name { font-size: 12px; font-weight: 500; color: var(--text-primary); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .member-loc { font-size: 11px; color: var(--text-tertiary); }

  .event-list { display: flex; flex-direction: column; gap: 8px; }
  .event-card {
    padding: 10px 12px;
    border: 1px solid var(--border);
    border-radius: var(--radius-md);
    cursor: pointer;
    transition: border-color var(--transition);
  }
  .event-card:hover { border-color: var(--border-mid); }
  .event-name { font-size: 12px; font-weight: 500; color: var(--text-primary); margin-bottom: 2px; }
  .event-time { font-size: 11px; color: var(--text-tertiary); }

  /* ── Scrollbar ── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: rgba(0,0,0,0.12); border-radius: 2px; }

  /* ── Search overlay ── */
  .search-overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.3);
    z-index: 100;
    display: none;
    align-items: flex-start;
    justify-content: center;
    padding-top: 80px;
  }
  .search-overlay.open { display: flex; }
  .search-box {
    background: var(--surface);
    border: 1px solid var(--border-mid);
    border-radius: var(--radius-lg);
    width: 480px;
    overflow: hidden;
    box-shadow: 0 8px 32px rgba(0,0,0,0.12);
  }
  .search-input-wrap { display: flex; align-items: center; gap: 10px; padding: 14px 16px; border-bottom: 1px solid var(--border); }
  .search-input-wrap svg { width: 16px; height: 16px; stroke-width: 1.6; color: var(--text-tertiary); flex-shrink: 0; }
  .search-input { flex: 1; border: none; outline: none; font-size: 14px; font-family: var(--font); color: var(--text-primary); background: transparent; }
  .search-input::placeholder { color: var(--text-tertiary); }
  .search-hint { padding: 10px 16px 12px; font-size: 12px; color: var(--text-tertiary); }
</style>
</head>
<body>

<div class="app">

  <!-- Nav -->
  <nav>
    <div class="nav-brand">
      <div class="nav-logo"></div>
      <span class="nav-name">genai community</span>
    </div>
    <div class="nav-links">
      <span class="nav-link" onclick="setNav(this)">explore</span>
      <span class="nav-link active" onclick="setNav(this)">community</span>
      <span class="nav-link" onclick="setNav(this)">events</span>
      <span class="nav-link" onclick="setNav(this)">learn</span>
    </div>
    <div class="nav-actions">
      <div class="nav-icon" onclick="toggleSearch()" title="Search">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
      </div>
      <div class="nav-icon" title="Notifications">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M18 8A6 6 0 0 0 6 8c0 7-3 9-3 9h18s-3-2-3-9"/><path d="M13.73 21a2 2 0 0 1-3.46 0"/></svg>
      </div>
      <div class="avatar-sm">GF</div>
    </div>
  </nav>

  <!-- Body -->
  <div class="body">

    <!-- Left sidebar -->
    <aside class="sidebar">
      <div class="sidebar-label">channels</div>
      <div class="sidebar-item active" onclick="setChannel(this)"><span class="hash">#</span>general</div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>research <span class="sidebar-badge">3</span></div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>prompts</div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>multimodal</div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>agents</div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>safety</div>
      <div class="sidebar-item" onclick="setChannel(this)"><span class="hash">#</span>open-source</div>

      <div class="sidebar-label">regions</div>
      <div class="sidebar-item" onclick="setChannel(this)">Americas</div>
      <div class="sidebar-item" onclick="setChannel(this)">Europe &amp; ME</div>
      <div class="sidebar-item" onclick="setChannel(this)">Asia Pacific</div>
    </aside>

    <!-- Main feed -->
    <main class="feed">

      <!-- Event banner -->
      <div class="banner">
        <div>
          <div class="banner-eyebrow">upcoming event</div>
          <div class="banner-title">GenAI Global Summit — June 2026</div>
          <div class="banner-sub">3 days · 120 speakers · 40 countries</div>
          <button class="banner-btn">Register</button>
        </div>
        <div class="banner-icon">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
        </div>
      </div>

      <!-- Feed header -->
      <div class="feed-header">
        <span class="feed-title">Latest</span>
        <div class="filter-group">
          <button class="filter-pill active" onclick="setFilter(this)">All</button>
          <button class="filter-pill" onclick="setFilter(this)">Trending</button>
          <button class="filter-pill" onclick="setFilter(this)">Unread</button>
        </div>
      </div>

      <!-- Posts -->
      <div class="post">
        <div class="post-inner">
          <div class="post-avatar" style="background:#E1F5EE;color:#085041;">AK</div>
          <div class="post-body">
            <div class="post-title">Reasoning models vs. chain-of-thought prompting — what's the real trade-off?</div>
            <div class="post-excerpt">Comparing internal reasoning in o-series models vs explicit prompting strategies across 3 months of benchmarks across domains. The results were more nuanced than expected.</div>
            <div class="post-meta">
              <span class="meta-item">Aiko K.</span>
              <span class="meta-item">2h ago</span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                47
              </span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                132
              </span>
              <span class="tag" style="background:#EEEDFE;color:#534AB7;">research</span>
            </div>
          </div>
        </div>
      </div>

      <div class="post">
        <div class="post-inner">
          <div class="post-avatar" style="background:#FAECE7;color:#712B13;">ML</div>
          <div class="post-body">
            <div class="post-title">Building autonomous agents with memory — lessons from 6 months in production</div>
            <div class="post-excerpt">Long-term memory architectures for agents: what worked, what failed catastrophically, and the patterns worth stealing. Covers episodic vs semantic memory, retrieval latency, and drift.</div>
            <div class="post-meta">
              <span class="meta-item">Marco L.</span>
              <span class="meta-item">5h ago</span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                89
              </span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                274
              </span>
              <span class="tag" style="background:#FAECE7;color:#993C1D;">agents</span>
            </div>
          </div>
        </div>
      </div>

      <div class="post">
        <div class="post-inner">
          <div class="post-avatar" style="background:#FAEEDA;color:#633806;">PR</div>
          <div class="post-body">
            <div class="post-title">Weekly prompt showcase — share your best system prompts</div>
            <div class="post-excerpt">Community thread for sharing and iterating on system prompts. This week's theme: structured reasoning and multi-step problem decomposition. Drop yours below.</div>
            <div class="post-meta">
              <span class="meta-item">Priya R.</span>
              <span class="meta-item">1d ago</span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                211
              </span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                509
              </span>
              <span class="tag" style="background:#FAEEDA;color:#854F0B;">prompts</span>
            </div>
          </div>
        </div>
      </div>

      <div class="post">
        <div class="post-inner">
          <div class="post-avatar" style="background:#E6F1FB;color:#0C447C;">SK</div>
          <div class="post-body">
            <div class="post-title">Is fine-tuning still worth it in 2026? A cost-benefit breakdown</div>
            <div class="post-excerpt">With frontier models becoming increasingly capable via prompting alone, when does fine-tuning actually pay off? Ran 14 experiments across 5 domains to find out.</div>
            <div class="post-meta">
              <span class="meta-item">Sam K.</span>
              <span class="meta-item">2d ago</span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                63
              </span>
              <span class="meta-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                188
              </span>
              <span class="tag" style="background:#E6F1FB;color:#185FA5;">research</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Compose -->
      <div class="compose">
        <div class="avatar-sm">GF</div>
        <div class="compose-placeholder" contenteditable="true" data-placeholder="Write something..."></div>
      </div>

    </main>

    <!-- Right panel -->
    <aside class="panel">

      <div class="panel-section">
        <div class="panel-label">community</div>
        <div class="stat-grid">
          <div class="stat-card">
            <div class="stat-number">94k</div>
            <div class="stat-label">members</div>
          </div>
          <div class="stat-card">
            <div class="stat-number">138</div>
            <div class="stat-label">online</div>
          </div>
        </div>
      </div>

      <div class="panel-section">
        <div class="panel-label">active now</div>
        <div class="member-list">
          <div class="member-item">
            <div class="member-avatar-wrap">
              <div class="member-avatar" style="background:#E1F5EE;color:#085041;">AK</div>
              <div class="online-dot"></div>
            </div>
            <div class="member-info">
              <div class="member-name">Aiko Kimura</div>
              <div class="member-loc">Tokyo</div>
            </div>
          </div>
          <div class="member-item">
            <div class="member-avatar-wrap">
              <div class="member-avatar" style="background:#FAECE7;color:#712B13;">ML</div>
              <div class="online-dot"></div>
            </div>
            <div class="member-info">
              <div class="member-name">Marco Levi</div>
              <div class="member-loc">Milan</div>
            </div>
          </div>
          <div class="member-item">
            <div class="member-avatar-wrap">
              <div class="member-avatar" style="background:#FAEEDA;color:#633806;">PR</div>
              <div class="online-dot"></div>
            </div>
            <div class="member-info">
              <div class="member-name">Priya Rao</div>
              <div class="member-loc">Bangalore</div>
            </div>
          </div>
          <div class="member-item">
            <div class="member-avatar-wrap">
              <div class="member-avatar" style="background:#E6F1FB;color:#0C447C;">SK</div>
              <div class="online-dot"></div>
            </div>
            <div class="member-info">
              <div class="member-name">Sam K.</div>
              <div class="member-loc">Singapore</div>
            </div>
          </div>
        </div>
      </div>

      <div class="panel-section">
        <div class="panel-label">upcoming</div>
        <div class="event-list">
          <div class="event-card">
            <div class="event-name">Safety office hours</div>
            <div class="event-time">Tomorrow · 3:00 PM UTC</div>
          </div>
          <div class="event-card">
            <div class="event-name">Paper reading — RL + LLMs</div>
            <div class="event-time">Fri May 23 · 4:00 PM UTC</div>
          </div>
          <div class="event-card">
            <div class="event-name">Multimodal showcase</div>
            <div class="event-time">Sat May 24 · 2:00 PM UTC</div>
          </div>
        </div>
      </div>

    </aside>

  </div>
</div>

<!-- Search overlay -->
<div class="search-overlay" id="searchOverlay" onclick="handleOverlayClick(event)">
  <div class="search-box">
    <div class="search-input-wrap">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
      <input class="search-input" id="searchInput" placeholder="Search discussions, members, topics..." autofocus>
    </div>
    <div class="search-hint">Try "reasoning models", "Aiko Kimura", or "agents"</div>
  </div>
</div>

<script>
  function setNav(el) {
    document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
    el.classList.add('active');
  }

  function setChannel(el) {
    document.querySelectorAll('.sidebar-item').forEach(i => i.classList.remove('active'));
    el.classList.add('active');
  }

  function setFilter(el) {
    document.querySelectorAll('.filter-pill').forEach(p => p.classList.remove('active'));
    el.classList.add('active');
  }

  function toggleSearch() {
    const overlay = document.getElementById('searchOverlay');
    overlay.classList.toggle('open');
    if (overlay.classList.contains('open')) {
      setTimeout(() => document.getElementById('searchInput').focus(), 50);
    }
  }

  function handleOverlayClick(e) {
    if (e.target === e.currentTarget) toggleSearch();
  }

  document.addEventListener('keydown', e => {
    if (e.key === 'Escape') document.getElementById('searchOverlay').classList.remove('open');
    if ((e.metaKey || e.ctrlKey) && e.key === 'k') { e.preventDefault(); toggleSearch(); }
  });

  const compose = document.querySelector('.compose-placeholder');
  compose.addEventListener('focus', () => compose.style.borderColor = 'var(--accent)');
  compose.addEventListener('blur', () => compose.style.borderColor = 'var(--border)');
</script>
</body>
</html>
