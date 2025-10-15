!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent"> 
<meta name="apple-mobile-web-app-title" content="ØªÙ‚Ø§Ø±ÙŠØ±"> 
<meta name="theme-color" content="#1982c4"> 
<title>ðŸ“Š ÙˆØ§Ø¬Ù‡Ø© Ø§Ù„ØªÙ‚Ø§Ø±ÙŠØ± Ø§Ù„ÙŠÙˆÙ…ÙŠØ©</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  /* ØªÙ†Ø³ÙŠÙ‚ Ø´Ø±ÙŠØ· Ø§Ù„Ø¥Ø¶Ø§ÙØ© Ù„Ù„Ø´Ø§Ø´Ø© Ø§Ù„Ø±Ø¦ÙŠØ³ÙŠØ© */
  #add-to-home-banner {
    background: #4682b4; /* Steel Blue */
    color: white;
    padding: 10px;
    font-size: 15px;
    font-weight: 600;
    text-align: center;
    position: sticky;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    display: none; /* ÙŠØªÙ… Ø¥Ø¸Ù‡Ø§Ø±Ù‡ Ø¨Ø§Ù„Ù€ JavaScript */
  }
  #add-to-home-banner button {
    background: #3cb371; /* Medium Sea Green */
    color: white;
    border: none;
    padding: 6px 12px;
    margin-right: 10px;
    border-radius: 8px;
    font-size: 14px;
    cursor: pointer;
  }
  #add-to-home-banner button:hover {
    background: #2e8b57;
  }
  body { font-family: "Cairo", sans-serif; background: linear-gradient(135deg, #f9f9f9, #e0e7ff); text-align: center; padding: 20px; }
  h1 { color: #222; font-size: 26px; margin-bottom: 8px; }
  p { color: #555; font-size: 16px; margin-bottom: 25px; }
  .button-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; max-width: 420px; margin: 0 auto; }
  button { padding: 15px; font-size: 18px; font-weight: bold; border: none; border-radius: 16px; color: white; cursor: pointer; transition: transform 0.2s, box-shadow 0.2s; }
  button:hover { transform: scale(1.05); box-shadow: 0 4px 10px rgba(0,0,0,0.2); }
  .b1 { background: #ff595e; } .b2 { background: #ffca3a; color: #333; } .b3 { background: #8ac926; } .b4 { background: #1982c4; } 
  .b5 { background: #6a4c93; } .b6 { background: #f3722c; } .b7 { background: #90be6d; } .b8 { background: #277da1; } 
  .b9 { background: #f9844a; } .b10 { background: #43aa8b; } 
  footer { margin-top: 30px; color: #777; font-size: 13px; }
  #pdf-loader-iframe { display: none; width: 0; height: 0; border: none; }

  /* ÙˆØ§Ø¬Ù‡Ø© Ø§Ù„Ø¯Ø®ÙˆÙ„ ÙˆØ¥Ù†Ø´Ø§Ø¡ Ø§Ù„Ø­Ø³Ø§Ø¨ */
  .auth-screen { max-width: 400px; margin: 80px auto; background: white; padding: 25px; border-radius: 16px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
  input { width: 90%; padding: 12px; margin: 8px 0; border-radius: 8px; border: 1px solid #ccc; font-size: 16px; }
  .btn-main { background: #1982c4; color: white; border: none; padding: 12px 20px; border-radius: 10px; font-size: 16px; cursor: pointer; width: 95%; }
  .btn-main:hover { background: #155a8a; }
  .btn-alt { background: #777; color: white; border: none; padding: 10px 16px; border-radius: 8px; font-size: 14px; cursor: pointer; margin-top: 10px; }
  .btn-alt:hover { background: #555; }
  .btn-link { background: none; border: none; color: #1982c4; cursor: pointer; margin-top: 10px; font-size: 14px; }
  #logout-btn { background: #ff595e; color: white; border: none; padding: 10px 18px; border-radius: 10px; font-size: 15px; cursor: pointer; margin-top: 20px; }
  #logout-btn:hover { background: #d94a51; }
  .msg { font-size: 14px; margin-top: 8px; }
  .msg.error { color: #e63946; }
  .msg.success { color: #2a9d8f; }

  /* Ø²Ø± Ø¥Ø¯Ø§Ø±Ø© Ø§Ù„Ù…Ø³ØªØ®Ø¯Ù…ÙŠÙ† */
  #admin-btn { margin-top: 15px; background: #6a4c93; color: #fff; border: none; padding: 10px 18px; border-radius: 10px; cursor: pointer; font-size: 14px; display: none; }
  #admin-btn:hover { background: #563d78; }

  /* Modal */
  #admin-modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.5); justify-content: center; align-items: center; z-index: 999; }
  #admin-modal .modal-content { background: #fff; padding: 20px; border-radius: 12px; max-width: 500px; max-height: 70%; overflow-y: auto; text-align: left; }
  .user-item { display: flex; justify-content: space-between; padding: 6px 10px; border-bottom: 1px solid #eee; font-size: 14px; }
  .user-item input { width: 50%; padding: 4px; font-size: 14px; border-radius: 6px; border: 1px solid #ccc; }
  .save-btn { background: #1982c4; color: #fff; border: none; padding: 4px 10px; border-radius: 6px; cursor: pointer; margin-left: 6px; font-size: 13px; }
  .save-btn:hover { background: #155a8a; }
</style>
</head>
<body>

<div id="add-to-home-banner">
  <span id="home-instructions"></span>
  <button onclick="hideHomeBanner()">Ø­Ø³Ù†Ù‹Ø§ØŒ ÙÙ‡Ù…Øª</button>
</div>

<div id="login-screen" class="auth-screen">
  <h2>ðŸ”’ ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø¯Ø®ÙˆÙ„</h2>
  <input type="email" id="email" placeholder="Ø§Ù„Ø¨Ø±ÙŠØ¯ Ø§Ù„Ø¥Ù„ÙƒØªØ±ÙˆÙ†ÙŠ">
  <input type="password" id="password" placeholder="ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ±">
  <button class="btn-main" onclick="login()">ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø¯Ø®ÙˆÙ„</button>
  <p class="msg" id="login-msg"></p>
  <button class="btn-link" onclick="forgotPassword()">Ù†Ø³ÙŠØª ÙƒÙ„Ù…Ø© Ø§Ù„Ø³Ø±ØŸ</button>
  <hr style="margin:14px 0;border:none;border-top:1px solid #eee" />
  <button class="btn-alt" onclick="showRegister()">Ø¥Ù†Ø´Ø§Ø¡ Ø­Ø³Ø§Ø¨ Ø¬Ø¯ÙŠØ¯</button>
</div>

<div id="register-screen" class="auth-screen" style="display:none;">
  <h2>ðŸ“ Ø¥Ù†Ø´Ø§Ø¡ Ø­Ø³Ø§Ø¨</h2>
  <input type="email" id="new-email" placeholder="Ø§Ù„Ø¨Ø±ÙŠØ¯ Ø§Ù„Ø¥Ù„ÙƒØªØ±ÙˆÙ†ÙŠ (ÙŠØ¬Ø¨ Ø£Ù† ÙŠÙ†ØªÙ‡ÙŠ Ø¨Ù€ @dakahlia.net)">
  <input type="password" id="new-password" placeholder="ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ±">
  <button class="btn-main" onclick="register()">ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø­Ø³Ø§Ø¨</button>
  <p class="msg" id="register-msg"></p>
  <button class="btn-alt" onclick="showLogin()">Ø±Ø¬ÙˆØ¹ Ù„ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø¯Ø®ÙˆÙ„</button>
</div>

<div id="reports-screen" style="display:none;">
  <h1>ðŸ“Š ÙˆØ§Ø¬Ù‡Ø© Ø§Ù„ØªÙ‚Ø§Ø±ÙŠØ± Ø§Ù„ÙŠÙˆÙ…ÙŠØ©</h1>
  <p>Ø§Ø¶ØºØ· Ø¹Ù„Ù‰ Ø§Ù„ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù…Ø·Ù„ÙˆØ¨ Ù„ØªØ­Ù…ÙŠÙ„ Ù…Ù„Ù PDF Ù…Ù† Google Sheets</p>

  <div class="button-grid">
    <button class="b1" onclick="openPDF('https://docs.google.com/spreadsheets/d/1Cab_-qOEAEBru5O3RFgoXqVjyY6fS5mXCmsEN-6qtTc/export?format=pdf&portrait=true&size=A4&fitw=true&sheetnames=false&printtitle=false&pagenumbers=false&gridlines=false&fzr=false&gid=789749771&range=A1%3AE252&attachment=true')">ðŸ“¦ ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ø¥Ù†ØªØ§Ø¬</button>
    <button class="b2">ðŸ“Š ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù…Ø®Ø²ÙˆÙ†</button>
    <button class="b3">ðŸ’° ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù…Ø¨ÙŠØ¹Ø§Øª</button>
    <button class="b4">ðŸ§° ØªÙ‚Ø±ÙŠØ± Ø§Ù„ØµÙŠØ§Ù†Ø©</button>
    <button class="b5">ðŸ§ª ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ø¬ÙˆØ¯Ø©</button>
    <button class="b6">ðŸ‘· ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù…ÙˆØ§Ø±Ø¯</button>
    <button class="b7">ðŸ“¦ ØªÙ‚Ø±ÙŠØ± Ø§Ù„ØªØ¹Ø¨Ø¦Ø©</button>
    <button class="b8">ðŸš› ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù†Ù‚Ù„</button>
    <button class="b9">ðŸŽ ØªÙ‚Ø±ÙŠØ± Ø§Ù„ØªØºÙ„ÙŠÙ</button>
    <button class="b10">ðŸ“˜ Ø§Ù„ØªÙ‚Ø±ÙŠØ± Ø§Ù„Ù†Ù‡Ø§Ø¦ÙŠ</button>
  </div>

  <button id="logout-btn" onclick="logout()">ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø®Ø±ÙˆØ¬</button>
  <button id="admin-btn" onclick="openAdminModal()">âš™ï¸ Ø¥Ø¯Ø§Ø±Ø© Ø§Ù„Ù…Ø³ØªØ®Ø¯Ù…ÙŠÙ†</button>

  <footer>Â© Ø¥Ø¹Ø¯Ø§Ø¯ : Ø£/ Ø£Ø­Ù…Ø¯ Ø­Ù…Ø¯Ø§Ù† - Ø±Ø¦ÙŠØ³ Ù‚Ø³Ù… Ø§Ù„ØªØ®Ø·ÙŠØ· ÙˆØ§Ù„Ù…ØªØ§Ø¨Ø¹Ø©</footer>
  <iframe id="pdf-loader-iframe" aria-hidden="true"></iframe>
</div>

<div id="admin-modal">
  <div class="modal-content">
    <h3>ðŸ“‹ Ø§Ù„Ù…Ø³ØªØ®Ø¯Ù…ÙˆÙ† Ø§Ù„Ù…Ø³Ø¬Ù„ÙˆÙ†</h3>
    <div id="users-list"></div>
    <button class="btn-alt" onclick="closeAdminModal()" style="margin-top:10px">Ø¥ØºÙ„Ø§Ù‚</button>
  </div>
</div>

<script>
const NO_PASS_USERS=['ahmed.hamdan@dakahlia.net','sadat.planning.officer@dakahlia.net'];
const ADMIN_EMAIL='ahmed.hamdan@dakahlia.net';

function showRegister(){ document.getElementById('login-screen').style.display='none'; document.getElementById('register-screen').style.display='block'; clearMsgs(); }
function showLogin(){ document.getElementById('register-screen').style.display='none'; document.getElementById('login-screen').style.display='block'; clearMsgs(); }
function showReports() {
  document.getElementById('login-screen').style.display = 'none';
  document.getElementById('register-screen').style.display = 'none';
  document.getElementById('reports-screen').style.display = 'block';
}

function getUsers(){ try{ return JSON.parse(localStorage.getItem('users')||'[]'); }catch(e){return[];} }
function saveUsers(arr){ localStorage.setItem('users',JSON.stringify(arr||[])); }
function clearMsgs(){ document.getElementById('login-msg').textContent=''; document.getElementById('register-msg').textContent=''; }

function register(){
  const email=(document.getElementById('new-email').value||'').trim().toLowerCase();
  const password=(document.getElementById('new-password').value||'').trim();
  const msgEl=document.getElementById('register-msg');
  msgEl.className='msg';
  if(!email||!password){ msgEl.classList.add('error'); msgEl.textContent='âš ï¸ Ø§Ù„Ø±Ø¬Ø§Ø¡ Ø¥Ø¯Ø®Ø§Ù„ Ø§Ù„Ø¨Ø±ÙŠØ¯ ÙˆÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ±'; return; }
  if(!email.endsWith('@dakahlia.net')){ msgEl.classList.add('error'); msgEl.textContent='âŒ ÙŠØ¬Ø¨ Ø£Ù† ÙŠÙƒÙˆÙ† Ø§Ù„Ø¨Ø±ÙŠØ¯ Ù…Ù† Ù†Ø·Ø§Ù‚ @dakahlia.net'; return; }
  if(password.length<4){ msgEl.classList.add('error'); msgEl.textContent='âš ï¸ ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ± Ù‚ØµÙŠØ±Ø©'; return; }
  const users=getUsers();
  if(users.some(u=>u.email===email)){ msgEl.classList.add('error'); msgEl.textContent='âš ï¸ Ù‡Ø°Ø§ Ø§Ù„Ø¨Ø±ÙŠØ¯ Ù…Ø³Ø¬Ù„ Ø¨Ø§Ù„ÙØ¹Ù„'; return; }
  users.push({ email,password,createdAt:new Date().toISOString() });
  saveUsers(users);
  msgEl.classList.add('success'); msgEl.textContent='âœ… ØªÙ… Ø¥Ù†Ø´Ø§Ø¡ Ø§Ù„Ø­Ø³Ø§Ø¨ Ø¨Ù†Ø¬Ø§Ø­';
  setTimeout(()=>showLogin(),1000);
}

function login(){
  const email=(document.getElementById('email').value||'').trim().toLowerCase();
  const password=(document.getElementById('password').value||'').trim();
  const msgEl=document.getElementById('login-msg');
  msgEl.className='msg';
  if(!email){ msgEl.classList.add('error'); msgEl.textContent='âš ï¸ Ø§Ø¯Ø®Ù„ Ø§Ù„Ø¨Ø±ÙŠØ¯'; return; }
  const users=getUsers();
  const found=users.find(u=>u.email===email&&u.password===password);
  if(found||NO_PASS_USERS.includes(email)){
    localStorage.setItem('loggedIn','true');
    localStorage.setItem('currentUser',email);
    msgEl.classList.add('success'); msgEl.textContent='âœ… ØªÙ… ØªØ³Ø¬ÙŠÙ„ Ø§Ù„Ø¯Ø®ÙˆÙ„';
    setTimeout(()=>{
      showReports();
      if(email===ADMIN_EMAIL){ document.getElementById('admin-btn').style.display='inline-block'; }
    },500);
  } else { msgEl.classList.add('error'); msgEl.textContent='âŒ Ø§Ù„Ø¨Ø±ÙŠØ¯ Ø£Ùˆ ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ± ØºÙŠØ± ØµØ­ÙŠØ­Ø©'; }
}

function forgotPassword(){ alert('Ø³ÙŠØªÙ… ÙØªØ­ ØªØ·Ø¨ÙŠÙ‚ Ø§Ù„Ø¨Ø±ÙŠØ¯ Ù„Ù†Ø³Ø® ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ± (ØªÙ… Ø¯Ù…Ø¬ Ø§Ù„Ù†Ø³Ø®Ø© Ø§Ù„Ù‚Ø¯ÙŠÙ…Ø© Ù‡Ù†Ø§)'); }

function logout(){
  localStorage.removeItem('loggedIn');
  localStorage.removeItem('currentUser');
  document.getElementById('reports-screen').style.display='none';
  document.getElementById('login-screen').style.display='block';
}

function openPDF(url) { handleOpenExportUrl(url); }

function isMobileDevice() {
  return /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini|Mobile/i.test(navigator.userAgent || '');
}
function handleOpenExportUrl(exportUrl) {
  if (isMobileDevice()) {
    try {
      var iframe = document.getElementById('pdf-loader-iframe');
      iframe.style.display = 'block';
      iframe.width = '100%';
      iframe.height = '100%';
      iframe.src = exportUrl;
      setTimeout(function(){
        iframe.style.display = 'none';
        iframe.width = '0';
        iframe.height = '0';
      }, 3000);
    } catch (e) {
      window.open(exportUrl, '_blank', 'noopener,noreferrer');
    }
  } else {
    window.open(exportUrl, '_blank', 'noopener,noreferrer');
  }
}

/* Admin modal Ù…Ø¹ ØªØ¹Ø¯ÙŠÙ„ Ø§Ù„Ø¨Ø§Ø³ÙˆØ±Ø¯ */
function openAdminModal(){
  const current=localStorage.getItem('currentUser');
  if(current!==ADMIN_EMAIL){ alert('ØºÙŠØ± Ù…ØµØ±Ø­'); return; }
  const listEl=document.getElementById('users-list'); listEl.innerHTML='';
  getUsers().forEach((u,i)=>{
    const div=document.createElement('div');
    div.className='user-item';
    div.innerHTML=`<span>${u.email}</span><input type="text" value="${u.password}" id="pw-${i}"><button class="save-btn" onclick="savePassword(${i})">Ø­ÙØ¸</button>`;
    listEl.appendChild(div);
  });
  document.getElementById('admin-modal').style.display='flex';
}
function closeAdminModal(){ document.getElementById('admin-modal').style.display='none'; }
function savePassword(idx){
  const users=getUsers();
  const newPass=document.getElementById(`pw-${idx}`).value.trim();
  if(newPass.length<4){ alert('ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ± ÙŠØ¬Ø¨ Ø£Ù† ØªÙƒÙˆÙ† 4 Ø£Ø­Ø±Ù Ø¹Ù„Ù‰ Ø§Ù„Ø£Ù‚Ù„'); return; }
  users[idx].password=newPass;
  saveUsers(users);
  alert('âœ… ØªÙ… ØªØ­Ø¯ÙŠØ« ÙƒÙ„Ù…Ø© Ø§Ù„Ù…Ø±ÙˆØ± Ø¨Ù†Ø¬Ø§Ø­');
}

/* Ø¥Ø¸Ù‡Ø§Ø± Ø§Ù„Ø¥Ø±Ø´Ø§Ø¯Ø§Øª Ù„Ù„Ø¥Ø¶Ø§ÙØ© Ù„Ù„Ø´Ø§Ø´Ø© Ø§Ù„Ø±Ø¦ÙŠØ³ÙŠØ© */
function showHomeBanner() {
    const banner = document.getElementById('add-to-home-banner');
    const instructions = document.getElementById('home-instructions');
    const userAgent = navigator.userAgent || '';

    if (userAgent.match(/iPhone|iPad|iPod/i)) {
        instructions.innerHTML = 'Ù„Ø¥Ø¶Ø§ÙØ© Ø§Ø®ØªØµØ§Ø±: Ø§Ø¶ØºØ· Ø¹Ù„Ù‰ **Ø£ÙŠÙ‚ÙˆÙ†Ø© Ø§Ù„Ù…Ø´Ø§Ø±ÙƒØ©** (&#8682;) Ø«Ù… "Ø§Ù„Ø¥Ø¶Ø§ÙØ© Ù„Ù„Ø´Ø§Ø´Ø© Ø§Ù„Ø±Ø¦ÙŠØ³ÙŠØ©".';
        banner.style.display = 'block';
    } else if (userAgent.match(/Android/i)) {
        instructions.innerHTML = 'Ù„Ø¥Ø¶Ø§ÙØ© Ø§Ø®ØªØµØ§Ø±: Ø§Ø¶ØºØ· Ø¹Ù„Ù‰ **Ø§Ù„Ø«Ù„Ø§Ø« Ù†Ù‚Ø§Ø·** (&#8942;) Ø«Ù… "Ø§Ù„Ø¥Ø¶Ø§ÙØ© Ù„Ù„Ø´Ø§Ø´Ø© Ø§Ù„Ø±Ø¦ÙŠØ³ÙŠØ©".';
        // Ù„Ø§ ØªØ¸Ù‡Ø± Banner ÙÙŠ Android Ø¥Ù„Ø§ Ø¥Ø°Ø§ ÙƒØ§Ù† Ø§Ù„Ø®ÙŠØ§Ø± ØºÙŠØ± Ù…ÙˆØ¬ÙˆØ¯
        // ÙˆÙ„ÙƒÙ† Ø¨Ù…Ø§ Ø£Ù† Ø§Ù„Ø®ÙŠØ§Ø± ØºÙŠØ± Ù…ÙˆØ¬ÙˆØ¯ØŒ Ù†Ø¹Ø±Ø¶ Ø§Ù„Ø¥Ø±Ø´Ø§Ø¯Ø§Øª Ø§Ù„ÙŠØ¯ÙˆÙŠØ©
        banner.style.display = 'block';
    }
}

function hideHomeBanner() {
    document.getElementById('add-to-home-banner').style.display = 'none';
    localStorage.setItem('homeBannerDismissed', 'true');
}


/* Ø¹Ù†Ø¯ ØªØ­Ù…ÙŠÙ„ Ø§Ù„ØµÙØ­Ø© */
window.onload=function(){
  if(localStorage.getItem('loggedIn')==='true'){
    showReports();
    const current=localStorage.getItem('currentUser');
    if(current===ADMIN_EMAIL){ document.getElementById('admin-btn').style.display='inline-block'; }
  }

  // Ø¹Ø±Ø¶ Ø§Ù„Ø¥Ø±Ø´Ø§Ø¯Ø§Øª Ø§Ù„ÙŠØ¯ÙˆÙŠØ© Ø¥Ø°Ø§ Ù„Ù… ÙŠÙƒÙ† Ù‚Ø¯ ØªÙ… Ø¥Ø®ÙØ§Ø¤Ù‡Ø§ Ù…Ù† Ù‚Ø¨Ù„
  if (isMobileDevice() && !localStorage.getItem('homeBannerDismissed')) {
      showHomeBanner();
  }
};
</script>
</body>
</html>
