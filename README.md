<!DOCTYPE html>

<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>نظام التنظيف الأهلية</title>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{--bg:#0a0e1a;--card:#111827;--c2:#1a2235;--bdr:#2a3347;--gl:#10b981;--gol:#f59e0b;--rd:#ef4444;--bl:#3b82f6;--or:#f97316;--mu:#6b7280;--tx:#f1f5f9;--pu:#8b5cf6}
body{background:var(--bg);font-family:'Tajawal',sans-serif;color:var(--tx);direction:rtl;min-height:100vh}
input,select,textarea{font-family:'Tajawal',sans-serif;font-size:.88rem;background:var(--bg);border:1px solid var(--bdr);color:var(--tx);padding:8px 11px;border-radius:8px;width:100%;outline:none;box-sizing:border-box}
input:focus,select:focus,textarea:focus{border-color:var(--bl);box-shadow:0 0 0 3px rgba(59,130,246,.15)}
select option{background:var(--c2)}
button{font-family:'Tajawal',sans-serif;cursor:pointer}
table{width:100%;border-collapse:collapse}
th{padding:8px;text-align:center;color:var(--mu);font-size:.66rem;font-weight:700;border-bottom:1px solid var(--bdr);white-space:nowrap;background:var(--c2)}
td{padding:7px 8px;text-align:center;border-bottom:1px solid rgba(42,51,71,.5);vertical-align:middle;font-size:.77rem}
tr:hover td{background:rgba(255,255,255,.015)}
.card{background:var(--card);border:1px solid var(--bdr);border-radius:10px;padding:16px;margin-bottom:12px}
.stitle{font-size:.9rem;font-weight:800;color:var(--gol);margin-bottom:12px;padding-bottom:8px;border-bottom:1px solid var(--bdr)}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px}
.g4{display:grid;grid-template-columns:repeat(4,1fr);gap:6px}
.fld{margin-bottom:10px}
.fld label{display:block;font-size:.73rem;color:var(--mu);margin-bottom:4px;font-weight:600}
.topbar{background:var(--card);border-bottom:1px solid var(--bdr);padding:9px 14px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100;box-shadow:0 4px 20px rgba(0,0,0,.3)}
.tabs{display:flex;background:var(--c2);border-bottom:1px solid var(--bdr);overflow-x:auto;padding:0 8px}
.tab{font-family:'Tajawal',sans-serif;font-weight:700;font-size:.76rem;padding:9px 12px;background:none;border:none;border-bottom:2px solid transparent;color:var(--mu);cursor:pointer;white-space:nowrap;transition:all .15s}
.tab.on{color:var(--gol);border-bottom-color:var(--gol)}
.page{display:none;padding:12px}
.page.on{display:block}
.badge{display:inline-block;padding:2px 9px;border-radius:20px;font-size:.69rem;font-weight:700}
.b-green{background:rgba(16,185,129,.15);color:#10b981;border:1px solid rgba(16,185,129,.4)}
.b-red{background:rgba(239,68,68,.15);color:#f87171;border:1px solid rgba(239,68,68,.4)}
.b-gold{background:rgba(245,158,11,.15);color:#fbbf24;border:1px solid rgba(245,158,11,.4)}
.b-blue{background:rgba(59,130,246,.15);color:#60a5fa;border:1px solid rgba(59,130,246,.4)}
.b-orange{background:rgba(249,115,22,.15);color:#fb923c;border:1px solid rgba(249,115,22,.4)}
.b-purple{background:rgba(139,92,246,.15);color:#a78bfa;border:1px solid rgba(139,92,246,.4)}
.b-paid{background:rgba(16,185,129,.15);color:#10b981;border:1px solid rgba(16,185,129,.4)}
.b-unpaid{background:rgba(239,68,68,.15);color:#f87171;border:1px solid rgba(239,68,68,.4)}
.b-absent{background:rgba(249,115,22,.15);color:#fb923c;border:1px solid rgba(249,115,22,.4)}
.btn{display:inline-flex;align-items:center;gap:5px;font-family:'Tajawal',sans-serif;font-weight:700;font-size:.84rem;padding:8px 14px;border:none;border-radius:8px;cursor:pointer;transition:all .15s}
.btn:active{transform:scale(.97)}
.btn-green{background:#059669;color:#fff}
.btn-blue{background:#2563eb;color:#fff}
.btn-gold{background:#d97706;color:#000}
.btn-red{background:rgba(239,68,68,.85);color:#fff}
.btn-wa{background:#25d366;color:#fff}
.btn-ghost{background:var(--c2);color:var(--mu);border:1px solid var(--bdr)}
.btn-purple{background:#7c3aed;color:#fff}
.btn-full{width:100%;justify-content:center}
.tbtn{font-family:'Tajawal',sans-serif;font-size:.69rem;font-weight:700;padding:3px 7px;border-radius:5px;cursor:pointer;margin:1px;border:1px solid}
.tb-wa{background:rgba(37,211,102,.1);color:#25d366;border-color:rgba(37,211,102,.3)}
.tb-rc{background:rgba(245,158,11,.1);color:#fbbf24;border-color:rgba(245,158,11,.3)}
.tb-ed{background:rgba(59,130,246,.1);color:#60a5fa;border-color:rgba(59,130,246,.3)}
.tb-dl{background:rgba(239,68,68,.1);color:#f87171;border-color:rgba(239,68,68,.3)}
.tb-map{background:rgba(16,185,129,.1);color:#34d399;border-color:rgba(16,185,129,.3)}
.sbox{background:var(--card);border:1px solid var(--bdr);border-radius:10px;padding:12px 10px;text-align:center}
.sbox .n{font-size:1.3rem;font-weight:900;line-height:1}
.sbox .l{font-size:.67rem;color:var(--mu);margin-top:4px;font-weight:600}
.mo-btn{font-family:'Tajawal',sans-serif;font-weight:700;font-size:.72rem;padding:6px 3px;border-radius:7px;cursor:pointer;text-align:center;background:var(--bg);border:2px solid var(--bdr);color:var(--mu);width:100%}
.mo-btn.on{background:rgba(16,185,129,.15);border-color:var(--gl);color:var(--gl)}
.pr-btn{font-family:'Tajawal',sans-serif;font-weight:800;font-size:.78rem;padding:8px 3px;border-radius:7px;cursor:pointer;text-align:center;background:var(--bg);border:2px solid var(--bdr);color:var(--mu);line-height:1.4;width:100%}
.pr-btn.on{background:rgba(245,158,11,.13);border-color:var(--gol);color:var(--gol)}
.pt-btn{font-family:'Tajawal',sans-serif;font-weight:800;font-size:.82rem;padding:9px 6px;border-radius:7px;cursor:pointer;text-align:center;background:var(--bg);border:2px solid var(--bdr);color:var(--mu);width:100%}
.pt-btn.pre{background:rgba(16,185,129,.12);border-color:var(--gl);color:var(--gl)}
.pt-btn.post{background:rgba(239,68,68,.12);border-color:var(--rd);color:#f87171}
.ps-btn{font-family:'Tajawal',sans-serif;font-weight:800;font-size:.76rem;padding:8px 3px;border-radius:7px;cursor:pointer;text-align:center;background:var(--bg);border:2px solid var(--bdr);color:var(--mu);line-height:1.5;width:100%}
.ps-btn.paid{background:rgba(16,185,129,.15);border-color:var(--gl);color:var(--gl)}
.ps-btn.unpaid{background:rgba(239,68,68,.15);border-color:var(--rd);color:#f87171}
.ps-btn.absent{background:rgba(249,115,22,.15);border-color:var(--or);color:var(--or)}
.sub-item{display:flex;align-items:center;justify-content:space-between;padding:9px 12px;border-radius:8px;cursor:pointer;border:2px solid var(--bdr);background:var(--bg);margin-bottom:6px;transition:all .15s}
.sub-item.active{border-color:var(--gol);background:rgba(245,158,11,.08)}
.ac-box{position:absolute;top:100%;right:0;left:0;background:var(--c2);border:1px solid var(--bdr);border-top:none;border-radius:0 0 7px 7px;z-index:50;max-height:120px;overflow-y:auto;display:none}
.ac-box.show{display:block}
.ac-item{padding:7px 10px;font-size:.83rem;cursor:pointer;color:var(--tx)}
.ac-item:hover{background:rgba(255,255,255,.06)}
.ov{display:none;position:fixed;inset:0;background:rgba(0,0,0,.85);z-index:998;align-items:center;justify-content:center;padding:14px}
.ov.open{display:flex}
.mbox{background:var(--card);border:1px solid var(--bdr);border-radius:12px;width:100%;max-width:440px;max-height:92vh;overflow-y:auto}
.mhead{padding:12px 16px;background:var(--c2);display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid var(--bdr);border-radius:12px 12px 0 0}
.mbody{padding:16px}
.rcp-box{background:#fff;color:#111;max-width:370px;width:100%;border-radius:6px;overflow:hidden;font-family:'Tajawal',sans-serif}
.rr{display:flex;justify-content:space-between;padding:4px 0;border-bottom:1px dashed #e0ddd8;font-size:.8rem;gap:8px}
#toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(8px);background:var(--c2);border:1px solid var(--bdr);color:var(--tx);padding:9px 22px;border-radius:22px;font-size:.83rem;font-weight:600;z-index:9999;white-space:nowrap;opacity:0;transition:all .25s;pointer-events:none;box-shadow:0 8px 32px rgba(0,0,0,.4)}
#toast.show{opacity:1;transform:translateX(-50%) translateY(0)}
.login-wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:20px}
.sgrid{display:grid;gap:10px;margin-bottom:12px}
@media print{body *{visibility:hidden}.rcp-box,.rcp-box *{visibility:visible}.rcp-box{position:fixed;inset:0;margin:auto}}
@media(max-width:768px){.mgrid{grid-template-columns:1fr!important}}
</style>
</head>
<body>

<!-- LOGIN -->

<div id="login-view" class="login-wrap">
  <div style="width:100%;max-width:380px">
    <div style="text-align:center;margin-bottom:28px">
      <div style="font-size:3rem">🧹</div>
      <div style="font-size:1.4rem;font-weight:900;color:var(--gol);margin-top:6px" id="login-title">خدمة التنظيف الأهلية</div>
      <div style="font-size:.82rem;color:var(--mu);margin-top:4px">نظام الإدارة المتكامل</div>
    </div>
    <div class="card" style="padding:24px">
      <div style="font-size:1rem;font-weight:800;text-align:center;margin-bottom:18px">تسجيل الدخول</div>
      <div class="fld"><label>اسم المستخدم</label><input id="l-u" placeholder="username" onkeydown="if(event.key==='Enter')doLogin()"></div>
      <div class="fld"><label>كلمة المرور</label><input id="l-p" type="password" placeholder="••••••••" onkeydown="if(event.key==='Enter')doLogin()"></div>
      <div id="l-err" style="display:none;background:rgba(239,68,68,.1);border:1px solid rgba(239,68,68,.3);border-radius:6px;padding:8px 12px;margin-bottom:12px;font-size:.8rem;color:#f87171;text-align:center"></div>
      <button class="btn btn-green btn-full" style="padding:11px;font-size:.95rem" onclick="doLogin()">🔐 دخول</button>
    </div>
    <div class="card" style="font-size:.75rem;color:var(--mu)">
      <div style="font-weight:700;color:var(--tx);margin-bottom:6px">بيانات تجريبية:</div>
      <div>👑 مدير: <b style="color:var(--gol)">admin</b> / <b style="color:var(--gol)">admin123</b></div>
      <div>💰 مستحصل: <b style="color:var(--gl)">collector</b> / <b style="color:var(--gl)">col123</b></div>
    </div>
  </div>
</div>

<!-- APP -->

<div id="app-view" style="display:none">
  <div class="topbar">
    <div style="display:flex;align-items:center;gap:10px">
      <div style="font-size:.95rem;font-weight:900;color:var(--gol)" id="app-logo">🧹</div>
      <span class="badge" id="user-badge"></span>
    </div>
    <div style="display:flex;gap:8px;align-items:center">
      <span style="font-size:.7rem;color:var(--mu)" id="app-dt"></span>
      <button class="btn btn-ghost" style="padding:4px 10px;font-size:.75rem" onclick="doLogout()">🚪 خروج</button>
    </div>
  </div>
  <div class="tabs" id="tabs-bar"></div>
  <div id="pages-wrap"></div>
</div>

<!-- RECEIPT MODAL -->

<div class="ov" id="ov-rcp" onclick="if(event.target===this)closeRcp()">
  <div class="rcp-box" id="rcp-content"></div>
</div>

<!-- LOC MODAL -->

<div class="ov" id="ov-loc" onclick="if(event.target===this)closeLoc()">
  <div class="mbox">
    <div class="mhead"><span style="font-weight:800;color:var(--gol)">📍 تحديد الموقع</span><button class="btn btn-ghost" style="padding:3px 9px;font-size:.8rem" onclick="closeLoc()">✖</button></div>
    <div class="mbody">
      <div style="background:rgba(16,185,129,.08);border:1px solid rgba(16,185,129,.25);border-radius:8px;padding:12px;margin-bottom:12px;text-align:center">
        <button class="btn btn-green btn-full" style="padding:11px" onclick="tryGPS()">📍 تحديد موقعي (GPS)</button>
        <div id="gps-msg" style="font-size:.78rem;margin-top:8px;color:var(--mu)"></div>
      </div>
      <button class="btn btn-blue btn-full" style="margin-bottom:12px" onclick="window.open('https://maps.google.com','_blank')">🗺️ فتح Google Maps — انسخ الإحداثيات</button>
      <div class="fld"><label>الصق الإحداثيات</label><input id="lc-paste" placeholder="33.315, 44.366" oninput="parsePaste()"></div>
      <div class="g2">
        <div class="fld"><label>خط العرض</label><input id="lc-lat" type="number" step="any" oninput="showLocPrev()"></div>
        <div class="fld"><label>خط الطول</label><input id="lc-lng" type="number" step="any" oninput="showLocPrev()"></div>
      </div>
      <div id="lc-prev" style="display:none;background:rgba(16,185,129,.08);border:1px solid rgba(16,185,129,.25);border-radius:6px;padding:8px;margin-bottom:10px;font-size:.8rem;color:var(--gl);text-align:center"></div>
      <button class="btn btn-green btn-full" onclick="confirmLoc()">✅ تأكيد الموقع</button>
    </div>
  </div>
</div>

<div id="toast"></div>

<script>
// ═══════════════════════ DATA ═══════════════════════
const K={subs:'cl5_subs',col:'cl5_col',exp:'cl5_exp',frz:'cl5_frz',stf:'cl5_stf',areas:'cl5_areas',cfg:'cl5_cfg',users:'cl5_users'};
const MN=['يناير','فبراير','مارس','أبريل','مايو','يونيو','يوليو','أغسطس','سبتمبر','أكتوبر','نوفمبر','ديسمبر'];
const PSL={paid:'دفع ✅',unpaid:'لم يدفع ❌',absent:'غير موجود 🚫'};
const PRICES=[5000,10000,15000,20000];
const ROLES_S=['سائق','عامل','مستحصل','مشرف','أخرى'];
const EXP_T=['راتب','وقود','صيانة','مستلزمات','إيجار','أخرى'];

function ls(k,d){try{const v=localStorage.getItem(k);return v?JSON.parse(v):d;}catch{return d;}}
function lset(k,v){try{localStorage.setItem(k,JSON.stringify(v));}catch{}}

let subs=ls(K.subs,[]),col=ls(K.col,[]),exp=ls(K.exp,[]),frz=ls(K.frz,[]),stf=ls(K.stf,[]);
let areas=ls(K.areas,['المنطقة الأولى','المنطقة الثانية','المنطقة الثالثة']);
let cfg=ls(K.cfg,{name:'خدمة التنظيف الأهلية',phone:'07773856015',extra:'المراسلة واتساب'});
let users=ls(K.users,[
  {id:1,username:'admin',password:'admin123',role:'manager',name:'المدير',active:true},
  {id:2,username:'collector',password:'col123',role:'collector',name:'المستحصل',active:true}
]);
let CU=null,curTab=0,locCB=null;

// Form state
const FS={
  col:{area:'',subId:null,price:10000,pt:'pre',ps:'paid',months:[],needed:'',date:td()},
  stf:{eid:null,lastId:null}
};

// ═══════════════════════ UTILS ═══════════════════════
function td(){return new Date().toISOString().slice(0,10);}
function esc(s){return String(s==null?'':s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}
function fmt(n){return(n||0).toLocaleString('ar-IQ');}
function toast(m){const t=document.getElementById('toast');t.textContent=m;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2600);}
function genId(){return new Date().getFullYear()+'-'+String(subs.length+1).padStart(3,'0');}
function badge(cls,txt){return`<span class="badge ${cls}">${esc(txt)}</span>`;}
function psBdg(ps){return badge({paid:'b-paid',unpaid:'b-unpaid',absent:'b-absent'}[ps]||'b-gold',PSL[ps]||'—');}
function ptBdg(pt){return pt==='pre'?badge('b-green','مقدم ⬆️'):badge('b-red','مؤخر ⬇️');}
function sbox(n,l,c='var(--tx)'){return`<div class="sbox"><div class="n" style="color:${c}">${esc(String(n))}</div><div class="l">${esc(l)}</div></div>`;}
function pills(arr){return(arr||[]).map(m=>`<span style="background:rgba(16,185,129,.12);color:var(--gl);border:1px solid rgba(16,185,129,.3);border-radius:3px;padding:1px 3px;font-size:.6rem;font-weight:700">${esc(m)}</span>`).join('');}
function tbl_wrap(html){return`<div style="overflow-x:auto">${html}</div>`;}

// ═══════════════════════ AUTH ═══════════════════════
function doLogin(){
  const u=document.getElementById('l-u').value.trim();
  const p=document.getElementById('l-p').value;
  const user=users.find(x=>x.username===u&&x.password===p&&x.active);
  if(!user){const e=document.getElementById('l-err');e.textContent='اسم المستخدم أو كلمة المرور غير صحيحة';e.style.display='block';return;}
  CU=user;
  document.getElementById('login-view').style.display='none';
  document.getElementById('app-view').style.display='block';
  document.getElementById('app-logo').textContent='🧹 '+cfg.name;
  document.getElementById('app-dt').textContent=new Date().toLocaleDateString('ar-IQ');
  const ub=document.getElementById('user-badge');
  ub.textContent=(CU.role==='manager'?'👑 مدير':'💰 مستحصل')+' — '+CU.name;
  ub.className='badge '+(CU.role==='manager'?'b-purple':'b-green');
  buildApp();
}
function doLogout(){CU=null;document.getElementById('login-view').style.display='flex';document.getElementById('app-view').style.display='none';document.getElementById('l-u').value='';document.getElementById('l-p').value='';}

// ═══════════════════════ TABS ═══════════════════════
function buildApp(){
  const isMgr=CU.role==='manager';
  const tabs=isMgr?['📊 لوحة التحكم','👤 المشتركين','💰 الجباية','📈 التقارير','💸 المصاريف','❄️ متعلق/ملغي','👷 الكادر','⚙️ إعدادات']:['👤 المشتركين','💰 الجباية','💸 مصاريفي'];
  document.getElementById('tabs-bar').innerHTML=tabs.map((t,i)=>`<button class="tab${i===0?' on':''}" onclick="goTab(${i})">${esc(t)}</button>`).join('');
  document.getElementById('pages-wrap').innerHTML=tabs.map((_,i)=>`<div class="page${i===0?' on':''}" id="pg${i}"></div>`).join('');
  curTab=0;render();
}
function goTab(i){curTab=i;document.querySelectorAll('.tab').forEach((t,j)=>t.classList.toggle('on',j===i));document.querySelectorAll('.page').forEach((p,j)=>p.classList.toggle('on',j===i));render();}
function pg(){return document.getElementById('pg'+curTab);}
function render(){
  const isMgr=CU.role==='manager';
  const fns=isMgr?[rDash,rSubs,rCol,rReport,rExp,rFrz,rStf,rSettings]:[rSubs,rCol,rExp];
  if(fns[curTab])fns[curTab]();
}

// ═══════════════════════ MONTH/PRICE/PAY WIDGETS ═══════════════════════
function moGrid(sel,ns){
  return`<div class="g4" style="margin-bottom:6px">`+MN.map((m,i)=>`<button class="mo-btn${sel.includes(m)?' on':''}" onclick="togMo('${ns}','${esc(m)}')">${i+1}<br>${esc(m)}</button>`).join('')+`</div>`;
}
function prGrid(val,ns){
  return`<div class="g4">`+PRICES.map(p=>`<button class="pr-btn${val===p?' on':''}" onclick="setPr('${ns}',${p})">${fmt(p)}<div style="font-size:.58rem;opacity:.65">دينار</div></button>`).join('')+`</div>`;
}
function ptRow(val,ns){
  return`<div class="g2">`+
  `<button class="pt-btn${val==='pre'?' pre':''}" onclick="setPT('${ns}','pre')"><div>⬆️</div>مقدم<div style="font-size:.62rem;opacity:.75">بداية الشهر</div></button>`+
  `<button class="pt-btn${val==='post'?' post':''}" onclick="setPT('${ns}','post')"><div>⬇️</div>مؤخر<div style="font-size:.62rem;opacity:.75">نهاية الشهر</div></button>`+
  `</div>`;
}
function psRow(val,ns){
  return`<div class="g3">`+
  [{v:'paid',l:'دفع',i:'✅'},{v:'unpaid',l:'لم يدفع',i:'❌'},{v:'absent',l:'غير موجود',i:'🚫'}]
  .map(({v,l,i})=>`<button class="ps-btn${val===v?' '+v:''}" onclick="setPS('${ns}','${v}')">${i}<br>${esc(l)}</button>`).join('')+
  `</div>`;
}

function togMo(ns,m){const s=FS[ns];s.months=s.months.includes(m)?s.months.filter(x=>x!==m):[...s.months,m];render();}
function setPr(ns,p){FS[ns].price=p;render();}
function setPT(ns,pt){FS[ns].pt=pt;render();}
function setPS(ns,ps){FS[ns].ps=ps;render();}

// ═══════════════════════ DASHBOARD ═══════════════════════
function rDash(){
  const inc=col.reduce((a,c)=>a+(c.total||0),0);
  const expT=exp.reduce((a,e)=>a+(e.amount||0),0);
  const debt=col.reduce((a,c)=>a+(c.debt||0),0);
  const net=inc-expT;
  const byC={};col.forEach(c=>{const n=c.who||'غير محدد';if(!byC[n])byC[n]={count:0,inc:0};byC[n].count++;byC[n].inc+=c.total||0;});
  const recent=[...col].sort((a,b)=>new Date(b.date||0)-new Date(a.date||0)).slice(0,8);
  pg().innerHTML=`
  <div class="sgrid" style="grid-template-columns:repeat(4,1fr)">
    ${sbox(subs.length,'المشتركين','var(--bl)')}${sbox(fmt(inc)+' د.ع','الوارد الكلي','var(--gol)')}${sbox(fmt(net)+' د.ع','صافي الربح',net>=0?'var(--gl)':'#f87171')}${sbox(fmt(debt)+' د.ع','💸 الديون','#f87171')}
  </div>
  <div class="sgrid" style="grid-template-columns:repeat(4,1fr)">
    ${sbox(col.filter(c=>c.ps==='paid').length,'دفعوا ✅','var(--gl)')}${sbox(col.filter(c=>c.ps==='unpaid').length,'لم يدفعوا','var(--rd)')}${sbox(col.filter(c=>c.ps==='absent').length,'غير موجود','var(--or)')}${sbox(fmt(expT)+' د.ع','المصاريف','#f87171')}
  </div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px">
    <div class="card"><div class="stitle">💰 أداء المستحصلين</div>
      ${Object.keys(byC).length===0?'<div style="text-align:center;padding:20px;color:var(--mu)">لا توجد بيانات</div>':tbl_wrap(`<table><thead><tr><th>المستحصل</th><th>عمليات</th><th>الوارد</th></tr></thead><tbody>${Object.entries(byC).map(([n,d])=>`<tr><td style="font-weight:700">${esc(n)}</td><td style="color:var(--bl)">${d.count}</td><td style="color:var(--gol);font-weight:700">${fmt(d.inc)}</td></tr>`).join('')}</tbody></table>`)}
    </div>
    <div class="card"><div class="stitle">🕐 آخر عمليات الجباية</div>
      ${recent.length===0?'<div style="text-align:center;padding:20px;color:var(--mu)">لا توجد عمليات</div>':tbl_wrap(`<table><thead><tr><th>الاسم</th><th>الحالة</th><th>المبلغ</th><th>المستحصل</th></tr></thead><tbody>${recent.map(c=>`<tr><td style="font-weight:700;font-size:.75rem">${esc(c.name)}</td><td>${psBdg(c.ps)}</td><td style="color:var(--gol);font-weight:700;font-size:.72rem">${c.total?fmt(c.total):'—'}</td><td style="font-size:.7rem;color:#a78bfa">${esc(c.who||'—')}</td></tr>`).join('')}</tbody></table>`)}
    </div>
  </div>`;
}

// ═══════════════════════ SUBS ═══════════════════════
let subsFilter={srch:'',area:''};
function rSubs(){
  const filtered=subs.filter(s=>(s.name.includes(subsFilter.srch)||( s.phone||'').includes(subsFilter.srch)||(s.addr||'').includes(subsFilter.srch))&&(!subsFilter.area||s.area===subsFilter.area));
  const withLoc=subs.filter(s=>s.lat&&s.lng);
  pg().innerHTML=`
  <div style="display:grid;grid-template-columns:350px 1fr;gap:12px;align-items:start" class="mgrid">
    <div class="card">
      <div class="stitle">👤 إضافة مشترك جديد</div>
      <div class="fld"><label>الاسم *</label><input id="sn" placeholder="الاسم الكامل"></div>
      <div class="g2">
        <div class="fld"><label>الهاتف *</label><input id="sp" placeholder="07xxxxxxxxx"></div>
        <div class="fld"><label>رقم الاشتراك</label><input id="sid" placeholder="${esc(genId())}"></div>
      </div>
      <div class="fld">
        <label>المنطقة *</label>
        <select id="sa" onchange="document.getElementById('saddr').value=''" style="margin-bottom:6px">
          <option value="">-- اختر --</option>${areas.map(a=>`<option>${esc(a)}</option>`).join('')}
        </select>
        <div style="display:flex;gap:6px"><input id="s-na" placeholder="منطقة جديدة..." style="flex:1"><button class="btn btn-blue" style="padding:7px 10px" onclick="addAreaFromSubs()">+</button></div>
      </div>
      <div class="fld" style="position:relative">
        <label>العنوان التفصيلي</label>
        <input id="saddr" placeholder="الحي / رقم المنزل" autocomplete="off" oninput="showAddrAC()" onfocus="showAddrAC()" onblur="setTimeout(()=>{const a=document.getElementById('saddr-ac');if(a)a.classList.remove('show')},150)">
        <div class="ac-box" id="saddr-ac"></div>
      </div>
      <div class="fld">
        <label>الموقع الجغرافي</label>
        <div style="display:flex;gap:6px">
          <input id="slat" placeholder="خط العرض" type="number" step="any" style="flex:1">
          <input id="slng" placeholder="خط الطول" type="number" step="any" style="flex:1">
          <button class="btn btn-blue" style="padding:7px 10px" onclick="openLoc('subs')">📍</button>
        </div>
        <div id="sloc-p" style="font-size:.72rem;color:var(--gl);margin-top:4px;display:none"></div>
      </div>
      <div class="fld"><label>تاريخ الاشتراك</label><input id="sdate" type="date" value="${td()}"></div>
      <div class="fld"><label>ملاحظات</label><textarea id="snotes" rows="2" placeholder="..."></textarea></div>

```
  <button class="btn btn-green btn-full" onclick="saveSub()">💾 حفظ المشترك</button>
</div>
<div>
  <div class="sgrid" style="grid-template-columns:repeat(3,1fr)">
    ${sbox(subs.length,'إجمالي المشتركين')}${sbox(areas.length,'المناطق','var(--gol)')}${sbox(withLoc.length,'لهم موقع 📍','var(--gl)')}
  </div>
  ${withLoc.length>0?`<div class="card" style="margin-bottom:10px"><div style="font-size:.78rem;color:var(--mu);margin-bottom:8px">📍 اضغط لفتح الموقع على الخريطة:</div><div style="display:flex;flex-wrap:wrap;gap:6px">${withLoc.map(s=>`<a href="https://maps.google.com?q=${s.lat},${s.lng}" target="_blank" style="background:var(--c2);border:1px solid var(--bdr);color:var(--gl);font-size:.75rem;font-weight:600;padding:4px 10px;border-radius:20px;text-decoration:none">📍 ${esc(s.name)}</a>`).join('')}</div></div>`:''}
  <div style="display:flex;gap:8px;margin-bottom:10px;flex-wrap:wrap">
    <input placeholder="🔍 بحث..." value="${esc(subsFilter.srch)}" oninput="subsFilter.srch=this.value;rSubs()" style="max-width:200px">
    <select onchange="subsFilter.area=this.value;rSubs()" style="max-width:160px">
      <option value="">كل المناطق</option>${areas.map(a=>`<option${subsFilter.area===a?' selected':''}>${esc(a)}</option>`).join('')}
    </select>
  </div>
  ${filtered.length===0?'<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا يوجد مشتركون</div>':tbl_wrap(`<table><thead><tr><th>الاسم</th><th>الهاتف</th><th>المنطقة</th><th>العنوان</th><th>التاريخ</th><th>أضافه</th><th>الموقع</th><th>حذف</th></tr></thead><tbody>${filtered.map(s=>`<tr><td style="font-weight:800">${esc(s.name)}</td><td style="color:var(--mu)">${esc(s.phone||'—')}</td><td>${badge('b-purple',s.area||'—')}</td><td style="color:var(--mu);font-size:.72rem">${esc(s.addr||'—')}</td><td style="color:var(--mu);font-size:.72rem">${esc(s.date||'—')}</td><td style="font-size:.7rem;color:#a78bfa">${esc(s.who||'—')}</td><td>${s.lat&&s.lng?`<a href="https://maps.google.com?q=${s.lat},${s.lng}" target="_blank" class="tbtn tb-map">📍 خريطة</a>`:'—'}</td><td><button class="tbtn tb-dl" onclick="delSub(${s.id})">🗑️</button></td></tr>`).join('')}</tbody></table>`)}
</div>
```

  </div>`;
}
function addAreaFromSubs(){const v=document.getElementById('s-na').value.trim();if(!v||areas.includes(v)){toast('⚠️ اسم غير صالح أو موجود');return;}areas.push(v);lset(K.areas,areas);document.getElementById('s-na').value='';toast('✅ تمت إضافة المنطقة');rSubs();}
function showAddrAC(){
  const area=document.getElementById('sa').value;
  const val=document.getElementById('saddr').value.toLowerCase();
  const list=document.getElementById('saddr-ac');
  if(!area){list.classList.remove('show');return;}
  const seen=new Set();
  const addrs=subs.filter(s=>s.area===area&&s.addr).map(s=>s.addr).filter(a=>{if(seen.has(a))return false;seen.add(a);return !val||a.toLowerCase().includes(val);});
  if(!addrs.length){list.classList.remove('show');return;}
  list.innerHTML=addrs.map(a=>`<div class="ac-item" onmousedown="document.getElementById('saddr').value=this.dataset.v;document.getElementById('saddr-ac').classList.remove('show')" data-v="${esc(a)}">${esc(a)}</div>`).join('');
  list.classList.add('show');
}
function saveSub(){
  const name=(document.getElementById('sn').value||'').trim();
  const phone=(document.getElementById('sp').value||'').trim();
  const area=document.getElementById('sa').value;
  if(!name){toast('⚠️ أدخل الاسم');return;}if(!phone){toast('⚠️ أدخل الهاتف');return;}if(!area){toast('⚠️ اختر المنطقة');return;}
  const sid=(document.getElementById('sid').value||'').trim()||genId();
  const lat=parseFloat(document.getElementById('slat').value)||null;
  const lng=parseFloat(document.getElementById('slng').value)||null;
  subs.push({id:Date.now(),name,phone,area,addr:(document.getElementById('saddr').value||'').trim(),lat,lng,date:document.getElementById('sdate').value,notes:(document.getElementById('snotes').value||'').trim(),status:'active',subid:sid,who:CU?CU.name:'مدير'});
  lset(K.subs,subs);toast('✅ تم حفظ المشترك');rSubs();
}
function delSub(id){if(!confirm('حذف المشترك؟'))return;subs=subs.filter(s=>s.id!==id);lset(K.subs,subs);toast('🗑️ تم الحذف');rSubs();}

// ═══════════════════════ COLLECT ═══════════════════════
let colFilter={srch:’’,area:’’,ps:’’,view:‘list’};
function rCol(){
const f=FS.col;
const uAreas=[…new Set(subs.filter(s=>s.status===‘active’).map(s=>s.area).filter(Boolean))];
const areaSubs=subs.filter(s=>s.status===‘active’&&(!f.area||s.area===f.area));
const activeSub=f.subId?subs.find(s=>s.id===f.subId):null;
const rcv=f.months.length,nd=parseInt(f.needed)||0,dm=f.ps!==‘paid’?(nd>0?nd:rcv):0,debt=dm*f.price,total=rcv*f.price;
const totDebt=col.reduce((a,c)=>a+(c.debt||0),0);
const filtCol=col.filter(c=>(c.name||’’).includes(colFilter.srch)&&(!colFilter.area||c.area===colFilter.area)&&(!colFilter.ps||c.ps===colFilter.ps));

function lastPS(subId){const x=col.filter(c=>c.subId===subId).sort((a,b)=>new Date(b.date)-new Date(a.date))[0];return x?x.ps:null;}

const CTH=`<thead><tr><th>التاريخ</th><th>الاسم</th><th>العنوان</th><th>السعر</th><th>نوع الدفع</th><th>الحالة</th><th>الأشهر</th><th>عدد</th><th>المبلغ</th><th>💸الدين</th><th>المستحصل</th><th>إجراءات</th></tr></thead>`;
function crow(c){return`<tr><td style="color:var(--mu);font-size:.7rem">${esc(c.date||'—')}</td><td style="font-weight:800">${esc(c.name)}</td><td style="color:var(--mu);font-size:.72rem">${esc(c.addr||c.area||'—')}</td><td style="font-weight:700;font-size:.72rem">${fmt(c.price)}</td><td>${ptBdg(c.pt)}</td><td>${psBdg(c.ps)}</td><td><div style="display:flex;flex-wrap:wrap;gap:2px;justify-content:center;max-width:100px;margin:0 auto">${pills(c.months)}</div></td><td style="color:var(--gl);font-weight:700">${c.rcv||0}</td><td style="color:var(--gol);font-weight:700;font-size:.72rem">${c.total?fmt(c.total):'—'}</td><td>${c.debt>0?`<span style="color:#f87171;font-weight:900;font-size:.72rem">💸${fmt(c.debt)}</span>`:'—'}</td><td style="font-size:.7rem;color:#a78bfa">${esc(c.who||'—')}</td><td>${c.ps!=='paid'&&c.debt>0?`<button class="tbtn tb-wa" onclick="sendDWA(${c.id})">💬دين</button>`:''}<button class="tbtn tb-rc" onclick="showRcp(${c.id})">🧾</button><button class="tbtn tb-dl" onclick="delCol(${c.id})">🗑️</button></td></tr>`;}

let tableHTML=’’;
if(colFilter.view===‘area’){
const grp={};filtCol.forEach(c=>{const a=c.area||‘بدون منطقة’;if(!grp[a])grp[a]=[];grp[a].push(c);});
tableHTML=Object.keys(grp).length===0?’<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا توجد سجلات</div>’:Object.entries(grp).map(([area,list])=>{
const inc=list.reduce((a,c)=>a+(c.total||0),0),dbt=list.reduce((a,c)=>a+(c.debt||0),0);
return`<div style="margin-bottom:14px"><div style="background:var(--c2);border:1px solid var(--bdr);border-radius:8px 8px 0 0;padding:8px 12px;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:5px"><span style="font-weight:900;color:var(--gol)">📍 ${esc(area)}</span><div style="display:flex;gap:5px;flex-wrap:wrap">${badge('b-blue','الكل:'+list.length)}${badge('b-green','دفع:'+list.filter(c=>c.ps==='paid').length)}${badge('b-red','لم يدفع:'+list.filter(c=>c.ps==='unpaid').length)}${badge('b-orange','غ.موجود:'+list.filter(c=>c.ps==='absent').length)}${badge('b-gold',fmt(inc)+' د.ع')}${dbt>0?badge('b-red','💸'+fmt(dbt)):''}</div></div><div style="border:1px solid var(--bdr);border-top:none;border-radius:0 0 8px 8px">${tbl_wrap(`<table>${CTH}<tbody>${list.map(crow).join(’’)}</tbody></table>`)}</div></div>`;
}).join(’’);
} else {
tableHTML=filtCol.length===0?’<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا توجد سجلات</div>’:tbl_wrap(`<table>${CTH}<tbody>${filtCol.map(crow).join('')}</tbody></table>`);
}

pg().innerHTML=`

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;align-items:start" class="mgrid">
    <div>
      <div class="card">
        <div class="stitle">📍 اختر الفرع</div>
        <select onchange="FS.col.area=this.value;FS.col.subId=null;rCol()" style="border-color:${!f.area?'var(--or)':'var(--bdr)'};margin-bottom:8px">
          <option value="">-- اختر الفرع أولاً --</option>${uAreas.map(a=>`<option${f.area===a?' selected':''}>${esc(a)}</option>`).join('')}
        </select>
        ${f.area?`<div style="font-size:.78rem;color:var(--mu)">${areaSubs.length} مشترك — اضغط على الاسم لتسجيل جبايته</div>`:''}
      </div>
      ${f.area?`<div class="card"><div class="stitle">👥 مشتركو ${esc(f.area)}</div>
        ${areaSubs.length===0?'<div style="text-align:center;padding:20px;color:var(--mu)">لا يوجد مشتركون</div>':areaSubs.map(s=>{
          const lst=lastPS(s.id);const isA=activeSub&&activeSub.id===s.id;
          return`<div class="sub-item${isA?' active':''}" onclick="selColSub(${s.id})"><div><div style="font-weight:800;color:${isA?'var(--gol)':'var(--tx)'};font-size:.88rem">${esc(s.name)}</div><div style="font-size:.72rem;color:var(--mu);margin-top:2px">🏠 ${esc(s.addr||'—')} | 📞 ${esc(s.phone||'—')}</div></div><div style="display:flex;flex-direction:column;align-items:flex-end;gap:3px">${lst?psBdg(lst):badge('b-blue','🆕 جديد')}${isA?'<span style="font-size:.67rem;color:var(--gol);font-weight:700">◀ محدد</span>':''}</div></div>`;
        }).join('')}
      </div>`:''}
    </div>
    <div>
      <div class="card">
        <div class="stitle">💰 تسجيل الجباية</div>
        ${!activeSub?'<div style="text-align:center;padding:30px;color:var(--mu);font-size:.9rem">← اختر الفرع ثم اضغط على مشترك</div>':`
          <div style="background:rgba(59,130,246,.08);border:1px solid rgba(59,130,246,.25);border-radius:8px;padding:8px 12px;margin-bottom:12px;font-size:.82rem"><b style="color:var(--gol);font-size:.95rem">${esc(activeSub.name)}</b><div style="margin-top:3px;color:var(--mu);font-size:.75rem">🏠 ${esc(activeSub.addr||'—')} | 📍 ${esc(activeSub.area||'—')} | 📞 ${esc(activeSub.phone||'—')}</div></div>
          <div style="font-size:.72rem;color:var(--mu);font-weight:800;margin-bottom:5px">💰 سعر الشهر</div>
          <div style="margin-bottom:10px">${prGrid(f.price,'col')}</div>
          <div style="font-size:.72rem;color:var(--mu);font-weight:800;margin-bottom:5px">🗓️ نوع الدفع</div>
          <div style="margin-bottom:10px">${ptRow(f.pt,'col')}</div>
          <div style="font-size:.72rem;color:var(--mu);font-weight:800;margin-bottom:5px">📌 حالة الدفع</div>
          <div style="margin-bottom:10px">${psRow(f.ps,'col')}</div>
          <div style="font-size:.72rem;color:var(--mu);font-weight:800;margin-bottom:5px">📅 الأشهر المستلمة</div>
          ${moGrid(f.months,'col')}
          ${f.months.length>0?`<div style="font-size:.7rem;color:var(--gl);margin-bottom:8px;text-align:center">✅ ${f.months.join(' — ')}</div>`:''}
          <div style="background:var(--bg);border:1px solid var(--bdr);border-radius:7px;padding:9px 11px;margin-bottom:9px">
            ${[['الأشهر المستلمة',rcv+' شهر','var(--gl)'],['المبلغ المستلم',total>0?fmt(total)+' د.ع':'—','var(--gol)'],['نوع الدفع',f.pt==='pre'?'مقدم ⬆️':'مؤخر ⬇️','var(--bl)'],['حالة الدفع',PSL[f.ps],f.ps==='paid'?'var(--gl)':f.ps==='unpaid'?'var(--rd)':'var(--or)'],...(f.ps!=='paid'&&dm>0?[['💸 الدين ('+dm+' شهر)',fmt(debt)+' د.ع','#f87171']]:[])].map(([l,v,c])=>`<div style="display:flex;justify-content:space-between;padding:4px 0;border-bottom:1px solid var(--bdr);font-size:.81rem"><span style="color:var(--mu)">${esc(l)}</span><span style="font-weight:700;color:${c}">${esc(v)}</span></div>`).join('')}
          </div>
          <div class="g2" style="margin-bottom:8px">
            <div class="fld"><label>الأشهر المطلوبة</label><input type="number" min="1" max="36" placeholder="12" value="${esc(f.needed)}" oninput="FS.col.needed=this.value;rCol()"></div>
            <div class="fld"><label>تاريخ التسجيل</label><input type="date" value="${esc(f.date)}" onchange="FS.col.date=this.value"></div>
          </div>
          <button class="btn btn-green btn-full" style="margin-bottom:7px" onclick="saveCol()">💾 حفظ جباية ${esc(activeSub.name)}</button>
          <div class="g2" style="gap:7px">
            <button class="btn btn-wa btn-full" onclick="sendDWAForm()">💬 رسالة الدين</button>
            <button class="btn btn-gold btn-full" onclick="showRcpForm()">🧾 وصل</button>
          </div>
        `}
      </div>
      <div class="sgrid" style="grid-template-columns:repeat(5,1fr)">
        ${sbox(col.length,'إجمالي')}${sbox(col.filter(c=>c.ps==='paid').length,'دفعوا ✅','var(--gl)')}${sbox(col.filter(c=>c.ps==='unpaid').length,'لم يدفعوا','var(--rd)')}${sbox(col.filter(c=>c.ps==='absent').length,'غير موجود','var(--or)')}${sbox(fmt(totDebt),'💸 الديون','#f87171')}
      </div>
    </div>
    <div style="grid-column:1/-1">
      <div style="display:flex;gap:8px;margin-bottom:10px;flex-wrap:wrap;align-items:center">
        <span style="font-weight:800;color:var(--gol);font-size:.9rem">📂 سجل الجباية</span>
        <input placeholder="🔍 بحث..." value="${esc(colFilter.srch)}" oninput="colFilter.srch=this.value;rCol()" style="max-width:180px">
        <select onchange="colFilter.area=this.value;rCol()" style="max-width:150px"><option value="">كل الفروع</option>${uAreas.map(a=>`<option${colFilter.area===a?' selected':''}>${esc(a)}</option>`).join('')}</select>
        <select onchange="colFilter.ps=this.value;rCol()" style="max-width:150px"><option value="">كل الحالات</option><option value="paid"${colFilter.ps==='paid'?' selected':''}>دفع ✅</option><option value="unpaid"${colFilter.ps==='unpaid'?' selected':''}>لم يدفع ❌</option><option value="absent"${colFilter.ps==='absent'?' selected':''}>غير موجود 🚫</option></select>
        <div style="margin-right:auto;display:flex;gap:4px">
          <button class="btn ${colFilter.view==='list'?'btn-blue':'btn-ghost'}" style="padding:5px 9px;font-size:.75rem" onclick="colFilter.view='list';rCol()">📋 قائمة</button>
          <button class="btn ${colFilter.view==='area'?'btn-blue':'btn-ghost'}" style="padding:5px 9px;font-size:.75rem" onclick="colFilter.view='area';rCol()">🗺️ فرع</button>
        </div>
      </div>
      ${tableHTML}
    </div>
  </div>`;
}

function selColSub(id){
FS.col.subId=id;
const last=col.filter(c=>c.subId===id).sort((a,b)=>new Date(b.date)-new Date(a.date))[0];
if(last){FS.col.price=last.price||10000;FS.col.pt=last.pt||‘pre’;FS.col.ps=last.ps||‘paid’;FS.col.months=last.months||[];FS.col.needed=last.needed||’’;}
else{FS.col.months=[];FS.col.needed=’’;}
rCol();
}
function saveCol(){
const s=subs.find(x=>x.id===FS.col.subId);if(!s){toast(‘⚠️ اختر مشتركاً’);return;}
const f=FS.col;const rcv=f.months.length,nd=parseInt(f.needed)||0,dm=f.ps!==‘paid’?(nd>0?nd:rcv):0;
col.push({id:Date.now(),subId:s.id,name:s.name,phone:s.phone,area:s.area,addr:s.addr,subid:s.subid,price:f.price,pt:f.pt,ps:f.ps,needed:nd,rcv,remaining:nd>0?Math.max(0,nd-rcv):0,total:rcv*f.price,months:[…f.months],debtMonths:dm,debt:dm*f.price,date:f.date,who:CU?CU.name:‘مدير’});
lset(K.col,col);toast(‘✅ تم حفظ جباية ‘+s.name);
FS.col.subId=null;FS.col.months=[];FS.col.needed=’’;FS.col.ps=‘paid’;rCol();
}
function delCol(id){if(!confirm(‘حذف السجل؟’))return;col=col.filter(c=>c.id!==id);lset(K.col,col);toast(‘🗑️ تم’);rCol();}

// ═══════════════════════ RECEIPT ═══════════════════════
function buildRcpHTML(d){
const isPaid=d.ps===‘paid’;
const pt=d.pt===‘pre’?‘مقدم ⬆️’:‘مؤخر ⬇️’;
const dm=d.debtMonths||(d.needed>0?d.needed:d.rcv)||0;
return`<div style="background:#111;padding:13px 16px;text-align:center"><div style="color:#d4a017;font-size:1rem;font-weight:900">${esc(cfg.name)}</div><div style="color:#888;font-size:.68rem;margin-top:2px">${isPaid?‘وصل استلام اشتراك’:‘إشعار دين’}</div></div>

  <div style="padding:11px 14px">
    ${[['اسم المشترك',d.name],['رقم الاشتراك',d.subid||'—'],['المنطقة',d.area||'—'],['العنوان',d.addr||'—'],['التاريخ',d.date||'—'],['سعر الشهر',fmt(d.price)+' د.ع'],['نوع الدفع',pt],['حالة الدفع',PSL[d.ps]||'—']].map(([l,v])=>`<div class="rr"><span style="color:#777">${esc(l)}</span><span style="font-weight:700">${esc(v)}</span></div>`).join('')}
    ${isPaid?`<div class="rr" style="align-items:flex-start"><span style="color:#777">الأشهر المستلمة</span><div style="display:flex;flex-wrap:wrap;gap:3px;justify-content:flex-end">${(d.months||[]).map(m=>`<span style="background:#e8f5e9;color:#1a7a30;border:1px solid #a5d6a7;border-radius:3px;padding:1px 5px;font-size:.67rem;font-weight:700">${esc(m)}</span>`).join('')||'—'}</div></div>
    <div style="display:flex;justify-content:space-between;padding:6px 0;border-top:2px solid #111;margin-top:5px;font-size:.82rem"><span style="font-weight:900">إجمالي المبلغ</span><span style="color:#b8860b;font-weight:900;font-size:1rem">${fmt(d.total)} د.ع</span></div>`
    :`<div style="background:#fff5f5;border:1px solid #f5c6cb;border-radius:6px;padding:10px;margin-top:8px"><div style="display:flex;justify-content:space-between;margin-bottom:5px;font-size:.8rem"><span style="color:#c0392b;font-weight:700">⚠️ ${esc(PSL[d.ps])}</span><span style="font-weight:700">${dm} شهر</span></div>${(d.months||[]).length>0?`<div style="display:flex;flex-wrap:wrap;gap:3px;margin-bottom:5px">${d.months.map(m=>`<span style="background:#fde8e8;color:#c0392b;border:1px solid #f5c6cb;border-radius:3px;padding:1px 5px;font-size:.67rem;font-weight:700">${esc(m)}</span>`).join('')}</div>`:''}<div style="display:flex;justify-content:space-between;padding-top:6px;border-top:2px dashed #e74c3c;font-size:.82rem"><span style="color:#c0392b;font-weight:900">💸 إجمالي الدين</span><span style="color:#cc0000;font-weight:900;font-size:1.05rem">${fmt(d.debt)} د.ع</span></div></div>`}
  </div>
  <div style="background:#f5f2ec;padding:8px 14px;text-align:center;border-top:1px solid #e0ddd8;font-size:.7rem;color:#666"><div style="font-weight:700;color:#111;margin-bottom:2px">للاستفسار والشكاوى</div><div>رقم الإدارة: ${esc(cfg.phone)}${cfg.extra?' — '+esc(cfg.extra):''}</div></div>
  <div style="display:grid;grid-template-columns:1fr 1fr;border-top:1px solid #e0ddd8"><button style="font-family:'Tajawal',sans-serif;font-weight:800;font-size:.83rem;padding:10px;border:none;cursor:pointer;background:#f0ede8;color:#333;border-right:1px solid #e0ddd8" onclick="closeRcp()">✖ إغلاق</button><button style="font-family:'Tajawal',sans-serif;font-weight:800;font-size:.83rem;padding:10px;border:none;cursor:pointer;background:#111;color:#d4a017" onclick="window.print()">🖨️ طباعة</button></div>`;
}
function showRcp(id){const d=col.find(c=>c.id===id);if(!d)return;document.getElementById('rcp-content').innerHTML=buildRcpHTML(d);document.getElementById('ov-rcp').classList.add('open');}
function showRcpForm(){
  const s=subs.find(x=>x.id===FS.col.subId);if(!s){toast('⚠️ اختر مشتركاً');return;}
  const f=FS.col;const rcv=f.months.length,nd=parseInt(f.needed)||0,dm=f.ps!=='paid'?(nd>0?nd:rcv):0;
  const d={name:s.name,subid:s.subid,area:s.area,addr:s.addr,date:f.date,price:f.price,pt:f.pt,ps:f.ps,rcv,months:[...f.months],debtMonths:dm,debt:dm*f.price,total:rcv*f.price};
  document.getElementById('rcp-content').innerHTML=buildRcpHTML(d);document.getElementById('ov-rcp').classList.add('open');
}
function closeRcp(){document.getElementById('ov-rcp').classList.remove('open');}

// ═══════════════════════ WHATSAPP ═══════════════════════
function wa(phone,msg){let p=(phone||’’).replace(/\D/g,’’);if(p.startsWith(‘0’))p=‘964’+p.slice(1);if(!p){toast(‘⚠️ لا يوجد رقم هاتف’);return;}window.open(‘https://wa.me/’+p+’?text=’+encodeURIComponent(msg),’_blank’);}
function debtMsg(d){
const dm=d.debtMonths||(d.needed>0?d.needed:d.rcv)||0;
return`*${cfg.name}* 🧹\n━━━━━━━━━━━━━━━━\n👤 *الاسم :* ${d.name}\n📍 *المنطقة :* ${d.area||'—'}\n🏠 *العنوان :* ${d.addr||'—'}\n📌 *الحالة :* ${PSL[d.ps]||'—'}\n━━━━━━━━━━━━━━━━\n💸 *لديك مبلغ دين :*\n• الأشهر المطلوبة: *${dm} شهر*\n${(d.months||[]).length?'• الأشهر: '+(d.months.join(' — '))+'\n':''}• سعر الشهر: *${fmt(d.price)} دينار*\n• *إجمالي الدين: ${fmt(d.debt)} دينار* 💰\n━━━━━━━━━━━━━━━━\nنرجو منك المبادرة بالسداد\nللاستفسار: ${cfg.phone}\nشكراً 🌿`;
}
function sendDWA(id){const d=col.find(c=>c.id===id);if(!d||d.ps===‘paid’){toast(‘هذا المشترك دفع’);return;}wa(d.phone,debtMsg(d));}
function sendDWAForm(){
const s=subs.find(x=>x.id===FS.col.subId);if(!s){toast(‘⚠️ اختر مشتركاً’);return;}
const f=FS.col;if(f.ps===‘paid’){toast(‘هذا المشترك دفع’);return;}
const rcv=f.months.length,nd=parseInt(f.needed)||0,dm=f.ps!==‘paid’?(nd>0?nd:rcv):0;
const d={name:s.name,phone:s.phone,area:s.area,addr:s.addr,price:f.price,ps:f.ps,rcv,months:[…f.months],needed:nd,debtMonths:dm,debt:dm*f.price};
wa(s.phone,debtMsg(d));
}

// ═══════════════════════ LOCATION ═══════════════════════
function openLoc(ns){locCB=ns;document.getElementById(‘ov-loc’).classList.add(‘open’);[‘lc-lat’,‘lc-lng’,‘lc-paste’].forEach(id=>{const el=document.getElementById(id);if(el)el.value=’’;});document.getElementById(‘gps-msg’).textContent=’’;document.getElementById(‘lc-prev’).style.display=‘none’;}
function closeLoc(){document.getElementById(‘ov-loc’).classList.remove(‘open’);locCB=null;}
function parsePaste(){const v=document.getElementById(‘lc-paste’).value;const m=v.match(/([\d.]+)[,\s]+([\d.]+)/);if(m){document.getElementById(‘lc-lat’).value=m[1];document.getElementById(‘lc-lng’).value=m[2];showLocPrev();}}
function showLocPrev(){const la=document.getElementById(‘lc-lat’).value,ln=document.getElementById(‘lc-lng’).value;const p=document.getElementById(‘lc-prev’);if(la&&ln){p.style.display=‘block’;p.innerHTML=`✅ ${la} , ${ln} — <a href="https://maps.google.com?q=${la},${ln}" target="_blank" style="color:var(--bl)">معاينة ↗</a>`;}else p.style.display=‘none’;}
function tryGPS(){
const msg=document.getElementById(‘gps-msg’);
if(!navigator.geolocation){msg.textContent=‘⚠️ GPS غير مدعوم’;return;}
msg.style.color=‘var(–mu)’;msg.textContent=‘⏳ جاري التحديد…’;
navigator.geolocation.getCurrentPosition(
p=>{const la=p.coords.latitude.toFixed(6),ln=p.coords.longitude.toFixed(6);document.getElementById(‘lc-lat’).value=la;document.getElementById(‘lc-lng’).value=ln;msg.style.color=‘var(–gl)’;msg.textContent=’✅ تم: ‘+la+’, ’+ln;showLocPrev();},
e=>{msg.style.color=‘var(–or)’;msg.textContent={1:‘⚠️ رُفض الإذن — اسمح من إعدادات المتصفح’,2:‘⚠️ تعذر التحديد’,3:‘⚠️ انتهت المهلة’}[e.code]||‘⚠️ خطأ’;},
{enableHighAccuracy:true,timeout:15000,maximumAge:0}
);
}
function confirmLoc(){
const la=parseFloat(document.getElementById(‘lc-lat’).value);
const ln=parseFloat(document.getElementById(‘lc-lng’).value);
if(!la||!ln){toast(‘⚠️ أدخل الإحداثيات’);return;}
if(locCB===‘subs’){
document.getElementById(‘slat’).value=la.toFixed(6);document.getElementById(‘slng’).value=ln.toFixed(6);
const p=document.getElementById(‘sloc-p’);p.style.display=‘block’;p.innerHTML=`✅ ${la.toFixed(6)}, ${ln.toFixed(6)} — <a href="https://maps.google.com?q=${la},${ln}" target="_blank" style="color:var(--bl)">معاينة ↗</a>`;
}
closeLoc();toast(‘✅ تم تحديد الموقع’);
}

// ═══════════════════════ REPORT ═══════════════════════
let rptF={from:’’,to:’’,res:null};
function rReport(){
const now=new Date();const y=now.getFullYear();const m=String(now.getMonth()+1).padStart(2,‘0’);
if(!rptF.from)rptF.from=`${y}-${m}-01`;
if(!rptF.to)rptF.to=`${y}-${m}-${new Date(y,now.getMonth()+1,0).getDate()}`;
const res=rptF.res;
pg().innerHTML=`

  <div class="card"><div class="stitle">📊 تقرير الاستحصال</div>
    <div class="g3" style="margin-bottom:12px">
      <div class="fld"><label>من تاريخ</label><input type="date" value="${esc(rptF.from)}" onchange="rptF.from=this.value"></div>
      <div class="fld"><label>إلى تاريخ</label><input type="date" value="${esc(rptF.to)}" onchange="rptF.to=this.value"></div>
      <div class="fld" style="display:flex;align-items:flex-end"><button class="btn btn-blue btn-full" onclick="genRpt()">🔍 عرض التقرير</button></div>
    </div>
  </div>
  ${res?`
  <div class="sgrid" style="grid-template-columns:repeat(4,1fr)">
    ${sbox(fmt(res.inc)+' د.ع','الوارد الكلي','var(--gol)')}${sbox(fmt(res.expT)+' د.ع','المصاريف','#f87171')}${sbox(fmt(res.net)+' د.ع','صافي الربح',res.net>=0?'var(--gl)':'#f87171')}${sbox(fmt(res.debt)+' د.ع','الديون','#f87171')}
  </div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px">
    <div class="card"><div class="stitle">📍 حسب المنطقة</div>${tbl_wrap(`<table><thead><tr><th>المنطقة</th><th>العدد</th><th>دفعوا</th><th>لم يدفعوا</th><th>الوارد</th><th>الديون</th></tr></thead><tbody>${Object.entries(res.byArea).map(([a,d])=>`<tr><td style="font-weight:800;color:var(--gol)">${esc(a)}</td><td>${d.list.length}</td><td style="color:var(--gl)">${d.list.filter(c=>c.ps==='paid').length}</td><td style="color:var(--rd)">${d.list.filter(c=>c.ps!=='paid').length}</td><td style="color:var(--gol);font-weight:700">${fmt(d.inc)}</td><td style="color:#f87171;font-weight:700">${d.debt>0?fmt(d.debt):'—'}</td></tr>`).join('')||'<tr><td colspan="6" style="text-align:center;color:var(--mu)">لا توجد بيانات</td></tr>'}</tbody></table>`)}</div>
    <div class="card"><div class="stitle">💰 حسب المستحصل</div>${tbl_wrap(`<table><thead><tr><th>المستحصل</th><th>عمليات</th><th>الوارد</th></tr></thead><tbody>${Object.entries(res.byWho).map(([n,d])=>`<tr><td style="font-weight:800;color:#a78bfa">${esc(n)}</td><td style="color:var(--bl)">${d.count}</td><td style="color:var(--gol);font-weight:700">${fmt(d.inc)}</td></tr>`).join('')||'<tr><td colspan="3" style="text-align:center;color:var(--mu)">لا توجد بيانات</td></tr>'}</tbody></table>`)}</div>
  </div>
  ${res.expL.length>0?`<div class="card"><div class="stitle">💸 المصاريف في هذه الفترة</div>${tbl_wrap(`<table><thead><tr><th>التاريخ</th><th>النوع</th><th>الوصف</th><th>المبلغ</th></tr></thead><tbody>${res.expL.map(e=>`<tr><td style="color:var(--mu)">${esc(e.date)}</td><td>${esc(e.type)}</td><td>${esc(e.desc||'—')}</td><td style="color:#f87171;font-weight:700">${fmt(e.amount)}</td></tr>`).join('')}</tbody></table>`)}</div>`:''}
  `:''}`;
}
function genRpt(){
  const list=col.filter(c=>c.date>=rptF.from&&c.date<=rptF.to);
  const expL=exp.filter(e=>e.date>=rptF.from&&e.date<=rptF.to);
  const inc=list.reduce((a,c)=>a+(c.total||0),0),debt=list.reduce((a,c)=>a+(c.debt||0),0),expT=expL.reduce((a,e)=>a+(e.amount||0),0);
  const byArea={},byWho={};
  list.forEach(c=>{const a=c.area||'بدون منطقة';if(!byArea[a])byArea[a]={list:[],inc:0,debt:0};byArea[a].list.push(c);byArea[a].inc+=c.total||0;byArea[a].debt+=c.debt||0;const n=c.who||'غير محدد';if(!byWho[n])byWho[n]={count:0,inc:0};byWho[n].count++;byWho[n].inc+=c.total||0;});
  rptF.res={list,expL,inc,debt,expT,net:inc-expT,byArea,byWho};rReport();
}

// ═══════════════════════ EXPENSE ═══════════════════════
let expF={srch:’’,type:’’,from:’’,to:’’};
function rExp(){
const EC={‘راتب’:‘b-blue’,‘وقود’:‘b-orange’,‘صيانة’:‘b-red’,‘مستلزمات’:‘b-purple’,‘إيجار’:‘b-gold’,‘أخرى’:‘b-green’};
const filtered=exp.filter(e=>((e.desc||’’).includes(expF.srch)||(e.type||’’).includes(expF.srch))&&(!expF.type||e.type===expF.type)&&(!expF.from||e.date>=expF.from)&&(!expF.to||e.date<=expF.to));
const allExp=exp.reduce((a,e)=>a+(e.amount||0),0),totInc=col.reduce((a,c)=>a+(c.total||0),0),net=totInc-allExp;
pg().innerHTML=`

  <div style="display:grid;grid-template-columns:300px 1fr;gap:12px;align-items:start" class="mgrid">
    <div class="card"><div class="stitle">💸 إضافة مصروف</div>
      <div class="fld"><label>النوع</label><select id="ex-t">${EXP_T.map(t=>`<option>${esc(t)}</option>`).join('')}</select></div>
      <div class="fld"><label>الوصف</label><input id="ex-d" placeholder="وصف المصروف"></div>
      <div class="g2">
        <div class="fld"><label>المبلغ (دينار)</label><input id="ex-a" type="number" placeholder="0"></div>
        <div class="fld"><label>التاريخ</label><input id="ex-dt" type="date" value="${td()}"></div>
      </div>
      <div class="fld"><label>ملاحظات</label><textarea id="ex-n" rows="2" placeholder="..."></textarea></div>
      <button class="btn btn-red btn-full" onclick="saveExp()">💾 حفظ المصروف</button>
    </div>
    <div>
      <div class="sgrid" style="grid-template-columns:repeat(4,1fr)">
        ${sbox(exp.length,'إجمالي العمليات')}${sbox(fmt(allExp)+' د.ع','المصاريف الكلية','#f87171')}${sbox(fmt(totInc)+' د.ع','الوارد الكلي','var(--gl)')}${sbox(fmt(net)+' د.ع','صافي الربح',net>=0?'var(--gl)':'#f87171')}
      </div>
      <div style="display:flex;gap:8px;margin-bottom:10px;flex-wrap:wrap">
        <input placeholder="🔍 بحث..." value="${esc(expF.srch)}" oninput="expF.srch=this.value;rExp()" style="max-width:180px">
        <select onchange="expF.type=this.value;rExp()" style="max-width:130px"><option value="">كل الأنواع</option>${EXP_T.map(t=>`<option${expF.type===t?' selected':''}>${esc(t)}</option>`).join('')}</select>
        <input type="date" value="${esc(expF.from)}" onchange="expF.from=this.value;rExp()" style="max-width:140px">
        <input type="date" value="${esc(expF.to)}" onchange="expF.to=this.value;rExp()" style="max-width:140px">
      </div>
      ${filtered.length===0?'<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا توجد مصاريف</div>':tbl_wrap(`<table><thead><tr><th>التاريخ</th><th>النوع</th><th>الوصف</th><th>المبلغ</th><th>أضافه</th><th>ملاحظات</th><th>حذف</th></tr></thead><tbody>${filtered.map(e=>`<tr><td style="color:var(--mu)">${esc(e.date)}</td><td>${badge(EC[e.type]||'b-gold',e.type)}</td><td>${esc(e.desc||'—')}</td><td style="color:#f87171;font-weight:700">${fmt(e.amount)}</td><td style="font-size:.7rem;color:#a78bfa">${esc(e.who||'—')}</td><td style="color:var(--mu);font-size:.72rem">${esc(e.notes||'—')}</td><td><button class="tbtn tb-dl" onclick="delExp(${e.id})">🗑️</button></td></tr>`).join('')}</tbody></table>`)}
    </div>
  </div>`;
}
function saveExp(){const a=parseFloat(document.getElementById('ex-a').value)||0;if(!a){toast('⚠️ أدخل المبلغ');return;}exp.push({id:Date.now(),type:document.getElementById('ex-t').value,desc:(document.getElementById('ex-d').value||'').trim(),amount:a,date:document.getElementById('ex-dt').value,notes:(document.getElementById('ex-n').value||'').trim(),who:CU?CU.name:'مدير'});lset(K.exp,exp);toast('✅ تم حفظ المصروف');rExp();}
function delExp(id){if(!confirm('حذف؟'))return;exp=exp.filter(e=>e.id!==id);lset(K.exp,exp);toast('🗑️ تم');rExp();}

// ═══════════════════════ FROZEN ═══════════════════════
let frzF={srch:’’,st:’’};
function rFrz(){
const filtered=frz.filter(f=>(f.name||’’).includes(frzF.srch)&&(!frzF.st||f.status===frzF.st));
pg().innerHTML=`

  <div class="card"><div class="stitle">❄️ تعليق أو إلغاء اشتراك</div>
    <div class="g3" style="margin-bottom:8px">
      <div class="fld"><label>المشترك</label><select id="fr-s"><option value="">-- اختر --</option>${subs.filter(s=>s.status==='active').map(s=>`<option value="${s.id}">${esc(s.name)}</option>`).join('')}</select></div>
      <div class="fld"><label>الحالة</label><select id="fr-st"><option value="frozen">❄️ متعلق</option><option value="cancelled">🚫 ملغي</option></select></div>
      <div class="fld"><label>التاريخ</label><input id="fr-dt" type="date" value="${td()}"></div>
    </div>
    <div class="fld"><label>السبب</label><textarea id="fr-r" rows="2" placeholder="السبب..."></textarea></div>
    <button class="btn btn-gold" onclick="saveFrz()">💾 تسجيل</button>
  </div>
  <div class="sgrid" style="grid-template-columns:repeat(3,1fr)">
    ${sbox(frz.length,'إجمالي السجلات')}${sbox(frz.filter(f=>f.status==='frozen').length,'متعلق ❄️','var(--bl)')}${sbox(frz.filter(f=>f.status==='cancelled').length,'ملغي 🚫','var(--rd)')}
  </div>
  <div style="display:flex;gap:8px;margin-bottom:10px">
    <input placeholder="🔍 بحث..." value="${esc(frzF.srch)}" oninput="frzF.srch=this.value;rFrz()" style="max-width:200px">
    <select onchange="frzF.st=this.value;rFrz()" style="max-width:150px"><option value="">الكل</option><option value="frozen"${frzF.st==='frozen'?' selected':''}>متعلق ❄️</option><option value="cancelled"${frzF.st==='cancelled'?' selected':''}>ملغي 🚫</option></select>
  </div>
  ${filtered.length===0?'<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا توجد سجلات</div>':tbl_wrap(`<table><thead><tr><th>التاريخ</th><th>الاسم</th><th>المنطقة</th><th>الحالة</th><th>السبب</th><th>حذف</th></tr></thead><tbody>${filtered.map(f=>`<tr><td style="color:var(--mu)">${esc(f.date)}</td><td style="font-weight:800">${esc(f.name)}</td><td>${badge('b-purple',f.area||'—')}</td><td>${f.status==='frozen'?badge('b-blue','❄️ متعلق'):badge('b-red','🚫 ملغي')}</td><td style="color:var(--mu);font-size:.73rem">${esc(f.reason||'—')}</td><td><button class="tbtn tb-dl" onclick="delFrz(${f.id})">🗑️</button></td></tr>`).join('')}</tbody></table>`)}`;
}
function saveFrz(){const id=parseInt(document.getElementById('fr-s').value);const s=subs.find(x=>x.id===id);if(!s){toast('⚠️ اختر مشتركاً');return;}frz.push({id:Date.now(),subId:s.id,name:s.name,phone:s.phone,area:s.area,subid:s.subid,status:document.getElementById('fr-st').value,date:document.getElementById('fr-dt').value,reason:(document.getElementById('fr-r').value||'').trim()});lset(K.frz,frz);toast('✅ تم التسجيل');rFrz();}
function delFrz(id){if(!confirm('حذف؟'))return;frz=frz.filter(f=>f.id!==id);lset(K.frz,frz);toast('🗑️ تم');rFrz();}

// ═══════════════════════ STAFF ═══════════════════════
let stfF={eid:null,lastId:null,srch:’’,role:’’,st:’’};
function rStf(){
const RC={‘سائق’:‘b-blue’,‘عامل’:‘b-green’,‘مستحصل’:‘b-gold’,‘مشرف’:‘b-purple’,‘أخرى’:‘b-orange’};
const es=stfF.eid?stf.find(s=>s.id===stfF.eid):null;
const filtered=stf.filter(s=>(s.name.includes(stfF.srch)||(s.role||’’).includes(stfF.srch))&&(!stfF.role||s.role===stfF.role)&&(!stfF.st||s.status===stfF.st));
const showBtns=stfF.eid||stfF.lastId;

pg().innerHTML=`

  <div style="display:grid;grid-template-columns:340px 1fr;gap:12px;align-items:start" class="mgrid">
    <div class="card"><div class="stitle">👷 ${stfF.eid?'تعديل موظف':'إضافة موظف'}</div>
      <div class="fld"><label>الاسم *</label><input id="sf-nm" value="${esc(es?es.name:'')}" placeholder="الاسم الكامل"></div>
      <div class="g2">
        <div class="fld"><label>الوظيفة</label><select id="sf-rl">${ROLES_S.map(r=>`<option${es&&es.role===r?' selected':''}>${esc(r)}</option>`).join('')}</select></div>
        <div class="fld"><label>الهاتف</label><input id="sf-ph" value="${esc(es?es.phone||'':'')}" placeholder="07xxxxxxxxx"></div>
      </div>
      <div style="background:rgba(245,158,11,.07);border:1px solid rgba(245,158,11,.25);border-radius:8px;padding:10px 12px;margin-bottom:10px">
        <div style="font-size:.75rem;font-weight:800;color:var(--gol);margin-bottom:8px">💰 الراتب</div>
        <div class="g2" style="margin-bottom:8px">
          <div class="fld"><label>الراتب الشهري *</label><input id="sf-ms" type="number" value="${es?es.ms||'':''}" placeholder="0" oninput="updStfCalc()"></div>
          <div class="fld"><label>أيام العمل بالشهر</label><input id="sf-wd" type="number" value="${es?es.wd||26:26}" placeholder="26" oninput="updStfCalc()"></div>
        </div>
        <div class="fld"><label>الأيام الفعلية</label><input id="sf-ad" type="number" value="${es?es.ad||'':''}" placeholder="0" oninput="updStfCalc()"></div>
        <div id="sf-calc" style="font-size:.75rem;color:var(--mu);margin-top:6px"></div>
      </div>
      <div style="background:rgba(239,68,68,.07);border:1px solid rgba(239,68,68,.2);border-radius:8px;padding:10px 12px;margin-bottom:10px">
        <div style="font-size:.75rem;font-weight:800;color:var(--rd);margin-bottom:8px">✂️ الخصومات (اختياري)</div>
        <div class="fld"><label>مبلغ الخصم</label><input id="sf-dd" type="number" value="${es?es.ded||'':''}" placeholder="0" oninput="updStfCalc()"></div>
        <div class="fld"><label>سبب الخصم</label><input id="sf-dr" value="${esc(es?es.dedr||'':'')}" placeholder="غياب / تأخير / ..."></div>
      </div>
      <div style="background:rgba(16,185,129,.08);border:1px solid rgba(16,185,129,.25);border-radius:8px;padding:10px 12px;margin-bottom:10px;display:flex;justify-content:space-between;align-items:center">
        <span style="font-size:.85rem;color:var(--mu);font-weight:700">💵 صافي الراتب</span>
        <span style="font-size:1.1rem;font-weight:900;color:var(--gl)" id="sf-net">0 دينار</span>
      </div>
      <div class="g2" style="margin-bottom:8px">
        <div class="fld"><label>تاريخ البدء</label><input id="sf-st" type="date" value="${es?es.start||td():td()}"></div>
        <div class="fld"><label>الحالة</label><select id="sf-ss"><option value="active"${!es||es.status==='active'?' selected':''}>✅ نشط</option><option value="inactive"${es&&es.status==='inactive'?' selected':''}>❌ متوقف</option></select></div>
      </div>
      <div class="fld"><label>ملاحظات</label><textarea id="sf-nt" rows="2">${esc(es?es.notes||'':'')}</textarea></div>
      <div style="display:flex;gap:6px;margin-bottom:8px">
        <button class="btn btn-green" style="flex:1;justify-content:center" onclick="saveStf()">💾 ${stfF.eid?'تحديث':'حفظ'}</button>
        <button class="btn btn-ghost" style="flex:1;justify-content:center" onclick="stfF.eid=null;stfF.lastId=null;rStf()">✖ مسح</button>
      </div>
      ${showBtns?`<div style="display:flex;gap:6px">
        <button class="btn btn-wa" style="flex:1;justify-content:center" onclick="stfWA(${stfF.eid||stfF.lastId})">💬 واتساب</button>
        <button class="btn btn-gold" style="flex:1;justify-content:center" onclick="stfRcp(${stfF.eid||stfF.lastId})">🧾 وصل</button>
      </div>`:'<div style="font-size:.71rem;color:var(--mu);text-align:center">💡 بعد الحفظ تظهر أزرار الواتساب والوصل</div>'}
    </div>
    <div>
      <div class="sgrid" style="grid-template-columns:repeat(4,1fr)">
        ${sbox(stf.length,'إجمالي الكادر')}${sbox(stf.filter(s=>s.status==='active').length,'نشطون','var(--gl)')}${sbox(fmt(stf.reduce((a,s)=>a+(s.net||0),0))+' د.ع','إجمالي الرواتب','var(--gol)')}${sbox(fmt(stf.reduce((a,s)=>a+(s.ded||0),0))+' د.ع','الخصومات','#f87171')}
      </div>
      <div style="display:flex;gap:8px;margin-bottom:10px;flex-wrap:wrap">
        <input placeholder="🔍 بحث..." value="${esc(stfF.srch)}" oninput="stfF.srch=this.value;rStf()" style="max-width:180px">
        <select onchange="stfF.role=this.value;rStf()" style="max-width:140px"><option value="">كل الوظائف</option>${ROLES_S.map(r=>`<option${stfF.role===r?' selected':''}>${esc(r)}</option>`).join('')}</select>
        <select onchange="stfF.st=this.value;rStf()" style="max-width:130px"><option value="">الكل</option><option value="active"${stfF.st==='active'?' selected':''}>نشط</option><option value="inactive"${stfF.st==='inactive'?' selected':''}>متوقف</option></select>
      </div>
      ${filtered.length===0?'<div style="text-align:center;padding:40px;color:var(--mu)">📭 لا يوجد كادر</div>':tbl_wrap(`<table><thead><tr><th>الاسم</th><th>الوظيفة</th><th>الراتب الشهري</th><th>الأيام الفعلية</th><th>المستحق</th><th>الخصم</th><th>الصافي</th><th>الحالة</th><th>إجراءات</th></tr></thead><tbody>${filtered.map(s=>`<tr><td style="font-weight:800">${esc(s.name)}</td><td>${badge(RC[s.role]||'b-gold',s.role)}</td><td style="color:var(--gol);font-weight:700">${fmt(s.ms||0)}</td><td style="color:var(--bl);font-weight:700">${s.ad||0}</td><td style="color:var(--gl);font-weight:700">${fmt(Math.round(s.earned||0))}</td><td style="color:${(s.ded||0)>0?'#f87171':'var(--mu)'}">${(s.ded||0)>0?fmt(s.ded):'—'}</td><td style="color:var(--gol);font-weight:900">${fmt(Math.round(s.net||0))}</td><td>${s.status==='active'?badge('b-green','✅ نشط'):badge('b-red','❌ متوقف')}</td><td><button class="tbtn tb-ed" onclick="editStf(${s.id})">✏️</button><button class="tbtn tb-wa" onclick="stfWA(${s.id})">💬</button><button class="tbtn tb-rc" onclick="stfRcp(${s.id})">🧾</button><button class="tbtn tb-dl" onclick="delStf(${s.id})">🗑️</button></td></tr>`).join('')}</tbody></table>`)}
    </div>
  </div>`;
  setTimeout(updStfCalc,50);
}
function updStfCalc(){
  const ms=parseFloat(document.getElementById('sf-ms')&&document.getElementById('sf-ms').value)||0;
  const wd=parseInt(document.getElementById('sf-wd')&&document.getElementById('sf-wd').value)||26;
  const ad=parseInt(document.getElementById('sf-ad')&&document.getElementById('sf-ad').value)||0;
  const ded=parseFloat(document.getElementById('sf-dd')&&document.getElementById('sf-dd').value)||0;
  const daily=wd>0?ms/wd:0,earned=daily*ad,net=Math.max(0,earned-ded);
  const c=document.getElementById('sf-calc'),n=document.getElementById('sf-net');
  if(c)c.innerHTML=ms>0?`الأجر اليومي: <b style="color:var(--gol)">${fmt(Math.round(daily))} دينار</b>${ad>0?` | المستحق: <b style="color:var(--gl)">${fmt(Math.round(earned))} دينار</b>`:''}`:' ';
  if(n)n.textContent=fmt(Math.round(net))+' دينار';
}
function saveStf(){
  const name=(document.getElementById('sf-nm')&&document.getElementById('sf-nm').value||'').trim();
  const ms=parseFloat(document.getElementById('sf-ms')&&document.getElementById('sf-ms').value)||0;
  if(!name){toast('⚠️ أدخل الاسم');return;}if(!ms){toast('⚠️ أدخل الراتب');return;}
  const wd=parseInt(document.getElementById('sf-wd').value)||26;
  const ad=parseInt(document.getElementById('sf-ad').value)||0;
  const ded=parseFloat(document.getElementById('sf-dd').value)||0;
  const daily=wd>0?ms/wd:0,earned=daily*ad,net=Math.max(0,earned-ded);
  const rec={id:stfF.eid||Date.now(),name,role:document.getElementById('sf-rl').value,phone:(document.getElementById('sf-ph').value||'').trim(),ms,wd,ad,daily,earned,ded,dedr:(document.getElementById('sf-dr').value||'').trim(),net,status:document.getElementById('sf-ss').value,start:document.getElementById('sf-st').value,notes:(document.getElementById('sf-nt').value||'').trim()};
  if(stfF.eid)stf=stf.map(s=>s.id===stfF.eid?rec:s);else stf.push(rec);
  lset(K.stf,stf);stfF.lastId=rec.id;stfF.eid=null;toast('✅ تم الحفظ');rStf();
}
function editStf(id){stfF.eid=id;stfF.lastId=null;rStf();}
function delStf(id){if(!confirm('حذف؟'))return;stf=stf.filter(s=>s.id!==id);lset(K.stf,stf);toast('🗑️ تم');rStf();}
function stfWA(id){
  const s=stf.find(x=>x.id===id);if(!s){toast('⚠️ لم يتم العثور على الموظف');return;}
  const msg=`*${cfg.name}* 🧹\n━━━━━━━━━━━━━━━━\n👷 *${s.name}* | ${s.role||'—'}\n━━━━━━━━━━━━━━━━\n💰 الراتب الشهري: *${fmt(s.ms||0)} دينار*\n📆 أيام العمل: ${s.wd||26} | الفعلية: *${s.ad||0} يوم*\n💵 الأجر اليومي: ${fmt(Math.round(s.daily||0))} دينار\n📊 المستحق: ${fmt(Math.round(s.earned||0))} دينار\n${(s.ded||0)>0?'✂️ خصم: '+fmt(s.ded)+' دينار'+(s.dedr?' ('+s.dedr+')':'')+'\n':''}\n━━━━━━━━━━━━━━━━\n*💵 صافي الراتب: ${fmt(Math.round(s.net||0))} دينار*\n━━━━━━━━━━━━━━━━\nللاستفسار: ${cfg.phone}\nشكراً 🌿`;
  wa(s.phone,msg);
}
function stfRcp(id){
  const s=stf.find(x=>x.id===id);if(!s){toast('⚠️ احفظ الموظف أولاً');return;}
  document.getElementById('rcp-content').innerHTML=`
    <div style="background:#111;padding:12px 15px;text-align:center"><div style="color:#d4a017;font-size:1rem;font-weight:900">${esc(cfg.name)}</div><div style="color:#888;font-size:.68rem;margin-top:2px">كشف راتب موظف</div></div>
    <div style="padding:11px 14px">
      ${[['الاسم',s.name],['الوظيفة',s.role||'—'],['الهاتف',s.phone||'—'],['الراتب الشهري',fmt(s.ms||0)+' د.ع'],['أيام العمل بالشهر',(s.wd||26)+' يوم'],['الأيام الفعلية',(s.ad||0)+' يوم'],['الأجر اليومي',fmt(Math.round(s.daily||0))+' د.ع'],['المستحق',fmt(Math.round(s.earned||0))+' د.ع']].map(([l,v])=>`<div class="rr"><span style="color:#777">${esc(l)}</span><span style="font-weight:700">${esc(v)}</span></div>`).join('')}
      ${(s.ded||0)>0?`<div class="rr"><span style="color:#c0392b;font-weight:700">✂️ خصم${s.dedr?' ('+s.dedr+')':''}</span><span style="font-weight:700;color:#c0392b">${fmt(s.ded)} د.ع</span></div>`:''}
      <div style="display:flex;justify-content:space-between;padding:6px 0;border-top:2px solid #111;margin-top:5px"><span style="font-weight:900">💵 صافي الراتب</span><span style="font-weight:900;color:#1a7a30;font-size:1.05rem">${fmt(Math.round(s.net||0))} د.ع</span></div>
    </div>
    <div style="background:#f5f2ec;padding:8px 14px;text-align:center;border-top:1px solid #e0ddd8;font-size:.7rem;color:#666"><div style="font-weight:700;color:#111;margin-bottom:2px">للاستفسار</div><div>${esc(cfg.phone)}${cfg.extra?' — '+esc(cfg.extra):''}</div></div>
    <div style="display:grid;grid-template-columns:1fr 1fr;border-top:1px solid #e0ddd8"><button style="font-family:'Tajawal',sans-serif;font-weight:800;font-size:.83rem;padding:10px;border:none;cursor:pointer;background:#f0ede8;color:#333;border-right:1px solid #e0ddd8" onclick="closeRcp()">✖ إغلاق</button><button style="font-family:'Tajawal',sans-serif;font-weight:800;font-size:.83rem;padding:10px;border:none;cursor:pointer;background:#111;color:#d4a017" onclick="window.print()">🖨️ طباعة</button></div>`;
  document.getElementById('ov-rcp').classList.add('open');
}

// ═══════════════════════ SETTINGS ═══════════════════════
function rSettings(){
pg().innerHTML=`

  <div style="max-width:700px;display:grid;grid-template-columns:1fr 1fr;gap:12px;align-items:start" class="mgrid">
    <div>
      <div class="card"><div class="stitle">🏢 إعدادات النظام</div>
        <div class="fld"><label>اسم الخدمة</label><input id="cfg-n" value="${esc(cfg.name)}"></div>
        <div class="fld"><label>رقم الشكاوي</label><input id="cfg-p" value="${esc(cfg.phone)}"></div>
        <div class="fld"><label>نص إضافي في الوصل</label><input id="cfg-e" value="${esc(cfg.extra||'')}"></div>
        <button class="btn btn-green" onclick="saveCfg()">💾 حفظ</button>
      </div>
      <div class="card"><div class="stitle">📍 إدارة المناطق</div>
        <div style="display:flex;flex-wrap:wrap;gap:7px;margin-bottom:12px">
          ${areas.map(a=>`<span style="background:var(--c2);border:1px solid var(--bdr);color:var(--tx);font-size:.8rem;font-weight:600;padding:4px 10px;border-radius:20px;display:inline-flex;align-items:center;gap:6px">${esc(a)}<button style="background:none;border:none;color:var(--rd);cursor:pointer;font-size:.85rem" onclick="delArea('${esc(a).replace(/'/g,"\\'")}')">✕</button></span>`).join('')}
        </div>
        <div style="display:flex;gap:8px"><input id="na" placeholder="منطقة جديدة" style="flex:1"><button class="btn btn-blue" onclick="addArea()">+ إضافة</button></div>
      </div>
      <div class="card"><div class="stitle">💾 البيانات</div>
        <div style="display:flex;gap:10px;flex-wrap:wrap">
          <button class="btn btn-blue" onclick="exportAll()">📤 تصدير الكل</button>
          <button class="btn btn-ghost" onclick="document.getElementById('imp-f').click()">📥 استيراد</button>
          <input type="file" id="imp-f" accept=".json" style="display:none;width:auto" onchange="importAll(event)">
        </div>
        <div style="margin-top:8px;font-size:.75rem;color:var(--mu)">💡 صدّر البيانات بشكل دوري كنسخة احتياطية</div>
      </div>
    </div>
    <div class="card"><div class="stitle">👥 إدارة المستخدمين</div>
      <div style="margin-bottom:14px">
        ${users.map(u=>`<div style="display:flex;align-items:center;justify-content:space-between;padding:8px 10px;background:var(--bg);border:1px solid var(--bdr);border-radius:7px;margin-bottom:6px">
          <div><div style="font-weight:700;font-size:.85rem;color:${u.active?'var(--tx)':'var(--mu)'}">${esc(u.name)}</div><div style="font-size:.7rem;color:var(--mu)">${esc(u.username)} | ${u.role==='manager'?'👑 مدير':'💰 مستحصل'}</div></div>
          <div style="display:flex;gap:5px">
            <button class="tbtn ${u.active?'tb-ed':'tb-dl'}" onclick="toggleUser(${u.id})">${u.active?'✅ نشط':'❌ معطل'}</button>
            ${u.id!==1?`<button class="tbtn tb-dl" onclick="delUser(${u.id})">🗑️</button>`:''}
          </div>
        </div>`).join('')}
      </div>
      <div style="border-top:1px solid var(--bdr);padding-top:12px">
        <div style="font-size:.78rem;font-weight:700;color:var(--mu);margin-bottom:8px">إضافة مستخدم جديد:</div>
        <div class="fld"><label>الاسم الظاهر</label><input id="nu-n" placeholder="مثال: أحمد المستحصل"></div>
        <div class="g2">
          <div class="fld"><label>اسم المستخدم</label><input id="nu-u" placeholder="username"></div>
          <div class="fld"><label>كلمة المرور</label><input id="nu-p" placeholder="password"></div>
        </div>
        <div class="fld"><label>الصلاحية</label><select id="nu-r"><option value="collector">💰 مستحصل</option><option value="manager">👑 مدير</option></select></div>
        <button class="btn btn-purple btn-full" onclick="addUser()">+ إضافة مستخدم</button>
      </div>
    </div>
  </div>`;
}
function saveCfg(){cfg.name=(document.getElementById('cfg-n').value||cfg.name).trim();cfg.phone=(document.getElementById('cfg-p').value||cfg.phone).trim();cfg.extra=(document.getElementById('cfg-e').value||'').trim();lset(K.cfg,cfg);document.getElementById('app-logo').textContent='🧹 '+cfg.name;toast('✅ تم حفظ الإعدادات');}
function addArea(){const v=(document.getElementById('na').value||'').trim();if(!v||areas.includes(v)){toast('⚠️ اسم غير صالح أو موجود');return;}areas.push(v);lset(K.areas,areas);document.getElementById('na').value='';toast('✅ تمت الإضافة');rSettings();}
function delArea(a){if(!confirm('حذف: '+a+'؟'))return;areas=areas.filter(x=>x!==a);lset(K.areas,areas);toast('🗑️ تم');rSettings();}
function toggleUser(id){users=users.map(u=>u.id===id?{...u,active:!u.active}:u);lset(K.users,users);rSettings();}
function delUser(id){if(id===1){toast('⚠️ لا يمكن حذف المدير الرئيسي');return;}if(!confirm('حذف المستخدم؟'))return;users=users.filter(u=>u.id!==id);lset(K.users,users);toast('🗑️ تم');rSettings();}
function addUser(){
  const n=(document.getElementById('nu-n').value||'').trim(),u=(document.getElementById('nu-u').value||'').trim(),p=(document.getElementById('nu-p').value||'').trim(),r=document.getElementById('nu-r').value;
  if(!n||!u||!p){toast('⚠️ أكمل البيانات');return;}if(users.find(x=>x.username===u)){toast('⚠️ اسم المستخدم موجود');return;}
  users.push({id:Date.now(),username:u,password:p,role:r,name:n,active:true});lset(K.users,users);toast('✅ تمت إضافة المستخدم');rSettings();
}
function exportAll(){
  const d={subs,col,exp,frz,stf,areas,cfg,users};
  const a=document.createElement('a');a.href='data:application/json;charset=utf-8,'+encodeURIComponent(JSON.stringify(d,null,2));a.download='نظام_التنظيف_'+new Date().toISOString().slice(0,10)+'.json';a.click();toast('📤 تم التصدير');
}
function importAll(e){
  const file=e.target.files[0];if(!file)return;
  const r=new FileReader();r.onload=ev=>{try{const d=JSON.parse(ev.target.result);if(d.subs){subs=d.subs;lset(K.subs,subs);}if(d.col){col=d.col;lset(K.col,col);}if(d.exp){exp=d.exp;lset(K.exp,exp);}if(d.frz){frz=d.frz;lset(K.frz,frz);}if(d.stf){stf=d.stf;lset(K.stf,stf);}if(d.areas){areas=d.areas;lset(K.areas,areas);}if(d.cfg){cfg=d.cfg;lset(K.cfg,cfg);}if(d.users){users=d.users;lset(K.users,users);}toast('📥 تم الاستيراد بنجاح');}catch{toast('⚠️ ملف غير صالح');}};r.readAsText(file);e.target.value='';
}

// ═══════════════════════ INIT ═══════════════════════
document.getElementById(‘login-title’).textContent=cfg.name;
</script>

</body>
</html>
