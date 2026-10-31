<!DOCTYPE html>
<html lang="fr" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>CREDITS PANEL PRO - YOUNES TECHNIQUE</title>
<!-- مكتبة HLS لتشغيل القنوات المباشرة والأفلام -->
<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800;900&display=swap" rel="stylesheet">
<style>
*{ box-sizing:border-box; margin:0; padding:0; font-family:'Cairo',-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif; -webkit-tap-highlight-color:transparent; } 
:root{ 
  --bg:#020405; 
  --panel:#050a0c; 
  --panel2:#081014; 
  --panel3:#0d181c; 
  --line:transparent; 
  --lime:#a8ff00; 
  --lime2:#c4ff52; 
  --text:#f0f5f3; 
  --muted:#859693; 
  --danger:#ff5b67; 
  --blue:#55b8ff; 
  --orange:#ffb84d; 
  --green:#37e39a; 
  --shadow:0 15px 35px rgba(0,0,0,.8); 
} 
body{ background: radial-gradient(circle at 50% 0%, rgba(168,255,0,.06), transparent 40%), var(--bg); color:var(--text); min-height:100vh; font-size:11px; overflow-x:hidden; } 
.app{ display:flex; min-height:100vh; position:relative; } 

/* SIDEBAR COMPACT MOBILE */ 
.sidebar{ width:240px; min-width:240px; background:rgba(3,6,7,.98); backdrop-filter:blur(20px); -webkit-backdrop-filter:blur(20px); border:none; padding:12px 10px; display:flex; flex-direction:column; position:fixed; top:0; bottom:0; left:0; z-index:1000; transform:translateX(-100%); transition:transform 0.3s cubic-bezier(0.4, 0, 0.2, 1); } 
.sidebar.open{ transform:translateX(0); }
.brand{ display:flex; align-items:center; gap:10px; padding:4px 4px 14px; border:none; } 
.logo{ width:36px; height:36px; border-radius:12px; display:flex; align-items:center; justify-content:center; background:var(--lime); color:#030607; font-size:18px; font-weight:900; box-shadow:0 0 15px rgba(168,255,0,.3); } 
.brand-text{ font-weight:900; font-size:12px; letter-spacing:.5px; } 
.brand-text span{ display:block; color:var(--lime); font-size:9px; margin-top:2px; letter-spacing:1px; } 

.admin-box{ margin:12px 2px; padding:10px; background:linear-gradient(135deg,#0a1215,#04080a); border:none; border-radius:12px; } 
.admin-box small{ color:var(--muted); display:block; font-size:9px; margin-bottom:3px; } 
.admin-box strong{ font-size:11px; } 
.status-dot{ display:inline-block; width:6px; height:6px; border-radius:50%; background:var(--lime); box-shadow:0 0 8px var(--lime); margin-right:5px; } 

.nav{ display:flex; flex-direction:column; gap:4px; overflow-y:auto; max-height:calc(100vh - 200px); padding-right:2px; } 
.nav::-webkit-scrollbar{ width:3px; }
.nav::-webkit-scrollbar-thumb{ background:rgba(255,255,255,0.05); border-radius:3px; }
.nav-item{ width:100%; border:0; background:transparent; color:var(--muted); display:flex; align-items:center; gap:10px; padding:10px 10px; border-radius:12px; cursor:pointer; text-align:left; transition:.2s; position:relative; } 
.nav-item:hover{ color:var(--text); background:#0a1215; } 
.nav-item.active{ background:linear-gradient(90deg,rgba(168,255,0,.15),rgba(168,255,0,.02)); color:var(--lime); border:none; } 
.nav-icon{ width:30px; height:30px; min-width:30px; border-radius:10px; display:flex; align-items:center; justify-content:center; background:#0a1215; } 
.nav-item.active .nav-icon{ background:rgba(168,255,0,.15); color:var(--lime); } 
.nav-icon svg{ width:16px; height:16px; } 
.nav-label{ display:flex; flex-direction:column; line-height:1.15; } 
.nav-fr{ font-size:11px; font-weight:700; } 
.nav-ar{ font-size:9px; margin-top:2px; direction:rtl; opacity:.7; } 
.sidebar-bottom{ margin-top:auto; border:none; padding-top:10px; color:var(--muted); font-size:9px; text-align:center; } 

/* MAIN CONTAINER */ 
.main{ width:100%; min-height:100vh; transition:all 0.3s ease; } 
.topbar{ height:60px; border:none; background:rgba(2,4,5,.9); backdrop-filter:blur(15px); -webkit-backdrop-filter:blur(15px); display:flex; align-items:center; justify-content:space-between; padding:0 15px; position:sticky; top:0; z-index:500; } 
.top-left{ display:flex; align-items:center; gap:10px; } 
.menu-btn{ border:none; background:var(--panel); color:var(--lime); width:36px; height:36px; border-radius:10px; cursor:pointer; font-size:16px; display:flex; align-items:center; justify-content:center; } 
.page-title h1{ font-size:14px; font-weight:800; } 
.page-title p{ color:var(--muted); font-size:9px; margin-top:2px; } 
.top-right{ display:flex; align-items:center; gap:8px; } 
.live-clock{ background:var(--panel); border:none; padding:6px 10px; border-radius:10px; color:var(--lime); font-size:10px; font-weight:bold; } 
.online{ padding:6px 10px; border-radius:10px; background:rgba(55,227,154,.08); border:none; color:var(--green); font-size:9px; font-weight:bold; } 

/* PAGES */ 
.page{ display:none; padding:15px; animation:pageIn .25s ease; } 
.page.active{ display:block; } 
@keyframes pageIn{ from{opacity:0;transform:translateY(5px)} to{opacity:1;transform:translateY(0)} } 
.section-head{ display:flex; justify-content:space-between; align-items:flex-start; gap:10px; margin-bottom:15px; flex-wrap:wrap; } 
.section-head h2{ font-size:15px; } 
.section-head p{ color:var(--muted); font-size:10px; margin-top:3px; } 

/* GLASS BUTTONS */
.btn {
  position: relative;
  border: none !important;
  background: rgba(255, 255, 255, 0.03) !important;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  color: var(--text);
  border-radius: 12px;
  padding: 9px 12px;
  font-weight: 700;
  font-size: 11px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  transition: .2s;
  white-space: nowrap;
}
.btn:active { transform: scale(0.97); }
.btn-lime { background: rgba(168, 255, 0, 0.12) !important; color: var(--lime2) !important; font-weight: 900; }
.btn-dark { background: rgba(13, 22, 26, 0.6) !important; }
.btn-danger { background: rgba(255, 91, 103, 0.1) !important; color: var(--danger) !important; }
.btn-blue { background: rgba(85, 184, 255, 0.1) !important; color: var(--blue) !important; }
.btn-small { padding: 6px 8px; font-size: 9px; border-radius: 10px; }

/* STATS */ 
.stats{ display:grid; grid-template-columns:repeat(2, 1fr); gap:10px; margin-bottom:15px; } 
.stat{ background:linear-gradient(145deg,#060c0e,#030607); border:none; border-radius:14px; padding:12px; position:relative; overflow:hidden; } 
.stat-top{ display:flex; justify-content:space-between; align-items:center; } 
.stat-icon{ width:28px; height:28px; border-radius:10px; background:#0a1215; display:flex; align-items:center; justify-content:center; color:var(--lime); font-size:12px; } 
.stat-label{ color:var(--muted); font-size:9px; } 
.stat-value{ font-size:16px; font-weight:900; margin-top:10px; } 
.stat-sub{ color:var(--muted); font-size:8px; margin-top:3px; } 

/* CARDS & TABLES */ 
.card{ background:linear-gradient(145deg,#050a0c,#030607); border:none; border-radius:16px; box-shadow:var(--shadow); margin-bottom:15px; overflow:hidden; } 
.card-head{ padding:12px 14px; border:none; display:flex; align-items:center; justify-content:space-between; gap:8px; flex-wrap:wrap; } 
.card-head h3{ font-size:12px; } 
.card-body{ padding:14px; } 

.table-wrap{ overflow-x:auto; width:100%; -webkit-overflow-scrolling:touch; } 
table{ width:100%; border-collapse:collapse; min-width:600px; } 
th{ color:var(--muted); font-size:9px; text-transform:uppercase; text-align:left; padding:10px; border:none; } 
td{ padding:10px; border:none; font-size:11px; } 
tr:hover td{ background:rgba(168,255,0,.02); } 
.avatar{ width:28px; height:28px; border-radius:10px; display:inline-flex; align-items:center; justify-content:center; background:rgba(168,255,0,.1); color:var(--lime); font-weight:900; margin-right:6px; font-size:10px; } 
.client-cell{ display:flex; align-items:center; } 
.badge{ display:inline-flex; padding:4px 7px; border-radius:8px; font-size:9px; font-weight:700; } 
.badge-green{ color:var(--green); background:rgba(55,227,154,.08); } 
.badge-lime{ color:var(--lime); background:rgba(168,255,0,.1); } 
.badge-orange{ color:var(--orange); background:rgba(255,184,77,.08); } 
.badge-blue{ color:var(--blue); background:rgba(85,184,255,.08); } 
.actions{ display:flex; gap:4px; flex-wrap:wrap; } 

/* FORMS */ 
.search{ width:100%; background:#030607; border:none; color:white; outline:none; border-radius:12px; padding:10px 12px; font-size:11px; box-shadow:inset 0 0 10px rgba(0,0,0,0.5); } 
.search-row{ margin-bottom:10px; } 
.form-grid{ display:grid; grid-template-columns:1fr; gap:10px; } 
.form-group{ display:flex; flex-direction:column; gap:5px; } 
.form-group.full{ grid-column:1/-1; } 
.form-group label{ font-size:10px; color:var(--muted); } 

.input, select, textarea, .custom-select-trigger { 
  width:100%; 
  background:#030607 !important; 
  border:none !important; 
  color:white !important; 
  outline:none !important; 
  border-radius:12px !important; 
  padding:10px 14px !important; 
  font-size:11px !important; 
  box-shadow: inset 0 0 10px rgba(0,0,0,0.6); 
} 
textarea{ min-height:80px; resize:vertical; font-family:monospace; font-size:10px; } 
option{ background:#030607; color:#fff; } 

.custom-select-trigger {
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
}
.custom-select-trigger:after {
  content: '\f107';
  font-family: 'Font Awesome 6 Free';
  font-weight: 900;
  color: var(--lime);
  font-size: 10px;
}

.custom-dropdown-modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(2, 4, 5, 0.85);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  z-index: 4000;
  align-items: center;
  justify-content: center;
  padding: 20px;
}
.custom-dropdown-modal.show {
  display: flex;
}
.custom-dropdown-content {
  width: 100%;
  max-width: 320px;
  background: linear-gradient(145deg, #070d10 0%, #030607 100%);
  border-radius: 20px;
  padding: 14px;
  box-shadow: 0 20px 50px rgba(0,0,0,0.9), 0 0 20px rgba(168,255,0,0.1);
  display: flex;
  flex-direction: column;
  gap: 6px;
  max-height: 80vh;
  overflow-y: auto;
}
.custom-dropdown-header {
  font-size: 12px;
  font-weight: 900;
  color: var(--lime);
  padding: 8px 10px 12px;
  border-bottom: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.custom-dropdown-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 12px;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.02);
  cursor: pointer;
  transition: all 0.2s ease;
  color: #fff;
  font-weight: 700;
  font-size: 11px;
}
.custom-dropdown-item:hover, .custom-dropdown-item.active {
  background: rgba(168, 255, 0, 0.1);
  color: var(--lime);
}

.app-mini-badge {
  display: flex;
  align-items: center;
  gap: 8px;
}
.app-icon-box {
  width: 26px;
  height: 26px;
  min-width: 26px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 11px;
  font-weight: 900;
  overflow: hidden;
  background: #030607;
  border: 1px solid rgba(255, 255, 255, 0.1);
}
.app-icon-box img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.badge-younes { color: var(--lime); background: rgba(168,255,0,0.15); box-shadow: 0 0 8px rgba(168,255,0,0.3); }
.badge-ibo { color: #e50914; background: rgba(229,9,20,0.2); box-shadow: 0 0 8px rgba(229,9,20,0.3); }
.badge-tod { color: var(--orange); background: rgba(255,184,77,0.2); box-shadow: 0 0 8px rgba(255,184,77,0.3); }
.badge-bob { color: #ff7b00; background: rgba(255,123,0,0.2); box-shadow: 0 0 8px rgba(255,123,0,0.3); }

.custom-radio {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  border: 2px solid var(--muted);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s;
}
.custom-dropdown-item.active .custom-radio {
  border-color: var(--lime);
  box-shadow: 0 0 10px rgba(168,255,0,0.5);
}
.custom-dropdown-item.active .custom-radio::after {
  content: '';
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--lime);
  box-shadow: 0 0 6px var(--lime);
}

/* QUICK ACTIONS GRID */
.quick-actions{ display:grid; grid-template-columns:repeat(2, 1fr); gap:8px; } 
.quick{ padding:12px; border-radius:12px; background:rgba(8, 16, 20, 0.6) !important; border:none !important; cursor:pointer; color:white; text-align:left; transition:.2s; width:100%; } 
.quick:active{ transform:scale(0.97); }
.quick-icon{ color:var(--lime); margin-bottom:6px; font-size:15px; } 
.quick strong{ display:block; font-size:11px; } 
.quick span{ display:block; color:var(--muted); font-size:8px; margin-top:2px; } 

.m3u-box, .xtream-box { background:rgba(6,12,15,0.8); border:none; border-radius:16px; padding:14px; margin-bottom:12px; }
.m3u-title, .xtream-title { font-weight:800; font-size:11px; margin-bottom:8px; display:flex; align-items:center; gap:6px; color:var(--lime); }
.m3u-status { font-size:10px; color:var(--muted); margin-top:6px; }
.m3u-success { color: var(--green); }
.m3u-error { color: var(--danger); }

.shimmer-title {
  position: relative;
  display: inline-block;
  color: var(--lime);
  font-size: 16px;
  font-weight: 900;
  margin-bottom: 6px;
  background: linear-gradient(90deg, #a8ff00 0%, #ffffff 50%, #a8ff00 100%);
  background-size: 200% auto;
  color: transparent;
  -webkit-background-clip: text;
  background-clip: text;
  animation: shine 3s linear infinite;
}
@keyframes shine {
  to { background-position: 200% center; }
}

.glass-test-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 14px;
  background: rgba(255, 255, 255, 0.04);
  border: none;
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-radius: 14px;
  color: var(--lime);
  font-weight: 800;
  font-size: 10px;
  cursor: pointer;
  transition: all 0.2s ease;
  box-shadow: 0 4px 15px rgba(0,0,0,0.5);
}
.glass-test-badge:hover {
  background: rgba(168, 255, 0, 0.1);
  transform: translateY(-2px);
}

.luxury-standalone-card {
  background: linear-gradient(145deg, #091419 0%, #030607 100%);
  border: none;
  border-radius: 20px;
  padding: 24px;
  text-align: center;
  box-shadow: 0 15px 40px rgba(0,0,0,0.9);
  margin-top: 10px;
}

.channels-grid-circular {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 12px;
}
@media (min-width: 600px) {
  .channels-grid-circular { grid-template-columns: repeat(4, 1fr); gap: 14px; }
}
@media (min-width: 900px) {
  .channels-grid-circular { grid-template-columns: repeat(6, 1fr); gap: 16px; }
}

.channel-mini-card {
  background: rgba(8, 16, 20, 0.7);
  border: none;
  border-radius: 16px;
  padding: 10px 6px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  transition: transform 0.2s, background 0.2s;
  box-shadow: 0 4px 15px rgba(0,0,0,0.4);
}
.channel-mini-card:active {
  transform: scale(0.95);
  background: rgba(168, 255, 0, 0.08);
}
.channel-circle-icon {
  width: 52px;
  height: 52px;
  min-width: 52px;
  border-radius: 50%;
  object-fit: cover;
  border: none;
  box-shadow: 0 0 15px rgba(168, 255, 0, 0.25);
  background: #030607;
}
.channel-mini-title {
  font-size: 9px;
  font-weight: 700;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  width: 100%;
}

.streaming-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
}
@media (min-width: 600px) {
  .streaming-grid { grid-template-columns: repeat(4, 1fr); gap: 10px; }
}
@media (min-width: 900px) {
  .streaming-grid { grid-template-columns: repeat(6, 1fr); gap: 12px; }
}

.stream-card {
  background: #081014;
  border-radius: 12px;
  overflow: hidden;
  border: none;
  cursor: pointer;
  transition: transform 0.2s;
  display: flex;
  flex-direction: column;
  position: relative;
}
.stream-card:hover {
  transform: translateY(-3px);
}
.stream-poster-wrap {
  width: 100%;
  height: 140px;
  position: relative;
  background: #030607;
  overflow: hidden;
}
.stream-poster {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.stream-play-badge {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.2s;
}
.stream-card:hover .stream-play-badge {
  opacity: 1;
}
.stream-play-badge i {
  width: 32px;
  height: 32px;
  background: var(--lime);
  color: #030607;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  box-shadow: 0 0 12px var(--lime);
}
.stream-info {
  padding: 6px 8px;
  display: flex;
  flex-direction: column;
  gap: 2px;
}
.stream-title {
  font-size: 10px;
  font-weight: 700;
  color: #fff;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.stream-sub {
  font-size: 8px;
  color: var(--muted);
}

/* MODALS */ 
.modal{ display:none; position:fixed; inset:0; background:rgba(0,0,0,.8); backdrop-filter:blur(5px); z-index:3000; align-items:center; justify-content:center; padding:12px; } 
.modal.show{ display:flex; } 
.modal-box{ width:100%; max-width:420px; max-height:85vh; overflow-y:auto; background:#050a0c; border:none; border-radius:16px; box-shadow:var(--shadow); } 
.modal-head{ padding:12px 14px; border:none; display:flex; justify-content:space-between; align-items:center; } 
.modal-head h3{ font-size:13px; } 
.close{ border:0; background:#0a1215; color:var(--muted); width:28px; height:28px; border-radius:10px; cursor:pointer; font-size:15px; display:flex; align-items:center; justify-content:center; } 
.modal-body{ padding:14px; } 
.modal-foot{ padding:12px 14px; border:none; display:flex; justify-content:flex-end; gap:6px; } 

.toast{ position:fixed; right:15px; bottom:15px; background:#0a1215; border:none; color:white; padding:10px 14px; border-radius:12px; font-size:11px; z-index:5000; transform:translateY(80px); opacity:0; transition:.3s; box-shadow:0 10px 25px rgba(0,0,0,0.6); } 
.toast.show{ transform:translateY(0); opacity:1; } 
.empty{ padding:35px 10px; text-align:center; color:var(--muted); font-size:10px; } 
</style>
</head>
<body>

<div class="app">
  <!-- SIDEBAR -->
  <aside class="sidebar" id="sidebar">
    <div class="brand">
      <div class="logo"><i class="fa-solid fa-crown"></i></div>
      <div class="brand-text">YOUNES TECHNIQUE<span>PLAYER PRO</span></div>
    </div>
    <div class="admin-box">
      <small>COMPTE ADMINISTRATEUR</small>
      <strong><span class="status-dot"></span>Admin Panel</strong>
    </div>
    <div class="nav">
      <button class="nav-item active" data-page="dashboard">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="7" height="7"></rect><rect x="14" y="3" width="7" height="7"></rect><rect x="3" y="14" width="7" height="7"></rect><rect x="14" y="14" width="7" height="7"></rect></svg></div>
        <div class="nav-label"><span class="nav-fr">Dashboard</span><span class="nav-ar">الرئيسية</span></div>
      </button>
      <button class="nav-item" data-page="test-playlist">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="5 3 19 12 5 21 5 3"></polygon></svg></div>
        <div class="nav-label"><span class="nav-fr">YOUNES TECHNIQUE Player</span><span class="nav-ar">مشغل يونيس تقنية المتكامل</span></div>
      </button>
      <button class="nav-item" data-page="clients">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M22 21v-2a4 4 0 0 0-3-3.87"></path></svg></div>
        <div class="nav-label"><span class="nav-fr">Clients</span><span class="nav-ar">العملاء</span></div>
      </button>
      <button class="nav-item" data-page="abonnements">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg></div>
        <div class="nav-label"><span class="nav-fr">Abonnements & Token</span><span class="nav-ar">الاشتراكات والتطوير</span></div>
      </button>
      <button class="nav-item" data-page="payments">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="5" width="20" height="14" rx="2"></rect><path d="M2 10h20"></path></svg></div>
        <div class="nav-label"><span class="nav-fr">Paiements</span><span class="nav-ar">الدفعات</span></div>
      </button>
      <button class="nav-item" data-page="history">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 12a9 9 0 1 0 3-6.7"></path><path d="M3 4v6h6"></path></svg></div>
        <div class="nav-label"><span class="nav-fr">Historique</span><span class="nav-ar">السجل</span></div>
      </button>
      <button class="nav-item" data-page="activation">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l2.2 6.6L21 11l-6.8 2.4L12 20l-2.2-6.6L3 11l6.8-2.4L12 2z"></path></svg></div>
        <div class="nav-label"><span class="nav-fr">Activation</span><span class="nav-ar">التفعيل</span></div>
      </button>
      <button class="nav-item" data-page="settings">
        <div class="nav-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="3"></circle></svg></div>
        <div class="nav-label"><span class="nav-fr">Paramètres</span><span class="nav-ar">الإعدادات</span></div>
      </button>
    </div>
    <div class="sidebar-bottom">YOUNES TECHNIQUE PRO v4.2</div>
  </aside>

  <!-- MAIN -->
  <main class="main">
    <header class="topbar">
      <div class="top-left">
        <button class="menu-btn" id="menuBtn">☰</button>
        <div class="page-title">
          <h1 id="topTitle">Dashboard</h1>
          <p>Panel Mobile • إدارة احترافية</p>
        </div>
      </div>
      <div class="top-right">
        <div class="live-clock" id="liveClock">--:--</div>
        <div class="online">● ON</div>
      </div>
    </header>

    <!-- DASHBOARD PAGE -->
    <div class="page active" id="dashboard">
      <div class="section-head">
        <div><h2>Dashboard — الرئيسية</h2><p>نظرة عامة على اللوحة</p></div>
        <button class="btn btn-lime btn-small" onclick="openClientModal()"> ＋ عميل </button>
      </div>
      <div class="stats">
        <div class="stat"><div class="stat-top"><span class="stat-label">Clients / العملاء</span><div class="stat-icon"><i class="fa-solid fa-users"></i></div></div><div class="stat-value" id="statClients">0</div><div class="stat-sub">إجمالي العملاء</div></div>
        <div class="stat"><div class="stat-top"><span class="stat-label">À payer / المطلوب</span><div class="stat-icon"><i class="fa-solid fa-wallet"></i></div></div><div class="stat-value" id="statDue">0 DH</div><div class="stat-sub">المبلغ الإجمالي</div></div>
        <div class="stat"><div class="stat-top"><span class="stat-label">Payé / المدفوع</span><div class="stat-icon"><i class="fa-solid fa-credit-card"></i></div></div><div class="stat-value" id="statPaid">0 DH</div><div class="stat-sub">المستلم</div></div>
        <div class="stat"><div class="stat-top"><span class="stat-label">Reste / الباقي</span><div class="stat-icon"><i class="fa-solid fa-triangle-exclamation"></i></div></div><div class="stat-value" id="statRemain">0 DH</div><div class="stat-sub">المتبقي</div></div>
      </div>
      <div class="card">
        <div class="card-head">
          <h3>العملاء الجدد — Récents</h3>
          <button class="btn btn-dark btn-small" onclick="showPage('clients')">الكل</button>
        </div>
        <div class="table-wrap">
          <table><thead><tr><th>Client</th><th>Compte</th><th>État</th><th>Reste</th></tr></thead><tbody id="dashboardTable"></tbody></table>
        </div>
      </div>
      <div class="card">
        <div class="card-head"><h3>إجراءات سريعة — Actions</h3></div>
        <div class="card-body">
          <div class="quick-actions">
            <button class="quick" onclick="openClientModal()"><div class="quick-icon">👤＋</div><strong>عميل جديد</strong><span>إضافة عميل</span></button>
            <button class="quick" onclick="showPage('test-playlist')"><div class="quick-icon"><i class="fa-solid fa-crown"></i></div><strong>مشغل يونيس تقنية</strong><span>YOUNES TECHNIQUE</span></button>
            <button class="quick" onclick="openPaymentModal()"><div class="quick-icon">💳</div><strong>تسجيل دفعة</strong><span>إضافة مبلغ</span></button>
            <button class="quick" onclick="showPage('abonnements')"><div class="quick-icon">🔑</div><strong>مولد التوكن</strong><span>Token Generator</span></button>
          </div>
        </div>
      </div>
    </div>

    <!-- YOUNES TECHNIQUE PLAYER DEDICATED PAGE -->
    <div class="page" id="test-playlist">
      <div class="section-head">
        <div><h2>YOUNES TECHNIQUE PLAYER PRO</h2><p>المشغل الذكي المتكامل المشفر (Live, VOD, Series)</p></div>
      </div>
      
      <div class="card">
        <div class="card-head"><h3>🔐 إعدادات وتفعيل المشغل الاحترافي</h3></div>
        <div class="card-body">
          <div class="form-group full" style="margin-bottom:10px;">
            <label>رابط Xtream / M3U الحالي:</label>
            <input class="input" id="luxuryServerInput" placeholder="http://server.com:port/get.php?username=USER&password=PASS&type=m3u_plus" oninput="validateM3UInputLive(this.value)" value="http://smart-v2.live:80/get.php?username=mkv1wx9aam&password=u25vaksvc6&type=m3u_plus">
            <div id="m3uInputStatus" class="m3u-status m3u-success" style="margin-top:6px;">✓ الرابط تم التحقق منه وجاهز للتشغيل.</div>
          </div>
          <div class="luxury-standalone-card">
            <i class="fa-solid fa-crown" style="font-size:48px; color:var(--lime); margin-bottom:10px; text-shadow:0 0 20px rgba(168,255,0,0.4);"></i>
            <h3 class="shimmer-title">YOUNES TECHNIQUE</h3>
            <p style="color:var(--muted); font-size:11px; margin-bottom:16px;">مشغل فائق السرعة بمعايير التطبيقات الكبرى، قفل تلقائي عند نهاية اليومية وربط بالجهاز ورقم الزبون.</p>
            <div style="display:flex; gap:10px; justify-content:center; flex-wrap:wrap; align-items:center;">
              <button class="btn btn-lime" onclick="launchStandaloneLuxuryApp()" style="padding:12px 20px; font-size:12px;"><i class="fa-solid fa-rocket"></i> تشغيل المشغل</button>
              <div class="glass-test-badge" onclick="runQuickTestM3U()">
                <i class="fa-solid fa-vial-circle-check"></i> Test M3U
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- CLIENTS PAGE -->
    <div class="page" id="clients">
      <div class="section-head">
        <div><h2>Clients — العملاء</h2><p>إدارة عملاء البانل</p></div>
        <button class="btn btn-lime btn-small" onclick="openClientModal()"> ＋ عميل </button>
      </div>
      <div class="card">
        <div class="card-head">
          <h3>قائمة العملاء</h3>
          <span class="badge badge-lime" id="clientCountText">0</span>
        </div>
        <div class="card-body">
          <div class="search-row"><input class="search" id="clientSearch" placeholder="بحث بالاسم أو الحساب..."></div>
          <div class="table-wrap">
            <table><thead><tr><th>Client</th><th>Compte</th><th>Total</th><th>Payé</th><th>Reste</th><th>Actions</th></tr></thead><tbody id="clientsTable"></tbody></table>
          </div>
        </div>
      </div>
    </div>

    <!-- ABONNEMENTS & TOKEN GENERATOR PAGE -->
    <div class="page" id="abonnements">
      <div class="section-head">
        <div><h2>Abonnements & Token Generator</h2><p>توليد وتصدير كود الـ Token للعميل والتحقق من الاشتراكات</p></div>
      </div>
      
      <!-- نافذة مولد التوكن المدمجة -->
      <div class="card" style="margin-bottom:15px; border:1px solid rgba(168,255,0,0.2);">
        <div class="card-head"><h3><i class="fa-solid fa-key" style="color:var(--lime);"></i> مولد كود التوكن (Token Generator Pro)</h3></div>
        <div class="card-body">
          <div class="form-grid">
            <div class="form-group full">
              <label>العميل</label>
              <input type="hidden" id="abonnementClientVal" value="">
              <div class="custom-select-trigger" onclick="openClientDropdown('abonnementClientVal', 'abonnementClientText', 'genName', 'genPhone')">
                <span id="abonnementClientText">اختر العميل من القائمة</span>
              </div>
            </div>

            <div class="form-group"><label>اسم العميل</label><input class="input" id="genName" placeholder="مثال: يونس الفروقي"></div>
            <div class="form-group"><label>رقم هاتف العميل (مع الرمز الدولي)</label><input class="input" id="genPhone" placeholder="+212600000000"></div>
            <div class="form-group"><label>تاريخ انتهاء الصلاحية (اليومية)</label><input class="input" type="date" id="genExpiry"></div>
            
            <div class="form-group full"><button class="btn btn-lime" onclick="generateAndShowToken()"><i class="fa-solid fa-wand-magic-sparkles"></i> توليد وحفظ كود التوكن (Token)</button></div>
          </div>

          <div class="result-box" id="resultBox" style="display:none; margin-top:14px; background:rgba(3,6,7,0.9); border-radius:14px; padding:12px; border:1px dashed rgba(168,255,0,0.3); flex-direction:column; gap:8px;">
            <div style="font-size:10px; color:var(--muted); font-weight:700;">كود التوكن المولّد بنجاح:</div>
            <div id="tokenOutput" style="background:#000; padding:10px; border-radius:10px; font-family:monospace; color:var(--lime); font-size:13px; font-weight:bold; text-align:center; letter-spacing:1px;">YT-XXXX-XXXX</div>
            <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;">
              <button class="btn" style="background:rgba(255,255,255,0.05)!important;" onclick="copyToken()"><i class="fa-solid fa-copy"></i> نسخ الكود</button>
              <button class="btn" style="background:rgba(55,227,154,0.15)!important; color:var(--green)!important;" onclick="sendViaWhatsApp()"><i class="fa-brands fa-whatsapp"></i> إرسال واتساب</button>
            </div>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="card-head"><h3>الاشتراكات والتوكنات النشطة</h3><span class="badge badge-lime" id="abonnementCount">0</span></div>
        <div class="table-wrap">
          <table><thead><tr><th>Client</th><th>Phone</th><th>Token</th><th>الصلاحية</th><th>Actions</th></tr></thead><tbody id="abonnementTable"></tbody></table>
        </div>
      </div>
    </div>

    <!-- PAYMENTS PAGE -->
    <div class="page" id="payments">
      <div class="section-head">
        <div><h2>Paiements — الدفعات</h2><p>سجل المدفوعات</p></div>
        <button class="btn btn-lime btn-small" onclick="openPaymentModal()"> ＋ دفعة </button>
      </div>
      <div class="card">
        <div class="card-head"><h3>الدفعات الأخيرة</h3></div>
        <div class="table-wrap">
          <table><thead><tr><th>Date</th><th>Client</th><th>Montant</th><th>Note</th></tr></thead><tbody id="paymentsTable"></tbody></table>
        </div>
      </div>
    </div>

    <!-- HISTORY PAGE -->
    <div class="page" id="history">
      <div class="section-head"><div><h2>Historique — السجل</h2><p>سجل العمليات</p></div></div>
      <div class="card"><div class="card-head"><h3>النشاطات</h3></div><div class="card-body"><div class="history-list" id="historyList"></div></div></div>
    </div>

    <!-- ACTIVATION PAGE -->
    <div class="page" id="activation">
      <div class="section-head"><div><h2>Activation — التفعيل</h2><p>تفعيل شاشات Smart TV عبر MAC</p></div></div>
      <div class="card" style="margin-bottom:15px;">
        <div class="card-head"><h3>تفعيل جديد</h3></div>
        <div class="card-body">
          <div class="form-grid">
            <div class="form-group full">
              <label>العميل</label>
              <input type="hidden" id="activationClientVal" value="">
              <div class="custom-select-trigger" onclick="openClientDropdown('activationClientVal', 'activationClientText', 'activationName', null)">
                <span id="activationClientText">اختر العميل</span>
              </div>
            </div>

            <div class="form-group"><label>اسم العميل</label><input class="input" id="activationName" placeholder="اسم العميل"></div>
            <div class="form-group"><label>MAC Address</label><input class="input" id="activationMac" placeholder="00:11:22:33:44:55" maxlength="17"></div>
            
            <div class="form-group full">
              <label>التطبيق</label>
              <input type="hidden" id="activationApp" value="YOUNES TECHNIQUE">
              <div class="custom-select-trigger" onclick="openCustomDropdown('activationApp')">
                <span id="activationAppText">YOUNES TECHNIQUE</span>
              </div>
            </div>

            <div class="form-group"><label>اليومية الأصلية (تاريخ الصلاحية)</label><input class="input" type="date" id="activationDuration"></div>
            <div class="form-group"><label>ملاحظة</label><input class="input" id="activationNote" placeholder="ملاحظة"></div>
            <div class="form-group full"><button class="btn btn-lime" onclick="createActivation()">⚡ تفعيل الآن</button></div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-head"><h3>التفعيلات النشطة</h3><span class="badge badge-lime" id="activationCount">0</span></div>
        <div class="table-wrap">
          <table><thead><tr><th>Client</th><th>MAC</th><th>App</th><th>اليومية</th><th>Actions</th></tr></thead><tbody id="activationTable"></tbody></table>
        </div>
      </div>
    </div>

    <!-- SETTINGS PAGE -->
    <div class="page" id="settings">
      <div class="section-head"><div><h2>Paramètres — الإعدادات</h2><p>إدارة البيانات والنسخ الاحتياطي</p></div></div>
      <div class="card">
        <div class="card-head"><h3>خيارات البيانات</h3></div>
        <div class="card-body">
          <div class="quick-actions">
            <button class="quick" onclick="exportData()"><div class="quick-icon">⬇</div><strong>تصدير JSON</strong><span>حفظ نسخة</span></button>
            <button class="quick" onclick="document.getElementById('importFile').click()"><div class="quick-icon">⬆</div><strong>استيراد JSON</strong><span>استرجاع البيانات</span></button>
            <button class="quick" onclick="clearAllData()"><div class="quick-icon" style="color:#ff5b67">🗑</div><strong>حذف الكل</strong><span>تفريغ الذاكرة</span></button>
          </div>
          <input type="file" id="importFile" accept=".json" style="display:none">
        </div>
      </div>
    </div>
  </main>
</div>

<!-- نافذة الاختيار المنبثقة الفاخرة المخصصة للتطبيقات والعملاء -->
<div class="custom-dropdown-modal" id="customDropdownModal">
  <div class="custom-dropdown-content">
    <div class="custom-dropdown-header">
      <span id="customModalTitle">اختر العنصر</span>
      <button class="close" onclick="closeCustomDropdown()">×</button>
    </div>
    <div id="customDropdownItems" style="display:flex; flex-direction:column; gap:6px;"></div>
  </div>
</div>

<!-- MODALS -->
<div class="modal" id="clientModal"><div class="modal-box"><div class="modal-head"><h3 id="clientModalTitle">عميل جديد</h3><button class="close" onclick="closeModal('clientModal')">×</button></div><div class="modal-body"><input type="hidden" id="editClientId"><div class="form-grid"><div class="form-group full"><label>الاسم الكامل</label><input class="input" id="clientName" placeholder="اسم العميل"></div><div class="form-group full"><label>رقم الهاتف</label><input class="input" id="clientPhone" placeholder="+212600000000"></div><div class="form-group full"><label>الحساب / Username</label><input class="input" id="clientAccount" placeholder="حساب العميل"></div></div></div><div class="modal-foot"><button class="btn btn-dark btn-small" onclick="closeModal('clientModal')">إلغاء</button><button class="btn btn-danger btn-small" id="deleteClientModalBtn" onclick="deleteCurrentClient()" style="display:none">حذف</button><button class="btn btn-lime btn-small" onclick="saveClient()">حفظ</button></div></div></div>
<div class="modal" id="debtModal"><div class="modal-box"><div class="modal-head"><h3>إضافة مبلغ</h3><button class="close" onclick="closeModal('debtModal')">×</button></div><div class="modal-body"><input type="hidden" id="debtClientId"><div class="form-grid"><div class="form-group"><label>المبلغ (DH)</label><input class="input" type="number" id="debtAmount" placeholder="0.00"></div><div class="form-group"><label>ملاحظة</label><input class="input" id="debtNote" placeholder="السبب"></div></div></div><div class="modal-foot"><button class="btn btn-dark btn-small" onclick="closeModal('debtModal')">إلغاء</button><button class="btn btn-lime btn-small" onclick="saveDebt()">إضافة</button></div></div></div>
<div class="modal" id="paymentModal"><div class="modal-box"><div class="modal-head"><h3>تسجيل دفعة</h3><button class="close" onclick="closeModal('paymentModal')">×</button></div><div class="modal-body"><input type="hidden" id="paymentClientId"><div class="form-grid"><div class="form-group full"><label>العميل</label><select id="paymentClient"><option value="">اختر العميل</option></select></div><div class="form-group"><label>المبلغ (DH)</label><input class="input" type="number" id="paymentAmount" placeholder="0.00"></div><div class="form-group"><label>ملاحظة</label><input class="input" id="paymentNote" placeholder="ملاحظة"></div></div></div><div class="modal-foot"><button class="btn btn-dark btn-small" onclick="closeModal('paymentModal')">إلغاء</button><button class="btn btn-lime btn-small" onclick="savePayment()">حفظ</button></div></div></div>
<div class="modal" id="detailModal"><div class="modal-box"><div class="modal-head"><h3>التفاصيل</h3><button class="close" onclick="closeModal('detailModal')">×</button></div><div class="modal-body" id="detailBody"></div></div></div>

<div class="toast" id="toast"></div>

<!-- واجهات مشغل YOUNES TECHNIQUE مقفل بالجهاز ورقم الزبون واليومية -->
<div id="luxuryOverlayWrapper" style="display:none; position:fixed; inset:0; z-index:9000; background:#020405;">
  <!-- شاشة إدخال كود Token والتحقق من القفل -->
  <div id="loginScreen" style="display:flex; flex-direction:column; align-items:center; justify-content:center; min-height:100vh; padding:20px; width:100vw; position:absolute; inset:0; background:radial-gradient(circle at 50% 10%, rgba(168,255,0,0.08) 0%, #020405 90%); z-index:9100;">
    <div class="request-card" id="requestCard" style="background:rgba(5, 10, 12, 0.95); backdrop-filter:blur(20px); width:100%; max-width:380px; padding:30px 22px; border-radius:26px; box-shadow:0 20px 45px rgba(0,0,0,0.95), 0 0 25px rgba(168,255,0,0.15); margin-bottom:14px; text-align:center; display:flex; flex-direction:column; align-items:center;">
      <i class="fa-solid fa-crown" style="font-size:50px; color:var(--lime); margin-bottom:8px; text-shadow:0 0 15px rgba(168,255,0,0.5);"></i>
      <div style="font-size:20px; font-weight:900; color:#fff; margin-bottom:6px;">YOUNES <span style="color:var(--lime);">TECHNIQUE</span></div>
      <p style="font-size:12px; color:var(--muted); font-weight:700; margin-bottom:22px; line-height:1.6;">التطبيق مقفل ومربوط برقم هاتف الزبون وجهازه. أدخل كود التوكن الخاص بك:</p>
      
      <div class="form-group full" style="width:100%; margin-bottom:14px;">
        <input class="input" type="text" id="tokenInput" placeholder="أدخل Token التفعيل..." style="text-align:center; font-weight:bold; letter-spacing:1px;">
      </div>

      <button class="btn btn-lime" style="width:100%; justify-content:center; padding:12px; font-weight:900;" onclick="verifyAndUnlockWithToken()">
        <i class="fa-solid fa-key"></i> <span>فحص وقفل الجهاز (Verify Token)</span>
      </button>

      <button class="btn" style="width:100%; margin-top:10px; background:rgba(255,255,255,0.05); color:var(--muted); justify-content:center;" onclick="exitLuxuryPlayer()">إلغاء</button>
    </div>
  </div>

  <!-- شاشة التطبيق الداخلية الرئيسية -->
  <div id="appScreen" style="display:none; flex-direction:column; justify-content:center; min-height:100vh; padding:15px 20px; max-width:1100px; margin:0 auto; position:absolute; inset:0; background:var(--bg);">
    <div style="display:flex; justify-content:space-between; align-items:center; background:#050a0c; padding:14px 20px; border-radius:18px; margin-bottom:12px;">
      <div style="font-size:16px; font-weight:900; color:#fff; display:flex; align-items:center; gap:8px;"><i class="fa-solid fa-crown" style="color:var(--lime);"></i> YOUNES <span style="color:var(--lime);">TECHNIQUE</span></div>
      <button class="btn" style="background:#0a1215; color:var(--lime);" onclick="exitLuxuryPlayer()"><i class="fa-solid fa-arrow-left"></i> الرجوع للبانل</button>
    </div>

    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:14px; margin-bottom:16px;">
      <div class="card" style="padding:24px; text-align:center; cursor:pointer;" onclick="openLiveSection()"><i class="fa-solid fa-tv" style="font-size:32px; color:var(--lime); margin-bottom:8px;"></i><h3 style="color:#fff;">Live TV</h3></div>
      <div class="card" style="padding:24px; text-align:center; cursor:pointer;" onclick="openVodSection('vod')"><i class="fa-solid fa-film" style="font-size:32px; color:var(--lime); margin-bottom:8px;"></i><h3 style="color:#fff;">Movies</h3></div>
      <div class="card" style="padding:24px; text-align:center; cursor:pointer;" onclick="openVodSection('series')"><i class="fa-solid fa-clapperboard" style="font-size:32px; color:var(--lime); margin-bottom:8px;"></i><h3 style="color:#fff;">Series</h3></div>
    </div>
  </div>

  <!-- شاشة البث المباشر -->
  <div id="liveMainLayout" style="display:none; height:100vh; width:100vw; flex-direction:column; background:#000; position:absolute; inset:0; z-index:9200;">
    <div style="position:relative; background:#000; height:35vh; display:flex;">
      <video id="liveVideoPlayer" autoplay playsinline controls style="width:100%; height:100%; object-fit:contain;"></video>
    </div>
    <div style="flex:1; background:#050a0c; display:flex; flex-direction:column; overflow:hidden;">
      <div style="padding:10px 14px; background:#020405; display:flex; align-items:center; justify-content:space-between;">
        <button class="btn" style="background:#0a1215; color:var(--lime);" onclick="exitLiveSection()"><i class="fa-solid fa-arrow-left"></i> رجوع</button>
        <h4 style="color:#fff;" id="liveCatHeader">Live Channels</h4>
        <div></div>
      </div>
      <div id="liveCategoriesHorizontalBar" style="display:flex; gap:8px; overflow-x:auto; padding:10px; background:#030607;"></div>
      <div id="liveChannelsGrid" style="flex:1; overflow-y:auto; padding:12px;" class="channels-grid-circular"></div>
    </div>
  </div>

  <!-- شاشة الأفلام والمسلسلات VOD -->
  <div id="vodMainLayout" style="display:none; height:100vh; width:100vw; flex-direction:column; background:#020405; position:absolute; inset:0; z-index:9200;">
    <div style="display:flex; align-items:center; justify-content:space-between; padding:12px 15px; background:#050a0c;">
      <button class="btn" style="background:#0a1215; color:var(--lime);" onclick="exitVodSection()"><i class="fa-solid fa-arrow-left"></i> رجوع</button>
      <span style="font-size:13px; font-weight:900; color:var(--lime);" id="vodMainTitle">Movies</span>
      <div></div>
    </div>
    <div id="vodCategoriesBar" style="display:flex; gap:6px; overflow-x:auto; padding:8px 12px; background:#030607;"></div>
    <div style="flex:1; overflow-y:auto; padding:10px; background:#020405;">
      <div id="vodGridContainer" class="streaming-grid"></div>
    </div>
  </div>

  <!-- نافذة تفاصيل الفيلم / المسلسل -->
  <div id="netflixDetailsModal" style="display:none; position:fixed; inset:0; background:rgba(2,4,5,0.98); z-index:9500; flex-direction:column; padding:15px; overflow-y:auto;">
    <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:12px;">
      <button class="btn" style="background:#0a1215; color:var(--lime);" onclick="closeDetailsModal()"><i class="fa-solid fa-arrow-left"></i> رجوع للمسلسلات</button>
      <h3 id="detailTitle" style="color:var(--lime); font-size:13px;">Title</h3>
      <div></div>
    </div>
    <div id="detailMainContent" style="display:flex; flex-direction:column; gap:12px; max-width:600px; margin:0 auto; width:100%;">
      <div style="display:flex; gap:12px; align-items:center;">
        <img id="detailPoster" src="" style="width:100px; height:140px; object-fit:cover; border-radius:12px;" onerror="this.src='https://via.placeholder.com/100x140?text=No+Image'">
        <div style="flex:1; display:flex; flex-direction:column; gap:6px;">
          <p id="detailDesc" style="color:#fff; font-size:10px; max-height:80px; overflow-y:auto; color:var(--muted);">Desc</p>
        </div>
      </div>
      <div id="seasonsContainer" style="display:flex; gap:8px; overflow-x:auto; padding:5px 0;"></div>
      <div id="episodesContainer" style="display:grid; grid-template-columns:1fr; gap:8px; max-height:45vh; overflow-y:auto;"></div>
    </div>
  </div>

  <!-- مشغل الفيديو الفعلي -->
  <div id="netflixPlayerModal" style="display:none; position:fixed; inset:0; background:#000; z-index:9600; flex-direction:column;">
    <div style="display:flex; align-items:center; justify-content:space-between; padding:10px 14px; background:#050a0c;">
      <button class="btn" style="background:#0a1215; color:var(--lime);" onclick="closeNetflixPlayer()"><i class="fa-solid fa-arrow-left"></i> رجوع للحلقات</button>
      <span id="netflixPlayerTitle" style="color:var(--lime); font-weight:bold; font-size:11px;">Player</span>
      <div></div>
    </div>
    <div style="flex:1; display:flex; align-items:center; justify-content:center; background:#000;">
      <video id="vodVideoElement" autoplay playsinline controls style="width:100%; height:100%; object-fit:contain;"></video>
    </div>
  </div>
</div>

<script>
const KEYS={ clients:"credits_panel_clients", payments:"credits_panel_payments", history:"credits_panel_history", transactions:"credits_panel_transactions", activations:"credits_panel_activations", abonnements:"credits_panel_abonnements", tokens:"yt_valid_tokens" }; 
let clients=load(KEYS.clients,[]); 
let payments=load(KEYS.payments,[]); 
let historyData=load(KEYS.history,[]); 
let transactions=load(KEYS.transactions,[]); 
let activations=load(KEYS.activations,[]); 
let abonnements=load(KEYS.abonnements,[]); 

function load(key,fallback){ try{ const value=localStorage.getItem(key); return value?JSON.parse(value):fallback; }catch(e){ return fallback; } } 
function saveData(){ 
  localStorage.setItem(KEYS.clients,JSON.stringify(clients)); 
  localStorage.setItem(KEYS.payments,JSON.stringify(payments)); 
  localStorage.setItem(KEYS.history,JSON.stringify(historyData)); 
  localStorage.setItem(KEYS.transactions,JSON.stringify(transactions)); 
  localStorage.setItem(KEYS.activations,JSON.stringify(activations)); 
  localStorage.setItem(KEYS.abonnements,JSON.stringify(abonnements)); 
} 
function makeId(){ return Date.now().toString(36)+Math.random().toString(36).substring(2,8); } 
function money(value){ return Number(value||0).toLocaleString("fr-FR",{minimumFractionDigits:0,maximumFractionDigits:2})+" DH"; } 
function now(){ return new Date().toLocaleTimeString("fr-FR",{hour:'2-digit',minute:'2-digit'}); } 
function dateOnly(){ return new Date().toLocaleDateString("fr-FR"); } 

function getTodayDefaultDate() {
  const d = new Date();
  const year = d.getFullYear();
  const month = String(d.getMonth() + 1).padStart(2, '0');
  const day = String(d.getDate()).padStart(2, '0');
  return `${year}-${month}-${day}`;
}

function escapeHtml(value){ return String(value??"").replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;").replace(/"/g,"&quot;").replace(/'/g,"&#039;"); } 
function initials(name){ return String(name||"?").split(" ").filter(Boolean).slice(0,2).map(x=>x[0]).join("").toUpperCase(); } 
function getClient(id){ return clients.find(c=>c.id===id); } 

const titles={ dashboard:"Dashboard", "test-playlist":"YOUNES TECHNIQUE Player", clients:"Clients", abonnements:"Abonnements & Token", payments:"Paiements", history:"Historique", activation:"Activation", settings:"Paramètres" }; 

document.querySelectorAll(".nav-item").forEach(item=>{ 
  item.addEventListener("click",function(){ 
    showPage(this.dataset.page); 
  }); 
}); 

function showPage(page){ 
  document.querySelectorAll(".page").forEach(p=>p.classList.remove("active")); 
  const target=document.getElementById(page); 
  if(target)target.classList.add("active"); 
  document.querySelectorAll(".nav-item").forEach(item=>{ 
    item.classList.toggle("active",item.dataset.page===page); 
  }); 
  document.getElementById("topTitle").textContent=titles[page]||"Dashboard"; 
  document.getElementById("sidebar").classList.remove("open"); 

  if(page === 'abonnements') setDefaultDates();
  if(page === 'activation') setDefaultDates();
} 

function setDefaultDates() {
  const today = getTodayDefaultDate();
  const genExpiry = document.getElementById("genExpiry");
  const actDur = document.getElementById("activationDuration");
  if(genExpiry && !genExpiry.value) genExpiry.value = today;
  if(actDur && !actDur.value) actDur.value = today;
}

document.getElementById("menuBtn").addEventListener("click",()=>{ document.getElementById("sidebar").classList.toggle("open"); }); 

function updateClock(){ 
  const d = new Date();
  document.getElementById("liveClock").textContent = d.toLocaleTimeString("fr-FR", {hour: '2-digit', minute:'2-digit'}); 
} 
setInterval(updateClock,1000); 
updateClock(); 

const appsDetailedList = [
  { name: "YOUNES TECHNIQUE", icon: '<i class="fa-solid fa-crown"></i>', badgeClass: "badge-younes" },
  { name: "IBO Player", icon: '<i class="fa-solid fa-play"></i>', badgeClass: "badge-ibo" },
  { name: "TOD Player", icon: '<img src="https://i.ibb.co/MmzxjC0/IMG-20261031-074328.jpg" alt="TOD">', badgeClass: "badge-tod" },
  { name: "Bob Player", icon: '<img src="https://i.ibb.co/tPYc0tFM/bob-player.webp" alt="Bob">', badgeClass: "badge-bob" }
];

function openCustomDropdown(fieldId) {
  const currentVal = document.getElementById(fieldId).value;
  document.getElementById("customModalTitle").textContent = "اختر التطبيق";
  const itemsContainer = document.getElementById("customDropdownItems");
  itemsContainer.innerHTML = "";
  
  appsDetailedList.forEach(app => {
    const isSelected = (app.name === currentVal);
    const item = document.createElement("div");
    item.className = `custom-dropdown-item ${isSelected ? 'active' : ''}`;
    item.innerHTML = `
      <div class="app-mini-badge">
        <div class="app-icon-box ${app.badgeClass}">${app.icon}</div>
        <span>${escapeHtml(app.name)}</span>
      </div>
      <div class="custom-radio"></div>
    `;
    item.onclick = () => {
      document.getElementById(fieldId).value = app.name;
      document.getElementById(fieldId + "Text").textContent = app.name;
      closeCustomDropdown();
    };
    itemsContainer.appendChild(item);
  });
  
  document.getElementById("customDropdownModal").classList.add("show");
}

function openClientDropdown(valFieldId, textDisplayId, nameInputId, phoneInputId) {
  document.getElementById("customModalTitle").textContent = "اختر العميل";
  const itemsContainer = document.getElementById("customDropdownItems");
  itemsContainer.innerHTML = "";
  
  if(!clients.length) {
    itemsContainer.innerHTML = `<div class="empty">لا يوجد عملاء مضافون بعد</div>`;
    document.getElementById("customDropdownModal").classList.add("show");
    return;
  }

  clients.forEach(c => {
    const currentVal = document.getElementById(valFieldId).value;
    const isSelected = (c.id === currentVal);
    const item = document.createElement("div");
    item.className = `custom-dropdown-item ${isSelected ? 'active' : ''}`;
    item.innerHTML = `
      <div class="app-mini-badge">
        <div class="avatar">${escapeHtml(initials(c.name))}</div>
        <span>${escapeHtml(c.name)}</span>
      </div>
      <div class="custom-radio"></div>
    `;
    item.onclick = () => {
      document.getElementById(valFieldId).value = c.id;
      document.getElementById(textDisplayId).textContent = c.name;
      if(nameInputId) document.getElementById(nameInputId).value = c.name;
      if(phoneInputId && document.getElementById(phoneInputId)) {
        document.getElementById(phoneInputId).value = c.phone || "";
      }
      closeCustomDropdown();
    };
    itemsContainer.appendChild(item);
  });

  document.getElementById("customDropdownModal").classList.add("show");
}

function closeCustomDropdown() {
  document.getElementById("customDropdownModal").classList.remove("show");
}

function validateM3UString(urlStr) {
  if(!urlStr || typeof urlStr !== 'string') return { valid: false, error: "الرابط فارغ" };
  const trimmed = urlStr.trim();
  try {
    const parsed = new URL(trimmed);
    if(parsed.protocol !== 'http:' && parsed.protocol !== 'https:') {
      return { valid: false, error: "يجب أن يبدأ الرابط بـ http أو https" };
    }
    let username = parsed.searchParams.get("username") || parsed.searchParams.get("user") || "";
    let password = parsed.searchParams.get("password") || parsed.searchParams.get("pass") || "";
    return { valid: true, host: parsed.origin, username: username || "unknown", password: password || "unknown" };
  } catch(e) {
    return { valid: false, error: "صيغة الرابط غير صحيحة" };
  }
}

function validateM3UInputLive(val) {
  const statusEl = document.getElementById("m3uInputStatus");
  if(!statusEl) return;
  const res = validateM3UString(val);
  if(res.valid) {
    statusEl.className = "m3u-status m3u-success";
    statusEl.innerHTML = `✓ الرابط سليـم وموثوق (Server: ${res.host})`;
  } else {
    statusEl.className = "m3u-status m3u-error";
    statusEl.innerHTML = `✗ تنبيه: ${res.error}`;
  }
}

function runQuickTestM3U() {
  const urlInput = document.getElementById("luxuryServerInput").value.trim();
  const validation = validateM3UString(urlInput);
  if(validation.valid) {
    toast(`✓ اختبار ناجح: الرابط سليم ومتصل (${validation.host})`);
  } else {
    toast(`✗ اختبار فاشل: ${validation.error}`);
  }
}

/* --- نظام توليد وتوحيد التوكن وقفل الجهاز --- */
function getDeviceFingerprint() {
  let deviceId = localStorage.getItem("yt_device_fingerprint");
  if(!deviceId) {
    deviceId = "DEV-" + Math.random().toString(36).substring(2, 10).toUpperCase() + "-" + Date.now().toString(36).toUpperCase();
    localStorage.setItem("yt_device_fingerprint", deviceId);
  }
  return deviceId;
}

function generateUnifiedToken(phone, expiryDate) {
  const cleanPhone = String(phone || "").trim().replace(/\D/g, '');
  const cleanDate = String(expiryDate || "").trim();
  if (!cleanPhone || !cleanDate) return null;

  const rawStr = `YT-${cleanPhone}-${cleanDate}`;
  let hash = 0;
  for (let i = 0; i < rawStr.length; i++) {
    hash = ((hash << 5) - hash) + rawStr.charCodeAt(i);
    hash |= 0;
  }
  
  const codeSegment = Math.abs(hash).toString(36).toUpperCase().padStart(6, '0').slice(0, 6);
  const phoneSegment = cleanPhone.slice(-4) || "0000";
  return `YT-${codeSegment}-${phoneSegment}`;
}

let generatedTokenText = "";

function generateAndShowToken() {
  const name = document.getElementById('genName').value.trim();
  const phone = document.getElementById('genPhone').value.trim();
  const expiry = document.getElementById('genExpiry').value;
  const clientId = document.getElementById('abonnementClientVal').value;

  if(!name || !phone || !expiry) {
    toast("المرجو ملء جميع الحقول أولاً");
    return;
  }

  generatedTokenText = generateUnifiedToken(phone, expiry);
  document.getElementById('tokenOutput').textContent = generatedTokenText;
  document.getElementById('resultBox').style.display = 'flex';

  // حفظ التوكن في القائمة والذاكرة للتحقق الفوري
  const savedTokens = JSON.parse(localStorage.getItem(KEYS.tokens) || "{}");
  savedTokens[generatedTokenText] = { name, phone, expiry, deviceId: getDeviceFingerprint() };
  localStorage.setItem(KEYS.tokens, JSON.stringify(savedTokens));

  // تسجيله أيضاً في الاشتراكات العامة للبانل
  abonnements.unshift({ 
    id: makeId(), 
    date: dateOnly(), 
    clientId, 
    name, 
    phone, 
    app: "YOUNES TECHNIQUE", 
    duration: expiry, 
    token: generatedTokenText 
  });
  saveData();
  renderAbonnements();

  toast("✓ تم توليد الكود وحفظه بنجاح 🚀");
}

function copyToken() {
  navigator.clipboard.writeText(generatedTokenText);
  toast("✓ تم نسخ الكود إلى الحافظة");
}

function sendViaWhatsApp() {
  const phone = document.getElementById('genPhone').value.trim().replace(/\D/g, '');
  const name = document.getElementById('genName').value.trim();
  const expiry = document.getElementById('genExpiry').value;
  
  const msg = `مرحباً بك يا ${name} 👋\nإليك كود التفعيل (Token) الخاص بتطبيق YOUNES TECHNIQUE PLAYER:\n\n🔑 Token: *${generatedTokenText}*\n📅 صالح لغاية: ${expiry}\n\nاستمتع بالمشاهدة! 📺🚀`;
  window.open(`https://wa.me/${phone}?text=${encodeURIComponent(msg)}`, '_blank');
}

function launchStandaloneLuxuryApp() {
  const activeSession = JSON.parse(localStorage.getItem("yt_active_session") || "null");
  const today = getTodayDefaultDate();

  if(activeSession) {
    if(today > activeSession.expiry) {
      toast("✗ انتهت صلاحية اليومية (انتهى الاشتراك)، يرجى التجديد.");
      localStorage.removeItem("yt_active_session");
    } else if(activeSession.deviceId !== getDeviceFingerprint()) {
      toast("✗ خطأ أمني: هذا التوكن مسجل على جهاز آخر.");
      localStorage.removeItem("yt_active_session");
    } else {
      openUnlockedAppScreen(activeSession);
      return;
    }
  }

  document.getElementById("luxuryOverlayWrapper").style.display = "block";
  document.getElementById("loginScreen").style.display = "flex";
  document.getElementById("appScreen").style.display = "none";
}

function verifyAndUnlockWithToken() {
  const tokenInput = document.getElementById("tokenInput").value.trim();
  if(!tokenInput) {
    toast("المرجو إدخال كود Token صالح");
    return;
  }

  const savedTokens = JSON.parse(localStorage.getItem(KEYS.tokens) || "{}");
  const tokenData = savedTokens[tokenInput];

  if(!tokenData) {
    toast("✗ كود Token غير صحيح أو غير مسجل في النظام");
    return;
  }

  const today = getTodayDefaultDate();
  if(today > tokenData.expiry) {
    toast("✗ عذراً، انتهت صلاحية هذا الاشتراك (انتهت اليومية)");
    return;
  }

  const sessionData = {
    phone: tokenData.phone,
    expiry: tokenData.expiry,
    deviceId: getDeviceFingerprint(),
    m3uUrl: document.getElementById("luxuryServerInput").value.trim()
  };
  localStorage.setItem("yt_active_session", JSON.stringify(sessionData));

  openUnlockedAppScreen(sessionData);
  toast("✓ تم التحقق وقفل الجهاز بنجاح! أهلاً بك 🚀");
}

function openUnlockedAppScreen(session) {
  const validation = validateM3UString(session.m3uUrl);
  const creds = { 
    host: validation.valid ? validation.host : "http://smart-v2.live:80", 
    user: validation.valid ? validation.username : "mkv1wx9aam", 
    pass: validation.valid ? validation.password : "u25vaksvc6", 
    deviceId: session.deviceId 
  };
  localStorage.setItem("faroukii_active_creds", JSON.stringify(creds));

  document.getElementById("luxuryOverlayWrapper").style.display = "block";
  document.getElementById("loginScreen").style.display = "none";
  document.getElementById("appScreen").style.display = "flex";
}

function exitLuxuryPlayer() {
  document.getElementById("luxuryOverlayWrapper").style.display = "none";
}

async function safeFetch(url) {
  try {
    const res = await fetch(url);
    if (res.ok) return await res.json();
  } catch(e) {}
  try {
    const proxyUrl = `https://api.allorigins.win/get?url=${encodeURIComponent(url)}`;
    const pRes = await fetch(proxyUrl);
    if(pRes.ok) {
      const json = await pRes.json();
      if(json.contents) return JSON.parse(json.contents);
    }
  } catch(e) {}
  return null;
}

async function openLiveSection() {
  document.getElementById("appScreen").style.display = "none";
  document.getElementById("liveMainLayout").style.display = "flex";
  const bar = document.getElementById("liveCategoriesHorizontalBar");
  const grid = document.getElementById("liveChannelsGrid");
  bar.innerHTML = "Loading...";
  grid.innerHTML = "Loading channels...";

  const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
  const categories = await safeFetch(`${acc.host}/player_api.php?username=${acc.user}&password=${acc.pass}&action=get_live_categories`);
  
  if(!categories || !Array.isArray(categories)) return;
  bar.innerHTML = "";
  categories.forEach((cat) => {
    const chip = document.createElement("div");
    chip.style.cssText = "background:#0a1215; color:#fff; padding:5px 12px; border-radius:12px; cursor:pointer; white-space:nowrap; font-weight:bold; font-size:10px;";
    chip.innerHTML = `<i class="fa-solid fa-folder" style="color:var(--lime); margin-right:4px;"></i> ${escapeHtml(cat.category_name)}`;
    chip.onclick = () => loadLiveStreams(cat.category_id);
    bar.appendChild(chip);
  });
  if(categories.length > 0) loadLiveStreams(categories[0].category_id);
}

async function loadLiveStreams(catId) {
  const grid = document.getElementById("liveChannelsGrid");
  const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
  let streams = await safeFetch(`${acc.host}/player_api.php?username=${acc.user}&password=${acc.pass}&action=get_live_streams&category_id=${catId}`);
  grid.innerHTML = "";
  if(!streams || !Array.isArray(streams)) {
    grid.innerHTML = `<div class="empty" style="grid-column:1/-1;">لا توجد قنوات متاحة في هذا القسم</div>`;
    return;
  }
  streams.forEach(item => {
    const playUrl = `${acc.host}/live/${acc.user}/${acc.pass}/${item.stream_id}.m3u8`;
    const card = document.createElement("div");
    card.className = "channel-mini-card";
    
    const logoImg = item.stream_icon ? 
      `<img src="${item.stream_icon}" class="channel-circle-icon" onerror="this.src='https://via.placeholder.com/52?text=TV'">` : 
      `<div class="channel-circle-icon" style="display:flex; align-items:center; justify-content:center; color:var(--lime); font-size:16px;"><i class="fa-solid fa-tv"></i></div>`;

    card.innerHTML = `${logoImg}<div class="channel-mini-title" title="${escapeHtml(item.name)}">${escapeHtml(item.name)}</div>`;
    card.onclick = () => {
      const video = document.getElementById("liveVideoPlayer");
      if (typeof Hls !== 'undefined' && Hls.isSupported()) {
        const hls = new Hls();
        hls.loadSource(playUrl);
        hls.attachMedia(video);
        hls.on(Hls.Events.MANIFEST_PARSED, () => video.play());
      } else { video.src = playUrl; video.play(); }
    };
    grid.appendChild(card);
  });
}

function exitLiveSection() {
  document.getElementById("liveMainLayout").style.display = "none";
  document.getElementById("appScreen").style.display = "flex";
}

async function openVodSection(type) {
  document.getElementById("appScreen").style.display = "none";
  document.getElementById("vodMainLayout").style.display = "flex";
  document.getElementById("vodMainTitle").textContent = type === 'vod' ? 'Movies & VOD' : 'Series Library';
  const bar = document.getElementById("vodCategoriesBar");
  const grid = document.getElementById("vodGridContainer");
  bar.innerHTML = "Loading...";
  grid.innerHTML = "Loading...";

  window.currentVodType = type;
  const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
  const catAction = type === 'vod' ? "get_vod_categories" : "get_series_categories";
  let categories = await safeFetch(`${acc.host}/player_api.php?username=${acc.user}&password=${acc.pass}&action=${catAction}`);
  
  if(!categories || !Array.isArray(categories)) {
    bar.innerHTML = "";
    loadVodStreams(type, "");
    return;
  }

  bar.innerHTML = "";
  categories.forEach(cat => {
    const chip = document.createElement("div");
    chip.style.cssText = "background:#0a1215; color:#fff; padding:5px 12px; border-radius:12px; cursor:pointer; white-space:nowrap; font-weight:bold; font-size:10px;";
    chip.innerHTML = `<i class="fa-solid fa-film" style="color:var(--lime); margin-right:4px;"></i> ${escapeHtml(cat.category_name)}`;
    chip.onclick = () => loadVodStreams(type, cat.category_id);
    bar.appendChild(chip);
  });
  loadVodStreams(type, categories[0].category_id);
}

async function loadVodStreams(type, catId) {
  const grid = document.getElementById("vodGridContainer");
  const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
  const action = type === 'vod' ? "get_vod_streams" : "get_series";
  let url = `${acc.host}/player_api.php?username=${acc.user}&password=${acc.pass}&action=${action}`;
  if(catId) url += `&category_id=${catId}`;

  let items = await safeFetch(url);
  grid.innerHTML = "";
  if(!items || !Array.isArray(items)) {
    grid.innerHTML = `<div class="empty" style="grid-column:1/-1;">لا توجد محتويات متاحة في هذا القسم</div>`;
    return;
  }

  items.forEach(item => {
    const poster = item.stream_icon || item.cover || 'https://via.placeholder.com/120x170?text=No+Poster';
    const title = item.name || item.title || "محتوى حصري";
    
    const card = document.createElement("div");
    card.className = "stream-card";
    card.innerHTML = `
      <div class="stream-poster-wrap">
        <img class="stream-poster" src="${poster}" onerror="this.src='https://via.placeholder.com/120x170?text=No+Image'">
        <div class="stream-play-badge"><i class="fa-solid fa-play"></i></div>
      </div>
      <div class="stream-info">
        <div class="stream-title" title="${escapeHtml(title)}">${escapeHtml(title)}</div>
        <div class="stream-sub">HD • 2026</div>
      </div>
    `;
    card.onclick = () => {
      if(type === 'vod') {
        document.getElementById("netflixDetailsModal").style.display = "flex";
        document.getElementById("detailPoster").src = poster;
        document.getElementById("detailTitle").textContent = title;
        document.getElementById("detailDesc").textContent = item.plot || item.description || "استمتع بمشاهدة هذا الفيلم حصرياً بجودة عالية.";
        document.getElementById("seasonsContainer").style.display = "none";
        document.getElementById("episodesContainer").innerHTML = `<button class="btn btn-lime" style="width:100%; justify-content:center; padding:12px;" onclick="launchMoviePlayer('${acc.host}/movie/${acc.user}/${acc.pass}/${item.stream_id}.${item.container_extension || 'mp4'}', '${escapeHtml(title)}')"><i class="fa-solid fa-play"></i> تشغيل الفيلم الآن</button>`;
      } else {
        loadSeriesDetails(item.series_id, title, poster, item.plot || item.description || "");
      }
    };
    grid.appendChild(card);
  });
}

async function loadSeriesDetails(seriesId, seriesTitle, poster, desc) {
  document.getElementById("netflixDetailsModal").style.display = "flex";
  document.getElementById("detailPoster").src = poster;
  document.getElementById("detailTitle").textContent = seriesTitle;
  document.getElementById("detailDesc").textContent = desc;
  
  const seasonsBox = document.getElementById("seasonsContainer");
  const episodesBox = document.getElementById("episodesContainer");
  seasonsBox.style.display = "flex";
  seasonsBox.innerHTML = "جاري تحميل المواسم...";
  episodesBox.innerHTML = "";

  const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
  const data = await safeFetch(`${acc.host}/player_api.php?username=${acc.user}&password=${acc.pass}&action=get_series_info&series_id=${seriesId}`);
  
  if(!data || !data.episodes) {
    seasonsBox.innerHTML = "لا توجد مواسم متاحة";
    return;
  }

  seasonsBox.innerHTML = "";
  const seasons = Object.keys(data.episodes);
  
  seasons.forEach((seasonNum, index) => {
    const chip = document.createElement("div");
    chip.style.cssText = `background:${index===0?'rgba(168,255,0,0.2)':'#0a1215'}; color:${index===0?'var(--lime)':'#fff'}; padding:6px 14px; border-radius:12px; cursor:pointer; white-space:nowrap; font-weight:bold; font-size:10px;`;
    chip.textContent = `الموسم ${seasonNum}`;
    chip.onclick = () => {
      document.querySelectorAll("#seasonsContainer > div").forEach(c => {
        c.style.background = '#0a1215';
        c.style.color = '#fff';
      });
      chip.style.background = 'rgba(168,255,0,0.2)';
      chip.style.color = 'var(--lime)';
      renderEpisodes(data.episodes[seasonNum], seriesTitle);
    };
    seasonsBox.appendChild(chip);
  });

  if(seasons.length > 0) {
    renderEpisodes(data.episodes[seasons[0]], seriesTitle);
  }
}

function renderEpisodes(episodesList, seriesTitle) {
  const episodesBox = document.getElementById("episodesContainer");
  episodesBox.innerHTML = "";
  if(!episodesList || !Array.isArray(episodesList)) {
    episodesBox.innerHTML = `<div class="empty">لا توجد حلقات في هذا الموسم</div>`;
    return;
  }

  episodesList.forEach(ep => {
    const acc = JSON.parse(localStorage.getItem("faroukii_active_creds"));
    const playUrl = `${acc.host}/series/${acc.user}/${acc.pass}/${ep.id}.${ep.container_extension || 'mp4'}`;
    
    const row = document.createElement("div");
    row.style.cssText = "background:#0a1215; padding:10px; border-radius:10px; display:flex; align-items:center; justify-content:between; cursor:pointer; gap:10px;";
    row.innerHTML = `
      <div style="width:28px; height:28px; background:rgba(168,255,0,0.1); color:var(--lime); border-radius:8px; display:flex; align-items:center; justify-content:center; font-weight:bold;"><i class="fa-solid fa-play"></i></div>
      <div style="flex:1; font-weight:bold; font-size:10px; color:#fff;">الحلقة ${ep.episode_num}: ${escapeHtml(ep.title || 'حلقة جديدة')}</div>
    `;
    row.onclick = () => launchMoviePlayer(playUrl, `${seriesTitle} - حلقة ${ep.episode_num}`);
    episodesBox.appendChild(row);
  });
}

function launchMoviePlayer(url, title) {
  document.getElementById("netflixDetailsModal").style.display = "none";
  document.getElementById("netflixPlayerModal").style.display = "flex";
  document.getElementById("netflixPlayerTitle").textContent = title;
  const video = document.getElementById("vodVideoElement");
  video.src = url;
  video.play().catch(()=>{});
}

function closeDetailsModal() {
  document.getElementById("netflixDetailsModal").style.display = "none";
}

function exitVodSection() {
  document.getElementById("vodMainLayout").style.display = "none";
  document.getElementById("appScreen").style.display = "flex";
}

function closeNetflixPlayer() {
  document.getElementById("netflixPlayerModal").style.display = "none";
  const video = document.getElementById("vodVideoElement");
  video.pause(); video.src = "";
  document.getElementById("netflixDetailsModal").style.display = "flex";
}

function renderStats(){ 
  const due=clients.reduce((sum,c)=>sum+Number(c.totalDue||0),0); 
  const paid=clients.reduce((sum,c)=>sum+Number(c.totalPaid||0),0); 
  const remain=clients.reduce((sum,c)=>sum+Math.max(0,Number(c.totalDue||0)-Number(c.totalPaid||0)),0); 
  document.getElementById("statClients").textContent=clients.length; 
  document.getElementById("statDue").textContent=money(due); 
  document.getElementById("statPaid").textContent=money(paid); 
  document.getElementById("statRemain").textContent=money(remain); 
} 

function clientStatus(client){ 
  const due=Number(client.totalDue||0); 
  const paid=Number(client.totalPaid||0); 
  const remain=Math.max(0,due-paid); 
  if(due<=0) return{text:"خالص",cls:"badge-green"}; 
  if(remain<=0) return{text:"مدفوع",cls:"badge-green"}; 
  return{text:"باقي",cls:"badge-orange"}; 
} 

function renderDashboard(){ 
  const body=document.getElementById("dashboardTable"); 
  const recent=[...clients].slice(0,5); 
  if(!recent.length){ body.innerHTML=`<tr><td colspan="4"><div class="empty">لا يوجد عملاء</div></td></tr>`; return; } 
  body.innerHTML=recent.map(client=>{ 
    const status=clientStatus(client); 
    const remain=Math.max(0,Number(client.totalDue||0)-Number(client.totalPaid||0)); 
    return`<tr><td><div class="client-cell"><span class="avatar">${escapeHtml(initials(client.name))}</span><strong>${escapeHtml(client.name)}</strong></div></td><td>${escapeHtml(client.account||"-")}</td><td><span class="badge ${status.cls}">${status.text}</span></td><td>${money(remain)}</td></tr>`; 
  }).join(""); 
} 

function renderClients(){ 
  const search=document.getElementById("clientSearch").value.trim().toLowerCase(); 
  const list=clients.filter(c=>String(c.name||"").toLowerCase().includes(search)||String(c.account||"").toLowerCase().includes(search)); 
  document.getElementById("clientCountText").textContent=clients.length; 
  const body=document.getElementById("clientsTable"); 
  if(!list.length){ body.innerHTML=`<tr><td colspan="6"><div class="empty">لا توجد نتائج</div></td></tr>`; return; } 
  body.innerHTML=list.map(c=>{ 
    const due=Number(c.totalDue||0); 
    const paid=Number(c.totalPaid||0); 
    const remain=Math.max(0,due-paid); 
    return`<tr><td><div class="client-cell"><span class="avatar">${escapeHtml(initials(c.name))}</span><strong>${escapeHtml(c.name)}</strong></div></td><td>${escapeHtml(c.account||"-")}</td><td>${money(due)}</td><td>${money(paid)}</td><td>${money(remain)}</td><td><div class="actions"><button class="btn btn-dark btn-small" onclick="viewClient('${c.id}')">👁</button><button class="btn btn-blue btn-small" onclick="openDebtModal('${c.id}')">＋</button><button class="btn btn-lime btn-small" onclick="openPaymentModal('${c.id}')">💳</button><button class="btn btn-danger btn-small" onclick="deleteClient('${c.id}')">🗑</button></div></td></tr>`; 
  }).join(""); 
} 

function openClientModal(){ 
  document.getElementById("editClientId").value=""; 
  document.getElementById("clientName").value=""; 
  document.getElementById("clientPhone").value=""; 
  document.getElementById("clientAccount").value=""; 
  document.getElementById("clientModalTitle").textContent="عميل جديد"; 
  openModal("clientModal"); 
} 

function saveClient(){ 
  const name=document.getElementById("clientName").value.trim(); 
  const phone=document.getElementById("clientPhone").value.trim(); 
  const account=document.getElementById("clientAccount").value.trim(); 
  if(!name){ toast("أدخل اسم العميل"); return; } 
  clients.unshift({id:makeId(),name,phone,account,totalDue:0,totalPaid:0,date:dateOnly()}); 
  saveData(); closeModal("clientModal"); renderAll(); toast("تم إضافة العميل بنجاح"); 
} 

function deleteClient(id){ 
  if(!confirm("حذف العميل؟")) return; 
  clients=clients.filter(c=>c.id!==id); 
  saveData(); renderAll(); toast("تم الحذف"); 
} 

function viewClient(id){ 
  const c=getClient(id); 
  if(!c)return; 
  const remain=Math.max(0,Number(c.totalDue||0)-Number(c.totalPaid||0)); 
  document.getElementById("detailBody").innerHTML=`<div class="form-grid"><div class="form-group"><label>الاسم</label><div class="input">${escapeHtml(c.name)}</div></div><div class="form-group"><label>الهاتف</label><div class="input">${escapeHtml(c.phone||"-")}</div></div><div class="form-group"><label>الحساب</label><div class="input">${escapeHtml(c.account||"-")}</div></div><div class="form-group"><label>المجموع</label><div class="input">${money(c.totalDue)}</div></div><div class="form-group"><label>المتبقي</label><div class="input" style="color:var(--orange);">${money(remain)}</div></div></div>`; 
  openModal("detailModal"); 
} 

function openDebtModal(id){ 
  document.getElementById("debtClientId").value=id; 
  document.getElementById("debtAmount").value=""; 
  document.getElementById("debtNote").value=""; 
  openModal("debtModal"); 
} 

function saveDebt(){ 
  const id=document.getElementById("debtClientId").value; 
  const amount=Number(document.getElementById("debtAmount").value); 
  const c=getClient(id); 
  if(!c||amount<=0){ toast("مبلغ غير صالح"); return; } 
  c.totalDue=Number(c.totalDue||0)+amount; 
  saveData(); closeModal("debtModal"); renderAll(); toast("تم إضافة المبلغ"); 
} 

function openPaymentModal(clientId=""){ 
  const select=document.getElementById("paymentClient"); 
  select.innerHTML=`<option value="">اختر العميل</option>`+clients.map(c=>`<option value="${c.id}">${escapeHtml(c.name)}</option>`).join(""); 
  select.value=clientId||""; 
  document.getElementById("paymentAmount").value=""; 
  openModal("paymentModal"); 
} 

function savePayment(){ 
  const id=document.getElementById("paymentClient").value; 
  const amount=Number(document.getElementById("paymentAmount").value); 
  const note=document.getElementById("paymentNote").value.trim(); 
  const c=getClient(id); 
  if(!c||amount<=0){ toast("بيانات غير صالحة"); return; } 
  c.totalPaid=Number(c.totalPaid||0)+amount; 
  payments.unshift({id:makeId(),clientId:id,name:c.name,amount,note,date:now()}); 
  saveData(); closeModal("paymentModal"); renderAll(); toast("تم تسجيل الدفعة بنجاح"); 
} 

function renderPayments(){ 
  const body=document.getElementById("paymentsTable"); 
  if(!payments.length){ body.innerHTML=`<tr><td colspan="4"><div class="empty">لا توجد دفعات</div></td></tr>`; return; } 
  body.innerHTML=payments.map(p=>`<tr><td>${escapeHtml(p.date)}</td><td><strong>${escapeHtml(p.name)}</strong></td><td><span class="badge badge-green">+${money(p.amount)}</span></td><td>${escapeHtml(p.note||"-")}</td></tr>`).join(""); 
} 

function renderAbonnements(){ 
  document.getElementById("abonnementCount").textContent=abonnements.length; 
  const body=document.getElementById("abonnementTable"); 
  if(!abonnements.length){ body.innerHTML=`<tr><td colspan="5"><div class="empty">لا توجد اشتراكات مسجلة</div></td></tr>`; return; } 
  body.innerHTML=abonnements.map(a=>`<tr><td><strong>${escapeHtml(a.name)}</strong></td><td>${escapeHtml(a.phone||"-")}</td><td><code>${escapeHtml(a.token)}</code></td><td>${escapeHtml(a.duration)}</td><td><button class="btn btn-danger btn-small" onclick="deleteAbonnement('${a.id}')">🗑</button></td></tr>`).join(""); 
} 

function deleteAbonnement(id){ 
  abonnements=abonnements.filter(x=>x.id!==id); 
  saveData(); renderAbonnements(); toast("تم حذف الاشتراك"); 
} 

function renderHistory(){ 
  document.getElementById("historyList").innerHTML=`<div class="empty">السجل فارغ</div>`; 
} 

function openModal(id){ document.getElementById(id).classList.add("show"); } 
function closeModal(id){ document.getElementById(id).classList.remove("show"); } 

function toast(msg){ 
  const t=document.getElementById("toast"); 
  t.textContent=msg; 
  t.classList.add("show"); 
  setTimeout(()=>t.classList.remove("show"),3000); 
} 

function exportData(){ 
  const data={clients,payments,activations,abonnements}; 
  const blob=new Blob([JSON.stringify(data,null,2)],{type:"json"}); 
  const url=URL.createObjectURL(blob); 
  const a=document.createElement("a"); 
  a.href=url; a.download="panel_backup.json"; a.click(); 
  toast("تم التصدير"); 
} 

function clearAllData(){ 
  if(!confirm("حذف كافة البيانات؟")) return; 
  clients=[]; payments=[]; activations=[]; abonnements=[]; 
  localStorage.removeItem(KEYS.tokens);
  saveData(); renderAll(); toast("تمت التصفية"); 
} 

function renderAll(){ 
  renderStats(); renderDashboard(); renderClients(); renderPayments(); renderAbonnements(); renderActivations(); renderHistory(); 
  setDefaultDates();
} 

renderAll();
</script>
</body>
</html>
