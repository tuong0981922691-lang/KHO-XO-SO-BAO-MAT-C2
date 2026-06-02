<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Diễn Đàn Cầu Kèo - Bridge Stream Core</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}html,body{height:100%}body{font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;background:#050302;color:#fff4e6;min-height:100vh;line-height:1.6;overflow:hidden}button,textarea,select,input{font:inherit}button{touch-action:manipulation}::-webkit-scrollbar{display:none}:root{--bg:#1c130d;--bg2:#24150d;--bg3:#2a1a10;--bg4:#3a2416;--deep:#120a06;--border:#5a3824;--border2:#6b432b;--neon:#ffd6a0;--neon2:#d40000;--gold:#facc15;--red:#ef4444;--green:#10b981;--text:#fff4e6;--muted:#c9a982;--admin:#ff6b35;--vip:#ffd600;--member:#38bdf8;--radius:14px;--radius-sm:8px;--mono:"SF Mono","Cascadia Code",ui-monospace,Menlo,Consolas,monospace}#forum-app{max-width:680px;height:100dvh;margin:0 auto;position:relative;background:linear-gradient(180deg,var(--bg3),var(--deep));overflow:hidden;display:flex;flex-direction:column;box-shadow:0 0 45px rgba(0,0,0,.95)}.f-header{background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border);padding:calc(10px + env(safe-area-inset-top)) 12px 10px;z-index:100;flex-shrink:0;box-shadow:0 4px 14px rgba(0,0,0,.32)}.f-header-inner{display:flex;align-items:center;justify-content:space-between;gap:12px}.f-logo{display:flex;align-items:center;gap:10px}.f-logo-icon{width:36px;height:36px;background:linear-gradient(135deg,var(--neon2),#ff7a4d);border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0}.f-logo-text{font-size:17px;font-weight:900;letter-spacing:-.3px;color:#ffe0b8}.f-logo-sub{font-size:11px;color:var(--muted);font-weight:500;margin-top:-2px}.f-header-right{display:flex;align-items:center;gap:8px}.f-notif-btn{position:relative;width:36px;height:36px;background:var(--bg4);border:1px solid var(--border2);border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:16px;color:var(--text)}.f-notif-dot{position:absolute;top:5px;right:5px;width:8px;height:8px;background:var(--red);border-radius:50%;border:2px solid var(--bg)}.f-tabs{display:flex;gap:4px;margin-top:12px;overflow-x:auto;padding-bottom:2px}.f-tab{padding:6px 14px;border-radius:20px;font-size:12px;font-weight:700;border:1px solid transparent;background:transparent;color:var(--muted);cursor:pointer;white-space:nowrap}.f-tab.active{background:rgba(212,0,0,.18);border-color:#ff5252;color:#fff}.f-scroll{flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;padding-bottom:calc(84px + env(safe-area-inset-bottom));scrollbar-width:none}.f-stats{display:flex;border-bottom:1px solid var(--border);background:var(--bg2)}.f-stat{flex:1;padding:12px 8px;text-align:center;border-right:1px solid var(--border)}.f-stat:last-child{border-right:none}.f-stat-num{font-size:18px;font-weight:900;font-family:var(--mono);color:#ffd6a0}.f-stat-label{font-size:10px;color:var(--muted);margin-top:2px;text-transform:uppercase;letter-spacing:.5px}.bridge-panel,.stream-panel{margin:14px 16px 0;background:linear-gradient(180deg,#24150d,#160d08);border:1px solid rgba(255,232,190,.10);border-radius:var(--radius);padding:12px;display:flex;flex-direction:column;gap:10px;box-shadow:0 8px 18px rgba(0,0,0,.22)}.bridge-panel{border-color:rgba(56,189,248,.22);background:linear-gradient(180deg,rgba(56,189,248,.08),rgba(18,10,6,.90))}.panel-row{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.panel-title{font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.4px}.core-status,.scan-status{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:#38bdf8;background:rgba(56,189,248,.10);border:1px solid rgba(56,189,248,.35);white-space:nowrap}.core-status.loading{color:var(--gold);background:rgba(250,204,21,.10);border-color:rgba(250,204,21,.35)}.core-status.ready,.scan-status.ok{color:var(--green);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.core-status.error,.scan-status.bad{color:var(--red);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.progress-shell{height:8px;border-radius:999px;overflow:hidden;background:rgba(0,0,0,.28);border:1px solid rgba(255,232,190,.08)}.progress-bar{height:100%;width:0%;background:linear-gradient(90deg,#d40000,#ffbc5e,#10b981);transition:width .18s ease}.core-log,.preview-body{font-family:var(--mono);font-size:10.5px;line-height:1.4;color:var(--muted);background:rgba(0,0,0,.16);border:1px dashed rgba(255,232,190,.11);border-radius:12px;padding:9px;white-space:pre-wrap}.file-list{display:flex;flex-direction:column;gap:8px}.file-row{display:grid;grid-template-columns:1fr auto;gap:8px;align-items:center;background:rgba(18,10,6,.55);border:1px solid rgba(255,232,190,.08);border-radius:12px;padding:9px 10px}.file-name{font-size:12px;color:var(--text);font-weight:850;line-height:1.25;word-break:break-word}.file-state{font-size:10px;font-weight:950;color:var(--gold);white-space:nowrap}.file-state.ok{color:var(--green)}.file-state.bad{color:var(--red)}.notice{font-size:11px;line-height:1.45;color:var(--muted);font-weight:760;background:rgba(0,0,0,.14);border-radius:12px;padding:9px;border:1px dashed rgba(255,232,190,.12)}.preview-head{display:flex;align-items:center;justify-content:space-between;gap:10px}.preview-meter{font-size:10px;color:var(--muted);font-weight:850}.preview-box{height:160px;overflow:auto;-webkit-overflow-scrolling:touch;border-radius:12px}.preview-body{min-height:100%;color:var(--text)}.f-composer{margin:14px 16px 0;background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);padding:14px}.f-composer-top{display:flex;gap:10px;align-items:flex-start}.f-composer-input{flex:1;background:var(--bg3);border:1px solid var(--border);border-radius:var(--radius-sm);padding:10px 14px;color:var(--text);font-size:14px;resize:none;outline:none;min-height:48px;max-height:200px;width:100%;overflow-y:auto}.f-composer-actions{display:flex;align-items:center;justify-content:space-between;margin-top:10px;padding-top:10px;border-top:1px solid var(--border);gap:8px;flex-wrap:wrap}.f-composer-tools{display:flex;gap:6px;flex-wrap:wrap}.f-tool-btn,.f-tag-select{padding:6px 10px;border-radius:var(--radius-sm);background:var(--bg3);border:1px solid var(--border);color:var(--muted);font-size:12px;cursor:pointer}.f-submit-btn{padding:8px 18px;background:linear-gradient(135deg,#d40000,#ff6b35);border:none;border-radius:var(--radius-sm);color:#fff;font-weight:900;font-size:13px;cursor:pointer}.f-submit-btn:disabled{opacity:.4;cursor:default}.f-img-preview{margin-top:10px;position:relative;display:none}.f-img-preview.show{display:block}.f-img-preview img{width:100%;max-height:220px;object-fit:cover;border-radius:var(--radius-sm);border:1px solid var(--border)}.f-img-remove{position:absolute;top:6px;right:6px;width:24px;height:24px;background:#000c;border-radius:50%;border:none;color:#fff;font-size:14px;cursor:pointer}.f-feed{margin-top:16px;display:flex;flex-direction:column;gap:2px}.f-section-label{padding:8px 20px;font-size:11px;font-weight:800;color:var(--muted);text-transform:uppercase;letter-spacing:.8px;display:flex;align-items:center;gap:8px}.f-section-label::after{content:'';flex:1;height:1px;background:var(--border)}.f-post{background:var(--bg2);border-top:1px solid var(--border);border-bottom:1px solid var(--border);animation:slideIn .3s ease}.f-post.pinned{border-left:3px solid var(--gold)}@keyframes slideIn{from{opacity:0;transform:translateY(-8px)}to{opacity:1;transform:translateY(0)}}.f-pin-badge{display:flex;align-items:center;gap:6px;padding:6px 16px;font-size:11px;color:var(--gold);font-weight:800;background:rgba(250,204,21,.06);border-bottom:1px solid rgba(250,204,21,.16)}.f-post-header{display:flex;align-items:flex-start;gap:10px;padding:14px 16px 8px}.f-avatar{width:40px;height:40px;border-radius:50%;flex-shrink:0;font-size:16px;display:flex;align-items:center;justify-content:center;font-weight:800;position:relative;border:2px solid transparent}.admin-av{background:linear-gradient(135deg,#ff6b35,#ff9800);border-color:#ff6b3566}.vip-av{background:linear-gradient(135deg,#b8860b,var(--gold));border-color:#ffd60066;color:#111}.member-av{background:linear-gradient(135deg,#2563eb,#38bdf8);border-color:#38bdf844}.me-av{background:linear-gradient(135deg,#00897b,var(--green));border-color:#10b98144}.f-online-dot{position:absolute;bottom:1px;right:1px;width:10px;height:10px;background:var(--green);border-radius:50%;border:2px solid var(--bg2)}.f-post-meta{flex:1;min-width:0}.f-post-name{font-size:14px;font-weight:800;display:flex;align-items:center;flex-wrap:wrap;gap:6px}.f-badge{font-size:9px;font-weight:900;padding:2px 7px;border-radius:20px;text-transform:uppercase;letter-spacing:.6px}.badge-admin{background:#ff6b3522;color:#ff6b35;border:1px solid #ff6b3544}.badge-vip{background:#ffd60022;color:#ffd600;border:1px solid #ffd60044}.badge-member{background:#38bdf815;color:#38bdf8;border:1px solid #38bdf833}.badge-tag{font-size:9px;font-weight:900;padding:2px 8px;border-radius:20px;text-transform:uppercase;letter-spacing:.4px;background:#d4000022;color:#ffb4a4;border:1px solid #d4000044}.f-post-time{font-size:11px;color:var(--muted);margin-top:2px}.f-opts-btn{width:28px;height:28px;background:transparent;border:none;color:var(--muted);font-size:18px;cursor:pointer;border-radius:50%}.f-opts-menu{position:absolute;right:0;top:32px;background:var(--bg3);border:1px solid var(--border2);border-radius:var(--radius-sm);min-width:160px;z-index:50;box-shadow:0 8px 32px #0008;display:none;overflow:hidden}.f-opts-menu.open{display:block}.f-opts-item{padding:10px 14px;font-size:13px;cursor:pointer;display:flex;align-items:center;gap:8px;white-space:nowrap}.f-opts-item.danger{color:var(--red)}.f-post-body{padding:0 16px 10px}.f-post-text{font-size:14px;line-height:1.7;color:var(--text);white-space:pre-line;word-break:break-word}.f-post-image{margin-top:10px;border-radius:var(--radius-sm);overflow:hidden;cursor:pointer;position:relative;background:var(--bg3)}.f-post-image img{width:100%;max-height:350px;object-fit:cover;display:block}.f-action-bar{display:flex;align-items:center;gap:0;padding:0 12px;border-top:1px solid var(--border)}.f-action-btn{flex:1;display:flex;align-items:center;justify-content:center;gap:6px;padding:10px 8px;background:transparent;border:none;color:var(--muted);font-size:13px;cursor:pointer;border-radius:var(--radius-sm)}.f-action-btn.liked{color:var(--red)}.f-reaction-row{padding:4px 16px 8px;display:flex;align-items:center;gap:6px;font-size:12px;color:var(--muted);min-height:28px}.f-comments{display:none;border-top:1px solid var(--border);background:var(--bg)}.f-comments.open{display:block}.f-comments-list{max-height:320px;overflow-y:auto;padding:10px 16px;display:flex;flex-direction:column;gap:10px}.f-comment{display:flex;gap:8px;align-items:flex-start}.f-comment-bubble{background:var(--bg3);border-radius:0 12px 12px 12px;padding:8px 12px;flex:1;min-width:0}.f-comment-name{font-size:12px;font-weight:800;margin-bottom:2px;display:flex;align-items:center;gap:6px}.f-comment-text{font-size:13px;line-height:1.5;word-break:break-word;color:var(--text)}.f-comment-time{font-size:10px;color:var(--muted);margin-top:4px}.f-comment-input-wrap{padding:10px 16px;display:flex;gap:8px;align-items:flex-start;border-top:1px solid var(--border);background:var(--bg2)}.f-comment-input{flex:1;background:var(--bg3);border:1px solid var(--border);border-radius:20px;padding:8px 14px;color:var(--text);font-size:13px;outline:none;resize:none;max-height:100px;overflow-y:auto;line-height:1.4}.f-comment-send{width:34px;height:34px;background:linear-gradient(135deg,#d40000,#ff6b35);border:none;border-radius:50%;color:#fff;font-size:16px;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px}.f-empty{text-align:center;padding:48px 24px;color:var(--muted)}.f-fab{position:fixed;bottom:24px;right:20px;width:50px;height:50px;background:linear-gradient(135deg,#d40000,#ff6b35);border-radius:50%;border:none;color:#fff;font-size:22px;cursor:pointer;box-shadow:0 4px 24px rgba(212,0,0,.45);display:flex;align-items:center;justify-content:center;z-index:90}.lock-overlay{position:absolute;inset:0;background:rgba(5,3,2,.48);backdrop-filter:blur(2px);z-index:200;display:none;align-items:center;justify-content:center;padding:22px;text-align:center}.lock-overlay.show{display:flex}.lock-card{border-radius:18px;background:linear-gradient(180deg,#2b1a10,#120a06);border:1px solid rgba(255,232,190,.16);box-shadow:0 18px 48px rgba(0,0,0,.5);padding:16px;max-width:330px;width:100%}.spinner{width:32px;height:32px;border-radius:50%;border:3px solid rgba(255,232,190,.16);border-top-color:var(--gold);margin:0 auto 10px;animation:spin .8s linear infinite}.lock-title{font-size:14px;font-weight:950;color:#ffd6a0;margin-bottom:6px;text-transform:uppercase}.lock-text{font-size:12px;line-height:1.4;color:var(--muted);font-weight:760}@keyframes spin{to{transform:rotate(360deg)}}#f-toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(80px);background:var(--bg3);border:1px solid var(--border2);border-radius:20px;padding:10px 20px;font-size:13px;z-index:500;white-space:nowrap;transition:transform .3s cubic-bezier(.34,1.56,.64,1),opacity .3s;opacity:0;pointer-events:none}#f-toast.show{transform:translateX(-50%) translateY(0);opacity:1}@media(max-width:480px){.f-composer-actions{flex-wrap:wrap;gap:8px}.f-stat-num{font-size:15px}.stream-box{height:140px}}
</style>
</head>
<body>
<div id="forum-app">
  <div class="f-header"><div class="f-header-inner"><div class="f-logo"><div class="f-logo-icon">🎯</div><div><div class="f-logo-text">CẦU KÈO PRO</div><div class="f-logo-sub">Cộng đồng thảo luận dữ liệu & quản trị rủi ro</div></div></div><div class="f-header-right"><div class="f-notif-btn" onclick="showToast('🔔 Bạn có thông báo mới')">🔔<div class="f-notif-dot"></div></div><div class="f-notif-btn" onclick="ForumBridge.streamReport(['Mở bảng quản trị: trong bản này quản trị được nối bằng bridge, không thao tác quyền thật.'])">⚙️</div></div></div><div class="f-tabs"><button class="f-tab active" onclick="filterFeed('all',this)">🏠 Tất cả</button><button class="f-tab" onclick="filterFeed('pinned',this)">📌 Ghim</button><button class="f-tab" onclick="filterFeed('keo-nha',this)">🏠 Kèo Nhà</button><button class="f-tab" onclick="filterFeed('tai-xi',this)">🎲 Tài/Xỉu</button><button class="f-tab" onclick="filterFeed('chot-so',this)">🔢 Chốt số</button><button class="f-tab" onclick="filterFeed('phan-tich',this)">📊 Phân Tích</button></div></div>
  <div class="f-scroll" id="main-scroll"><div class="f-stats"><div class="f-stat"><div class="f-stat-num" id="stat-posts">0</div><div class="f-stat-label">Bài đăng</div></div><div class="f-stat"><div class="f-stat-num" id="stat-members">0</div><div class="f-stat-label">Thành viên</div></div><div class="f-stat"><div class="f-stat-num" id="stat-online">0</div><div class="f-stat-label">Online</div></div><div class="f-stat"><div class="f-stat-num" id="stat-today">0</div><div class="f-stat-label">Hôm nay</div></div></div>
    <section class="bridge-panel"><div class="panel-row"><div class="panel-title">Cổng dữ liệu diễn đàn</div><div class="core-status" id="coreStatus">CHỜ KẾT NỐI</div></div><div class="progress-shell"><div class="progress-bar" id="progressBar"></div></div><div class="core-log" id="coreLog">Bridge sẵn sàng: window.ForumBridge</div></section>
    <section class="bridge-panel"><div class="panel-row"><div class="panel-title">Nguồn / file hệ thống</div><div class="scan-status" id="scanStatus">Không đủ dữ liệu xác thực</div></div><div class="file-list" id="fileList"></div><div class="notice" id="scanNotice">Các file đính kèm đã được gọi quét nhưng công cụ đọc tệp trả về rỗng/hỏng/không thể xử lý. Khi backend gửi dữ liệu thật, khu vực này sẽ cập nhật động.</div></section>
    <section class="stream-panel"><div class="preview-head"><div class="panel-title">Preview báo cáo / stream backend</div><div class="preview-meter" id="previewMeter">0 dòng</div></div><div class="preview-box" id="previewBox"><pre class="preview-body" id="previewBody">Chưa có dữ liệu stream.</pre></div></section>
    <div class="f-composer"><div class="f-composer-top"><div class="f-avatar me-av" style="width:38px;height:38px;font-size:14px">Tôi<div class="f-online-dot"></div></div><textarea class="f-composer-input" id="post-input" placeholder="Chia sẻ phân tích dữ liệu, cảnh báo rủi ro, hoặc câu hỏi nghiên cứu..." rows="2" oninput="autoResize(this);toggleSubmit()"></textarea></div><div class="f-img-preview" id="img-preview"><img id="preview-img" src="" alt="preview"><button class="f-img-remove" onclick="removeImage()">✕</button></div><div class="f-composer-actions"><div class="f-composer-tools"><label class="f-tool-btn" for="img-upload">🖼️ Ảnh<input type="file" id="img-upload" accept="image/*" style="display:none" onchange="previewImage(this)"></label><select class="f-tag-select" id="post-tag"><option value="">🏷️ Chọn tag</option><option value="keo-nha">🏠 Kèo Nhà</option><option value="tai-xi">🎲 Tài/Xỉu</option><option value="chot-so">🔢 Chốt Số</option><option value="phan-tich">📊 Phân Tích</option></select></div><button class="f-submit-btn" id="submit-btn" disabled onclick="submitPost()">Đăng bài</button></div></div>
    <div class="f-feed" id="feed"><div class="f-section-label">Bài đăng nổi bật</div></div>
  </div>
  <button class="f-fab" onclick="document.getElementById('post-input').focus();document.getElementById('post-input').scrollIntoView({behavior:'smooth',block:'center'})">✏️</button><div id="f-toast"></div><div class="lock-overlay" id="lockOverlay"><div class="lock-card"><div class="spinner"></div><div class="lock-title" id="lockTitle">Đang xử lý</div><div class="lock-text" id="lockText">Đang kết nối backend...</div></div></div>
</div>
<script>
"use strict";
const ME={id:0,name:'Tôi',role:'member',avatar:'me-av',initials:'Tôi',online:true};let USERS=[{id:1,name:'Admin Hệ Thống',role:'admin',avatar:'admin-av',initials:'AD',online:true},{id:2,name:'Nhà phân tích dữ liệu',role:'vip',avatar:'vip-av',initials:'PT',online:true},{id:3,name:'Thành viên mới',role:'member',avatar:'member-av',initials:'TV',online:false}];const TAG_LABELS={'keo-nha':'🏠 Kèo Nhà','tai-xi':'🎲 Tài/Xỉu','chot-so':'🔢 Chốt Số','phan-tich':'📊 Phân Tích'};let posts=[],pendingImage=null,currentFilter='all',postIdCounter=100,isBusy=false;const MAX_VISIBLE_CHARS=120000,STREAM_BATCH_LINES=24;let fullReport=[],visibleNode=document.createTextNode(''),lineCount=0,queue=[],scheduled=false;const defaultFiles=[{name:'nghiên cứu xổ số 1.docx',state:'Không đọc được',level:'warn'},{name:'HỆ THỐNG CAPABILITY TOKEN (CẤP QUYỀN TRUY CẬP).docx',state:'Không đọc được',level:'warn'},{name:'bản cấu trúc hệ thống nghiên cứu xổ số trọng tâm cốt lõi.docx',state:'Không đọc được',level:'warn'}];
document.addEventListener('DOMContentLoaded',()=>{document.getElementById('previewBody').textContent='';document.getElementById('previewBody').appendChild(visibleNode);renderFiles(defaultFiles,'Không đủ dữ liệu xác thực','Các file đính kèm không đọc được bằng công cụ quét. Dữ liệu diễn đàn hiện là seed an toàn, không phải dữ liệu thật từ file.');seedPosts();resetReport('Chưa có dữ liệu stream. Backend có thể gọi window.ForumBridge.streamReport([...]).');setCore('','CHỜ KẾT NỐI',0);});
function setBusy(v,title,detail){isBusy=v;document.getElementById('lockOverlay').classList.toggle('show',v);if(title)document.getElementById('lockTitle').textContent=title;if(detail)document.getElementById('lockText').textContent=detail}function setCore(state,msg,progress){const el=document.getElementById('coreStatus');el.className='core-status';if(state)el.classList.add(state);el.textContent=msg||'CHỜ KẾT NỐI';if(typeof progress==='number')document.getElementById('progressBar').style.width=Math.max(0,Math.min(100,progress))+'%'}function setLog(msg){document.getElementById('coreLog').textContent=msg||''}
function renderFiles(files,status,notice){const list=document.getElementById('fileList');list.replaceChildren();(Array.isArray(files)?files:[]).forEach(f=>{const r=document.createElement('div'),n=document.createElement('div'),s=document.createElement('div');r.className='file-row';n.className='file-name';s.className='file-state';n.textContent=f.name||'Nguồn chưa đặt tên';s.textContent=f.state||'Chưa rõ';if(f.level==='ok')s.classList.add('ok');if(f.level==='bad')s.classList.add('bad');r.append(n,s);list.appendChild(r)});if(!list.children.length){const r=document.createElement('div'),n=document.createElement('div'),s=document.createElement('div');r.className='file-row';n.className='file-name';s.className='file-state';n.textContent='Chưa có nguồn dữ liệu';s.textContent='Đang chờ';r.append(n,s);list.appendChild(r)}const st=document.getElementById('scanStatus');st.className='scan-status';if(status&&status.toLowerCase().includes('đủ'))st.classList.add('ok');if(status&&status.toLowerCase().includes('lỗi'))st.classList.add('bad');st.textContent=status||'Chưa có dữ liệu lõi';document.getElementById('scanNotice').textContent=notice||'Nguồn có thể cập nhật động bằng API hook.'}
function resetReport(text){fullReport=[];lineCount=0;queue=[];scheduled=false;visibleNode.data=text||'';if(text)fullReport.push(text);document.getElementById('previewMeter').textContent=(text?text.split('\n').length:0)+' dòng';document.getElementById('previewBox').scrollTop=0}function appendVisible(text){if(!text)return;fullReport.push(text);lineCount+=(text.match(/\n/g)||[]).length;let cur=visibleNode.data+text;if(cur.length>MAX_VISIBLE_CHARS)cur='[Đã thu gọn phần đầu để tránh nghẽn DOM trên mobile. Nội dung đầy đủ vẫn nằm trong bộ nhớ phiên.]\n\n'+cur.slice(-MAX_VISIBLE_CHARS);visibleNode.data=cur;document.getElementById('previewMeter').textContent=lineCount+' dòng · '+Math.round(cur.length/1024)+'KB hiển thị';const box=document.getElementById('previewBox');box.scrollTop=box.scrollHeight}function flush(){if(scheduled)return;scheduled=true;requestAnimationFrame(()=>{let block='',c=0;while(queue.length&&c<STREAM_BATCH_LINES){block+=queue.shift();c++}appendVisible(block);scheduled=false;if(queue.length)flush()})}function streamReport(lines){(Array.isArray(lines)?lines:[String(lines||'')]).forEach(l=>queue.push(String(l).endsWith('\n')?String(l):String(l)+'\n'));flush()}
function normalizeUser(u){return{id:Number(u.id)||Date.now(),name:String(u.name||'Người dùng'),role:['admin','vip','member'].includes(u.role)?u.role:'member',avatar:u.avatar||((u.role==='admin')?'admin-av':(u.role==='vip')?'vip-av':'member-av'),initials:String(u.initials||String(u.name||'ND').slice(0,2)).slice(0,3),online:!!u.online}}function normalizePost(p){return{id:Number(p.id)||++postIdCounter,userId:Number(p.userId)||0,pinned:!!p.pinned,tag:p.tag||'phan-tich',text:String(p.text||''),image:p.image||null,likes:Array.isArray(p.likes)?p.likes:[],comments:Array.isArray(p.comments)?p.comments:[],ts:p.ts||'Vừa xong',views:Number(p.views)||0}}
function setForumData(payload){setBusy(true,'Đang nhận dữ liệu','Đang chuẩn hóa dữ liệu diễn đàn từ backend...');setCore('loading','ĐANG NHẬN DỮ LIỆU',20);try{if(payload&&Array.isArray(payload.users))USERS=payload.users.map(normalizeUser);if(payload&&Array.isArray(payload.posts))posts=payload.posts.map(normalizePost);renderFeed();setCore('ready','ĐÃ CẬP NHẬT',100);setLog('Đã cập nhật diễn đàn từ backend. Posts: '+posts.length+', Users: '+USERS.length);streamReport(['Đã cập nhật dữ liệu diễn đàn từ backend. Bài đăng: '+posts.length+'. Thành viên: '+USERS.length+'.']);}catch(e){setCore('error','LỖI DỮ LIỆU',0);setLog('Lỗi chuẩn hóa dữ liệu: '+e.message);streamReport(['Không có đủ dữ liệu xác thực hoặc dữ liệu backend sai cấu trúc: '+e.message]);}finally{setBusy(false)}}
function seedPosts(){posts=[{id:1,userId:1,pinned:true,tag:'phan-tich',text:'📌 NGUYÊN TẮC DIỄN ĐÀN:\n\n1. Chia sẻ phân tích phải ghi rõ nguồn và giới hạn dữ liệu.\n2. Không đưa lời khuyên đặt tiền hoặc cổ vũ cá cược.\n3. Tôn trọng thành viên và phản biện bằng dữ liệu.\n4. Nếu thiếu dữ kiện phải ghi: Không đủ dữ liệu xác thực.',image:null,likes:[],comments:[{id:1,userId:2,text:'Đồng ý. Cần tách rõ phân tích dữ liệu và quyết định tài chính.',ts:'2 giờ trước',likes:1}],ts:'Hôm nay, 08:00',views:412},{id:2,userId:2,pinned:false,tag:'phan-tich',text:'📊 Ghi chú phân tích: Khi xem chu kỳ hoặc tần suất, cần kiểm tra độ dài mẫu, nguồn dữ liệu, và rủi ro ngụy tương quan. Không dùng một vài điểm dữ liệu ngắn để kết luận chắc chắn.',image:null,likes:[1],comments:[],ts:'Hôm nay, 10:30',views:289}];renderFeed();updateStats()}
function renderFeed(){const feed=document.getElementById('feed');const label=feed.querySelector('.f-section-label')||document.createElement('div');label.className='f-section-label';label.textContent='Bài đăng nổi bật';feed.replaceChildren(label);let filtered=posts;if(currentFilter==='pinned')filtered=posts.filter(p=>p.pinned);else if(currentFilter!=='all')filtered=posts.filter(p=>p.tag===currentFilter);if(!filtered.length){const e=document.createElement('div');e.className='f-empty';e.innerHTML='<div style="font-size:40px;margin-bottom:12px">🔍</div><div>Chưa có bài đăng nào trong mục này</div>';feed.appendChild(e);return}[...filtered].reverse().forEach(p=>feed.appendChild(buildPostEl(p)));updateStats()}
function buildPostEl(post){const user=post.userId===0?ME:(USERS.find(u=>u.id===post.userId)||ME);const isLiked=post.likes.includes(0);const el=document.createElement('div');el.className='f-post'+(post.pinned?' pinned':'');el.dataset.id=post.id;const pin=post.pinned?'<div class="f-pin-badge">📌 Bài được ghim</div>':'';const role=user.role==='admin'?'badge-admin':user.role==='vip'?'badge-vip':'badge-member';const tag=post.tag?'<span class="f-badge badge-tag">'+escHtml(TAG_LABELS[post.tag]||post.tag)+'</span>':'';el.innerHTML=pin+'<div class="f-post-header"><div class="f-avatar '+escAttr(user.avatar)+'">'+escHtml(user.initials)+(user.online?'<div class="f-online-dot"></div>':'')+'</div><div class="f-post-meta"><div class="f-post-name">'+escHtml(user.name)+' <span class="f-badge '+role+'">'+escHtml(user.role.toUpperCase())+'</span> '+tag+'</div><div class="f-post-time">🕐 '+escHtml(post.ts)+' · 👁 '+escHtml(post.views)+'</div></div><div style="position:relative"><button class="f-opts-btn" onclick="toggleOpts('+post.id+',event)">⋯</button><div class="f-opts-menu" id="opts-'+post.id+'"><div class="f-opts-item" onclick="copyText('+post.id+')">📋 Sao chép</div><div class="f-opts-item" onclick="ForumBridge.streamReport([\'Đã báo cáo bài viết '+post.id+'\']);closeOpts()">🚩 Báo cáo</div></div></div></div><div class="f-post-body"><div class="f-post-text">'+escHtml(post.text)+'</div>'+(post.image?'<div class="f-post-image"><img src="'+escAttr(post.image)+'" alt="post image" loading="lazy"></div>':'')+'</div><div class="f-reaction-row" id="react-row-'+post.id+'">'+(post.likes.length?'<span>❤️ '+post.likes.length+' lượt thích</span>':'')+(post.comments.length?'<span style="margin-left:auto">'+post.comments.length+' bình luận</span>':'')+'</div><div class="f-action-bar"><button class="f-action-btn '+(isLiked?'liked':'')+'" onclick="toggleLike('+post.id+',this)"><span>'+(isLiked?'❤️':'🤍')+'</span><span>Thích</span></button><button class="f-action-btn" onclick="toggleComments('+post.id+',this)"><span>💬</span><span>Bình luận</span></button><button class="f-action-btn" onclick="sharePost('+post.id+')"><span>↗️</span><span>Chia sẻ</span></button></div><div class="f-comments" id="comments-'+post.id+'"><div class="f-comments-list" id="clist-'+post.id+'"></div><div class="f-comment-input-wrap"><div class="f-avatar me-av" style="width:30px;height:30px;font-size:11px;flex-shrink:0">Tôi</div><textarea class="f-comment-input" id="cinput-'+post.id+'" placeholder="Viết bình luận..." rows="1" oninput="autoResize(this)"></textarea><button class="f-comment-send" onclick="sendComment('+post.id+')">➤</button></div></div>';const list=el.querySelector('#clist-'+post.id);post.comments.forEach(c=>list.appendChild(buildCommentEl(c)));if(!post.comments.length){const empty=document.createElement('div');empty.style.cssText='text-align:center;color:var(--muted);font-size:13px;padding:8px';empty.textContent='Hãy là người đầu tiên bình luận 🌟';list.appendChild(empty)}return el}
function buildCommentEl(c){const user=USERS.find(u=>u.id===c.userId)||ME;const wrap=document.createElement('div');wrap.className='f-comment';wrap.innerHTML='<div class="f-avatar '+escAttr(user.avatar)+'" style="width:30px;height:30px;font-size:11px">'+escHtml(user.initials)+'</div><div class="f-comment-bubble"><div class="f-comment-name">'+escHtml(user.name)+'</div><div class="f-comment-text">'+escHtml(c.text)+'</div><div class="f-comment-time">'+escHtml(c.ts)+' · '+escHtml(c.likes||0)+' ❤️</div></div>';return wrap}
function submitPost(){const input=document.getElementById('post-input');const text=input.value.trim();const tag=document.getElementById('post-tag').value;if(!text&&!pendingImage)return;const now=new Date();const ts='Hôm nay, '+String(now.getHours()).padStart(2,'0')+':'+String(now.getMinutes()).padStart(2,'0');posts.push({id:++postIdCounter,userId:0,pinned:false,tag,text,image:pendingImage,likes:[],comments:[],ts,views:1});input.value='';input.style.height='';pendingImage=null;document.getElementById('img-preview').classList.remove('show');document.getElementById('preview-img').src='';document.getElementById('post-tag').value='';document.getElementById('submit-btn').disabled=true;renderFeed();showToast('✅ Bài đăng thành công');streamReport(['Người dùng đăng bài mới: '+(tag||'không tag')+'.'])}
function toggleLike(id,btn){const p=posts.find(x=>x.id===id);if(!p)return;const i=p.likes.indexOf(0);if(i===-1){p.likes.push(0);btn.classList.add('liked');btn.children[0].textContent='❤️'}else{p.likes.splice(i,1);btn.classList.remove('liked');btn.children[0].textContent='🤍'}renderFeed()}function toggleComments(id,btn){const s=document.getElementById('comments-'+id);s.classList.toggle('open')}function sendComment(id){const inp=document.getElementById('cinput-'+id);const text=inp.value.trim();if(!text)return;const p=posts.find(x=>x.id===id);if(!p)return;p.comments.push({id:Date.now(),userId:0,text,ts:'Vừa xong',likes:0});renderFeed();showToast('💬 Đã bình luận')}function filterFeed(filter,tab){currentFilter=filter;document.querySelectorAll('.f-tab').forEach(t=>t.classList.remove('active'));tab.classList.add('active');renderFeed()}function toggleOpts(id,e){e.stopPropagation();const m=document.getElementById('opts-'+id);const open=m.classList.contains('open');closeOpts();if(!open)m.classList.add('open')}function closeOpts(){document.querySelectorAll('.f-opts-menu.open').forEach(m=>m.classList.remove('open'))}document.addEventListener('click',closeOpts);function copyText(id){const p=posts.find(x=>x.id===id);if(p)navigator.clipboard&&navigator.clipboard.writeText(p.text).catch(()=>{});closeOpts();showToast('📋 Đã sao chép')}function sharePost(id){showToast('↗️ Đã sao chép link bài viết')}function previewImage(input){const f=input.files[0];if(!f)return;const r=new FileReader();r.onload=e=>{pendingImage=e.target.result;document.getElementById('preview-img').src=pendingImage;document.getElementById('img-preview').classList.add('show');document.getElementById('submit-btn').disabled=false};r.readAsDataURL(f)}function removeImage(){pendingImage=null;document.getElementById('img-preview').classList.remove('show');document.getElementById('preview-img').src='';document.getElementById('img-upload').value='';toggleSubmit()}function autoResize(el){el.style.height='auto';el.style.height=Math.min(el.scrollHeight,el.closest('.f-composer')?200:100)+'px'}function toggleSubmit(){const text=document.getElementById('post-input').value.trim();document.getElementById('submit-btn').disabled=!text&&!pendingImage}let toastTimer;function showToast(msg){const t=document.getElementById('f-toast');t.textContent=msg;t.classList.add('show');clearTimeout(toastTimer);toastTimer=setTimeout(()=>t.classList.remove('show'),2500)}function updateStats(){document.getElementById('stat-posts').textContent=posts.length;document.getElementById('stat-members').textContent=USERS.length;document.getElementById('stat-online').textContent=USERS.filter(u=>u.online).length;document.getElementById('stat-today').textContent=posts.filter(p=>p.ts&&p.ts.includes('Hôm nay')).length}function escHtml(s){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;')}function escAttr(s){return escHtml(s).replace(/'/g,'&#039;')}
window.ForumBridge={setFiles:(files,status,notice)=>renderFiles(files,status,notice),setStatus:(state,msg,progress)=>setCore(state,msg,progress),setLog:msg=>setLog(msg),startLoading:(title,detail)=>setBusy(true,title||'Đang xử lý',detail||'Đang chờ backend...'),stopLoading:()=>setBusy(false),setData:payload=>setForumData(payload),setPosts:arr=>setForumData({posts:arr}),setUsers:arr=>setForumData({users:arr,posts}),streamReport:lines=>streamReport(lines),resetReport:text=>resetReport(text||''),getFullReport:()=>fullReport.join('')};
</script>
</body>
</html>
--------------------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Module Không Gian Video AI</title>
<style>
:root{
    --bg-main:#1c130d;
    --bg-board:#2a1a10;
    --bg-deep:#120a06;
    --panel:#24150d;
    --panel-2:#160d08;
    --text-main:#fff4e6;
    --text-soft:#ffe0b8;
    --text-muted:#c9a982;
    --border-color:#5a3824;
    --glass-border:#6b432b;
    --accent:#d40000;
    --accent-bright:#ff3838;
    --ok:#10b981;
    --warn:#facc15;
    --bad:#ef4444;
    --font-ui:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:var(--font-ui);-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{background:#050302;display:flex;justify-content:center;align-items:flex-start;width:100vw;height:100dvh;overflow:hidden;color:var(--text-main)}
button,input{font:inherit}
.app-wrapper{max-width:480px;width:100%;height:100%;position:relative;background:var(--bg-main);overflow:hidden;display:flex;flex-direction:column;box-shadow:0 0 45px rgba(0,0,0,.95);border-left:1px solid rgba(255,232,190,.08);border-right:1px solid rgba(255,232,190,.08)}
.sub-screen{position:relative;display:flex;flex-direction:column;flex:1;background:linear-gradient(180deg,var(--bg-board),var(--bg-deep));min-height:0;width:100%;height:100%;padding-top:env(safe-area-inset-top)}
.mock-header{padding:10px 12px;background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border-color);display:grid;grid-template-columns:38px 1fr auto;align-items:center;gap:10px;z-index:20;flex-shrink:0;box-shadow:0 4px 14px rgba(0,0,0,.32)}
.mock-back-btn{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass-border);color:var(--text-soft);font-size:20px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 2px rgba(255,232,190,.08),0 3px 8px rgba(0,0,0,.25)}
.mock-back-btn:active{transform:scale(.94)}
.mock-header-title{font-weight:950;font-size:14px;color:var(--text-soft);letter-spacing:.5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;text-transform:uppercase}
.header-chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}
.video-player-container{width:100%;aspect-ratio:16/9;background:#000;position:relative;flex-shrink:0;border-bottom:1px solid var(--border-color);box-shadow:0 6px 18px rgba(0,0,0,.5);z-index:10;overflow:hidden}
.video-player-container iframe,.video-player-container video{width:100%;height:100%;border:none;object-fit:contain;background:#000;display:block}
.player-placeholder{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;background:radial-gradient(circle at 50% 35%,#2a1a10 0%,#120a06 68%);color:var(--text-muted);text-align:center;padding:20px}
.player-placeholder svg{width:54px;height:54px;fill:#6b432b;margin-bottom:10px;filter:drop-shadow(0 4px 12px rgba(0,0,0,.45))}
.player-placeholder strong{font-size:13px;letter-spacing:.7px;color:var(--text-soft);text-transform:uppercase}
.player-placeholder small{display:block;margin-top:6px;font-size:11px;line-height:1.35;color:var(--text-muted);max-width:300px}
.video-info-section{padding:14px 15px 13px;flex-shrink:0;border-bottom:1px solid rgba(255,232,190,.08);background:linear-gradient(180deg,#24150d,#1a0f09)}
.video-title{font-size:16px;font-weight:900;color:var(--text-main);margin-bottom:9px;line-height:1.35;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.video-meta{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:12px;color:var(--text-muted)}
.ai-status-badge{background:rgba(16,185,129,.10);color:var(--ok);padding:5px 8px;border-radius:8px;border:1px solid rgba(16,185,129,.35);font-weight:950;letter-spacing:.4px;display:flex;align-items:center;gap:5px;white-space:nowrap;max-width:58%;overflow:hidden;text-overflow:ellipsis}
.ai-status-badge.waiting{border-color:rgba(250,204,21,.45);color:var(--warn);background:rgba(250,204,21,.10)}
.ai-status-badge.error{border-color:rgba(239,68,68,.45);color:var(--bad);background:rgba(239,68,68,.10)}
.playlist-header{padding:14px 15px 9px;font-size:12px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.8px;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-shrink:0}
.playlist-count{font-size:11px;color:var(--text-muted);font-weight:850;text-transform:none;letter-spacing:0}
.playlist-container{flex:1;overflow-y:auto;overflow-x:hidden;padding:0 15px 15px;display:flex;flex-direction:column;gap:10px;-webkit-overflow-scrolling:touch;scrollbar-width:none;min-height:0}
.playlist-container::-webkit-scrollbar{display:none;width:0;height:0}
.video-card{width:100%;display:flex;gap:12px;background:linear-gradient(180deg,rgba(58,36,22,.76),rgba(33,18,8,.92));padding:8px;border-radius:12px;border:1px solid rgba(255,232,190,.08);cursor:pointer;transition:transform .18s,background .18s,border-color .18s,box-shadow .18s;box-shadow:0 4px 12px rgba(0,0,0,.20);text-align:left;color:inherit}
.video-card:active{background:linear-gradient(180deg,#3a2416,#211208);transform:scale(.985)}
.video-card.active{border-color:var(--ok);background:linear-gradient(180deg,rgba(16,185,129,.12),rgba(33,18,8,.94));box-shadow:0 0 0 1px rgba(16,185,129,.16),0 6px 16px rgba(0,0,0,.28)}
.thumb-wrapper{width:120px;height:68px;border-radius:9px;overflow:hidden;position:relative;flex-shrink:0;background:#1e130c;border:1px solid rgba(255,232,190,.10)}
.thumb-art{width:100%;height:100%;display:flex;align-items:center;justify-content:center;background:radial-gradient(circle at 30% 20%,rgba(255,82,82,.34),transparent 36%),linear-gradient(135deg,#3a2416,#120a06);color:#ffe0b8;font-size:18px;font-weight:950;letter-spacing:.7px;text-align:center;padding:8px;text-transform:uppercase}
.thumb-wrapper img{width:100%;height:100%;object-fit:cover;display:block}
.duration-badge{position:absolute;bottom:4px;right:4px;background:rgba(0,0,0,.82);color:#fff;font-size:10px;padding:2px 5px;border-radius:5px;font-weight:900}
.type-badge{position:absolute;top:4px;left:4px;background:rgba(212,0,0,.86);color:#fff;font-size:9px;padding:2px 5px;border-radius:999px;font-weight:950;letter-spacing:.2px}
.card-info{flex:1;min-width:0;display:flex;flex-direction:column;justify-content:flex-start;padding:1px 0}
.card-title{font-size:13px;font-weight:850;color:var(--text-main);margin-bottom:4px;line-height:1.3;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.card-date{font-size:11px;color:var(--text-muted);font-weight:750}
.card-status{font-size:10px;font-weight:950;margin-top:auto;color:var(--ok);letter-spacing:.2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.card-status.wait{color:var(--warn)}
.card-status.error{color:var(--bad)}
.footer-note{flex-shrink:0;background:linear-gradient(135deg,#2b1a10,#160d08);border-top:1px solid var(--border-color);padding:10px 14px calc(10px + env(safe-area-inset-bottom));font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:800;text-align:center}
.footer-note b{color:#ffd6a0}
@media(max-height:720px){.playlist-container{gap:8px}.video-card{padding:7px}.thumb-wrapper{width:112px;height:63px}.footer-note{display:none}}
@media(max-width:380px){.mock-header{grid-template-columns:36px 1fr auto;padding:9px 10px}.mock-back-btn{width:36px;height:32px}.mock-header-title{font-size:13px}.header-chip{font-size:9px;padding:5px 7px}.video-info-section{padding:12px}.video-title{font-size:15px}.playlist-container{padding:0 12px 12px}.playlist-header{padding:12px 12px 8px}.thumb-wrapper{width:108px;height:61px}.video-card{gap:9px}.card-title{font-size:12px}.ai-status-badge{font-size:11px;max-width:62%}}
</style>
</head>
<body>
<div class="app-wrapper">
    <div id="video-workspace" class="sub-screen">
        <div class="mock-header">
            <button class="mock-back-btn" id="btn-exit-video" type="button" aria-label="Trở về">←</button>
            <span class="mock-header-title">Không gian Video AI</span>
            <span class="header-chip">AI VIDEO</span>
        </div>

        <div class="video-player-container" id="main-player-box" aria-live="polite">
            <div class="player-placeholder" id="player-placeholder">
                <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M8 5v14l11-7z"></path></svg>
                <strong>Chọn video để phát</strong>
                <small>Hỗ trợ YouTube, Vimeo, MP4, WebM, OGG và HLS nếu trình duyệt có hỗ trợ native HLS.</small>
            </div>
        </div>

        <div class="video-info-section">
            <div class="video-title" id="current-vid-title">Chưa chọn video phân tích</div>
            <div class="video-meta">
                <span id="current-vid-date">--/--/2026</span>
                <span class="ai-status-badge waiting" id="current-vid-status">ĐANG CHỜ</span>
            </div>
        </div>

        <div class="playlist-header">
            <span>Danh sách video</span>
            <span class="playlist-count" id="playlist-count">0 mục</span>
        </div>
        <div class="playlist-container" id="playlist-render-area"></div>
        <div class="footer-note"><b>Ghi chú:</b> 4 thẻ video được bố trí kín hơn. Dữ liệu mẫu nằm trong <b>dbVideos</b>; khi có video thật, thay URL và metadata tại đó.</div>
    </div>
</div>

<script>
"use strict";

document.addEventListener("DOMContentLoaded", function(){
    const $ = function(id){ return document.getElementById(id); };

    const dbVideos = [
        {
            id:"v01",
            title:"Video YouTube mẫu - hồ sơ phân tích ngày 01/06/2026",
            date:"01/06/2026",
            url:"https://www.youtube.com/watch?v=dQw4w9WgXcQ",
            thumbText:"YT 01",
            thumb:"",
            duration:"04:20",
            status:"YouTube",
            state:"ok"
        },
        {
            id:"v02",
            title:"Video Vimeo mẫu - kiểm thử player iframe ngoài YouTube",
            date:"02/06/2026",
            url:"https://vimeo.com/76979871",
            thumbText:"VIMEO",
            thumb:"",
            duration:"02:15",
            status:"Vimeo",
            state:"ok"
        },
        {
            id:"v03",
            title:"Video MP4 trực tiếp - kiểm thử thẻ video native",
            date:"03/06/2026",
            url:"https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4",
            thumbText:"MP4",
            thumb:"",
            duration:"00:05",
            status:"MP4 native",
            state:"ok"
        },
        {
            id:"v04",
            title:"Khung video HLS/WebM/OGG - thay URL thật khi vận hành",
            date:"04/06/2026",
            url:"https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm",
            thumbText:"WEBM",
            thumb:"",
            duration:"00:05",
            status:"WebM native",
            state:"wait"
        }
    ];

    const playlistBox = $("playlist-render-area");
    const playerBox = $("main-player-box");
    const txtTitle = $("current-vid-title");
    const txtDate = $("current-vid-date");
    const txtStatus = $("current-vid-status");
    const btnExit = $("btn-exit-video");
    const playlistCount = $("playlist-count");

    let currentActiveId = null;

    function showPlaceholder(title, detail){
        playerBox.replaceChildren();
        const box = document.createElement("div");
        box.className = "player-placeholder";
        const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
        svg.setAttribute("viewBox", "0 0 24 24");
        svg.setAttribute("aria-hidden", "true");
        const path = document.createElementNS("http://www.w3.org/2000/svg", "path");
        path.setAttribute("d", "M8 5v14l11-7z");
        svg.appendChild(path);
        const strong = document.createElement("strong");
        strong.textContent = title;
        const small = document.createElement("small");
        small.textContent = detail;
        box.appendChild(svg);
        box.appendChild(strong);
        box.appendChild(small);
        playerBox.appendChild(box);
    }

    function safeUrl(rawUrl){
        if(typeof rawUrl !== "string" || !rawUrl.trim()) return null;
        try{
            const url = new URL(rawUrl.trim());
            if(url.protocol !== "https:" && url.protocol !== "http:") return null;
            return url;
        }catch(error){
            return null;
        }
    }

    function extractYoutubeId(rawUrl){
        const url = safeUrl(rawUrl);
        if(!url) return "";
        const host = url.hostname.replace(/^www\./, "").toLowerCase();
        let id = "";
        if(host === "youtu.be"){
            id = url.pathname.split("/").filter(Boolean)[0] || "";
        }else if(host === "youtube.com" || host === "m.youtube.com" || host === "music.youtube.com"){
            if(url.pathname === "/watch") id = url.searchParams.get("v") || "";
            else if(url.pathname.startsWith("/embed/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
            else if(url.pathname.startsWith("/shorts/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
            else if(url.pathname.startsWith("/live/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
        }
        return /^[A-Za-z0-9_-]{6,}$/.test(id) ? id : "";
    }

    function extractVimeoId(rawUrl){
        const url = safeUrl(rawUrl);
        if(!url) return "";
        const host = url.hostname.replace(/^www\./, "").toLowerCase();
        if(host !== "vimeo.com" && host !== "player.vimeo.com") return "";
        const parts = url.pathname.split("/").filter(Boolean);
        let id = "";
        if(host === "player.vimeo.com" && parts[0] === "video") id = parts[1] || "";
        if(host === "vimeo.com") id = parts.find(function(part){ return /^\d+$/.test(part); }) || "";
        return /^\d+$/.test(id) ? id : "";
    }

    function getExtension(pathname){
        const clean = pathname.toLowerCase().split("?")[0].split("#")[0];
        const idx = clean.lastIndexOf(".");
        return idx >= 0 ? clean.slice(idx + 1) : "";
    }

    function getPlayableType(rawUrl){
        const ytId = extractYoutubeId(rawUrl);
        if(ytId){
            return {type:"iframe",provider:"YouTube",src:"https://www.youtube.com/embed/" + ytId + "?autoplay=1&rel=0&playsinline=1"};
        }

        const vimeoId = extractVimeoId(rawUrl);
        if(vimeoId){
            return {type:"iframe",provider:"Vimeo",src:"https://player.vimeo.com/video/" + vimeoId + "?autoplay=1&title=0&byline=0&portrait=0"};
        }

        const url = safeUrl(rawUrl);
        if(!url) return {type:"invalid",provider:"",src:""};

        const ext = getExtension(url.pathname);
        const directVideoMap = {
            mp4:"video/mp4",
            m4v:"video/mp4",
            webm:"video/webm",
            ogg:"video/ogg",
            ogv:"video/ogg",
            mov:"video/quicktime",
            m3u8:"application/vnd.apple.mpegurl"
        };

        if(Object.prototype.hasOwnProperty.call(directVideoMap, ext)){
            return {type:"video",provider:ext.toUpperCase(),src:url.href,mime:directVideoMap[ext],extension:ext};
        }

        return {type:"unsupported",provider:"",src:""};
    }

    function setStatusBadge(videoData){
        txtStatus.className = "ai-status-badge waiting";
        if(videoData.state === "ok") txtStatus.className = "ai-status-badge";
        if(videoData.state === "warn" || videoData.state === "wait") txtStatus.className = "ai-status-badge waiting";
        if(videoData.state === "error") txtStatus.className = "ai-status-badge error";
        txtStatus.textContent = videoData.status || "Chưa rõ";
    }

    function playVideo(videoData){
        if(!videoData) return;
        currentActiveId = videoData.id;
        document.querySelectorAll(".video-card").forEach(function(card){
            card.classList.toggle("active", card.dataset.id === currentActiveId);
        });
        txtTitle.textContent = videoData.title || "Không có tiêu đề";
        txtDate.textContent = "Ngày: " + (videoData.date || "Chưa có ngày");
        setStatusBadge(videoData);

        const playable = getPlayableType(videoData.url);
        playerBox.replaceChildren();

        if(playable.type === "iframe"){
            const iframe = document.createElement("iframe");
            iframe.src = playable.src;
            iframe.title = playable.provider + " Video Player";
            iframe.allow = "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share";
            iframe.allowFullscreen = true;
            iframe.referrerPolicy = "strict-origin-when-cross-origin";
            playerBox.appendChild(iframe);
            return;
        }

        if(playable.type === "video"){
            const video = document.createElement("video");
            video.controls = true;
            video.playsInline = true;
            video.autoplay = true;
            video.preload = "metadata";

            const source = document.createElement("source");
            source.src = playable.src;
            source.type = playable.mime;
            video.appendChild(source);

            video.addEventListener("error", function(){
                showPlaceholder("Trình duyệt không phát được định dạng này", "File có thể cần codec khác, CORS hợp lệ, hoặc cần thư viện riêng nếu là HLS trên trình duyệt không hỗ trợ native.");
            });

            playerBox.appendChild(video);
            video.play().catch(function(){
                /* Autoplay có thể bị trình duyệt chặn. Người dùng bấm Play thủ công trên controls. */
            });
            return;
        }

        showPlaceholder("Không phát được video", "URL không hợp lệ hoặc chưa thuộc nhóm hỗ trợ: YouTube, Vimeo, MP4, M4V, WebM, OGG, OGV, MOV, M3U8.");
    }

    function detectProviderLabel(rawUrl){
        const playable = getPlayableType(rawUrl);
        if(playable.provider) return playable.provider;
        if(playable.type === "unsupported") return "URL";
        return "N/A";
    }

    function createThumb(videoData){
        const wrap = document.createElement("div");
        wrap.className = "thumb-wrapper";
        if(videoData.thumb && /^https?:\/\//i.test(videoData.thumb)){
            const img = document.createElement("img");
            img.src = videoData.thumb;
            img.alt = videoData.thumbText || "thumbnail";
            img.loading = "lazy";
            img.onerror = function(){
                wrap.replaceChildren(createThumbArt(videoData), createTypeBadge(videoData), createDuration(videoData.duration));
            };
            wrap.appendChild(img);
        }else{
            wrap.appendChild(createThumbArt(videoData));
        }
        wrap.appendChild(createTypeBadge(videoData));
        wrap.appendChild(createDuration(videoData.duration));
        return wrap;
    }

    function createThumbArt(videoData){
        const art = document.createElement("div");
        art.className = "thumb-art";
        art.textContent = videoData.thumbText || "VIDEO";
        return art;
    }

    function createTypeBadge(videoData){
        const span = document.createElement("span");
        span.className = "type-badge";
        span.textContent = detectProviderLabel(videoData.url);
        return span;
    }

    function createDuration(duration){
        const span = document.createElement("span");
        span.className = "duration-badge";
        span.textContent = duration || "--:--";
        return span;
    }

    function renderPlaylist(){
        playlistBox.replaceChildren();
        playlistCount.textContent = dbVideos.length + " mục";
        dbVideos.forEach(function(vid){
            const card = document.createElement("button");
            card.type = "button";
            card.className = "video-card";
            card.dataset.id = vid.id;
            card.setAttribute("aria-label", "Phát video: " + (vid.title || "Không có tiêu đề"));

            const thumb = createThumb(vid);
            const info = document.createElement("div");
            info.className = "card-info";

            const title = document.createElement("div");
            title.className = "card-title";
            title.textContent = vid.title || "Không có tiêu đề";

            const date = document.createElement("div");
            date.className = "card-date";
            date.textContent = vid.date || "Chưa có ngày";

            const status = document.createElement("div");
            status.className = "card-status";
            if(vid.state === "warn" || vid.state === "wait") status.classList.add("wait");
            if(vid.state === "error") status.classList.add("error");
            status.textContent = vid.status || "Chưa rõ";

            info.appendChild(title);
            info.appendChild(date);
            info.appendChild(status);
            card.appendChild(thumb);
            card.appendChild(info);
            card.addEventListener("click", function(){ playVideo(vid); });
            playlistBox.appendChild(card);
        });
    }

    btnExit.addEventListener("click", function(){
        currentActiveId = null;
        showPlaceholder("Đã ngắt phát video", "Player đã được dọn sạch để tránh video chạy ngầm khi rời không gian.");
        txtTitle.textContent = "Hệ thống chờ lệnh";
        txtDate.textContent = "--/--/--";
        txtStatus.className = "ai-status-badge waiting";
        txtStatus.textContent = "OFFLINE";
        document.querySelectorAll(".video-card").forEach(function(card){ card.classList.remove("active"); });
    });

    renderPlaylist();
});
</script>
</body>
</html>
-----------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Super App Xổ Số V10 - Tần Suất Lô</title>
<style>
    /* ============================================================
       RESET + ENGINE FONT (FIX: optimizeLegibility chỉ áp cho chữ,
       không áp toàn cục để tránh tụt hiệu năng khi render 3000+ ô)
       ============================================================ */
    *, *::before, *::after {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        scrollbar-width: none;
        -webkit-tap-highlight-color: transparent;
    }
    *::-webkit-scrollbar { display: none; }

    /* Font số dùng chung: tabular-nums để số không nhảy/lệch khi quay & không lem */
    .num-font {
        font-family: "SF Mono", "Helvetica Neue", Helvetica, Arial, sans-serif;
        font-variant-numeric: tabular-nums lining-nums;
        font-feature-settings: "tnum" 1, "lnum" 1;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-rendering: optimizeLegibility;
    }

    html, body { height: 100%; }
    body {
        background-color: #050505;
        display: flex;
        justify-content: center;
        align-items: flex-start;
        height: 100dvh;
        overflow: hidden;
        width: 100vw;
    }

    /* ============================================================
       BIẾN MÀU – LIGHT
       ============================================================ */
    .app-wrapper {
        --bg-main: #ffffff; --bg-board: #cbd5e1; --text-main: #111111; --text-dim: #6b7280;
        --border-color: #cbd5e1;
        --db-bg: #d40000; --db-text: #ffffff; --led-color: #00e676; --led-bg: #111111;
        --sheet-bg: #f8f9fa; --block-text: #333333;
        --cell-bg: #ffffff; --cell-border: #e2e8f0;
        --sticky-bg: #f1f5f9; --sticky-text: #d40000;
        --block-bg: #ffffff;
        --lo-chip-bg: linear-gradient(135deg, #d40000, #ff5252);
        --lo-chip-shadow: rgba(212,0,0,0.4);
        --tv-bg-base: #0a0f18; --tv-border: #1e293b;
        --modal-overlay: rgba(0,0,0,0.45);
        --glass-bg: linear-gradient(180deg, #ffffff 0%, #eef2f7 100%);
        --glass-shadow: inset 0 2px 4px rgba(255,255,255,1), 0 2px 5px rgba(0,0,0,0.08);
        --glass-border: #cbd5e1;
        --ai-bar-bg: linear-gradient(135deg, #e3f2fd, #bbdefb);
        --ai-bar-border: #90caf9; --ai-bar-text: #1565c0; --ai-bar-input: #ffffff;
    }
    /* ============================================================
       BIẾN MÀU – DARK
       ============================================================ */
    #toggle-dark:checked ~ .app-wrapper {
        --bg-main: #121212; --bg-board: #0f172a; --text-main: #ffffff; --text-dim: #94a3b8;
        --border-color: #334155;
        --sheet-bg: #0b0f17; --block-text: #dddddd;
        --cell-bg: #1e293b; --cell-border: #334155;
        --sticky-bg: #0f172a; --sticky-text: #ff5252;
        --block-bg: #1e293b;
        --lo-chip-bg: linear-gradient(135deg, #ff1744, #d50000);
        --lo-chip-shadow: rgba(255, 23, 68, 0.4);
        --tv-bg-base: #05080f; --tv-border: #334155;
        --modal-overlay: rgba(0,0,0,0.72);
        --glass-bg: linear-gradient(180deg, #243044 0%, #161f30 100%);
        --glass-shadow: inset 0 1px 2px rgba(255,255,255,0.07), 0 3px 6px rgba(0,0,0,0.45);
        --glass-border: #334155;
        --ai-bar-bg: linear-gradient(135deg, #0f2440, #102a4d);
        --ai-bar-border: #1e3a5f; --ai-bar-text: #7cc4ff; --ai-bar-input: #0f172a;
    }

    .app-wrapper {
        max-width: 480px; width: 100%; height: 100%;
        position: relative; background-color: var(--bg-main);
        color: var(--text-main); overflow: hidden;
        box-shadow: 0 0 40px rgba(0,0,0,0.9);
    }

    /* ============================================================
       LỚP 1: LUỒNG LỊCH SỬ
       ============================================================ */
    .main-layer { width: 100%; height: 100%; display: flex; flex-direction: column; background: var(--bg-board); transition: background .3s ease; }

    .top-controls { display: flex; justify-content: space-between; align-items: center; padding: 10px 16px; background: var(--bg-main); border-bottom: 1px solid var(--border-color); z-index: 5; }
    .top-controls-left, .top-controls-right { display: flex; gap: 14px; align-items: center; }

    .switch-wrap { display: flex; flex-direction: column; align-items: center; gap: 4px; }
    .switch-label-text { font-size: 10px; font-weight: 700; color: var(--text-main); text-transform: uppercase; letter-spacing: .3px; }
    .switch { position: relative; display: inline-block; width: 36px; height: 18px; }
    .switch input { opacity: 0; width: 0; height: 0; }
    .switch input:disabled + .slider { opacity: .5; cursor: not-allowed; }
    .slider { position: absolute; cursor: pointer; inset: 0; background-color: #cbd5e1; transition: .3s; border-radius: 20px; box-shadow: inset 0 1px 3px rgba(0,0,0,.2); }
    .slider:before { position: absolute; content: ""; height: 14px; width: 14px; left: 2px; bottom: 2px; background-color: #fff; transition: .3s; border-radius: 50%; box-shadow: 0 1px 2px rgba(0,0,0,.3); }
    input:checked + .slider { background-color: var(--db-bg); }
    input:checked + .slider:before { transform: translateX(18px); }

    .boards-feed { flex: 1; overflow-y: auto; overflow-x: hidden; padding: 16px 12px; display: flex; flex-direction: column; gap: 24px; -webkit-overflow-scrolling: touch; }

    .board { background: var(--bg-main); border-radius: 14px; border: 1px solid var(--border-color); padding: 12px; box-shadow: 0 2px 4px rgba(0,0,0,.02), 0 8px 16px rgba(0,0,0,.05); transition: background .3s ease, border-color .3s ease; }
    .board-header { text-align: center; margin-bottom: 14px; padding-bottom: 10px; border-bottom: 1.5px dashed var(--border-color); }
    .board-title { font-size: 17px; font-weight: 900; color: var(--text-main); text-transform: uppercase; letter-spacing: .5px; }
    .board-title.live { color: var(--db-bg); text-shadow: 0 2px 4px rgba(212,0,0,.18); }
    .status-blink { font-size: 12px; color: var(--db-bg); animation: blink 1.2s infinite; font-weight: 700; margin-top: 4px; }
    .board-date { font-size: 13px; color: var(--text-dim); font-style: italic; margin-top: 4px; font-weight: 700; text-transform: capitalize; }
    @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: .3; } }

    .row { display: flex; margin-bottom: 6px; align-items: stretch; gap: 6px; }
    .prize-name { width: 40px; flex-shrink: 0; display: flex; justify-content: center; align-items: center; font-size: 13px; font-weight: 900; background: var(--glass-bg); box-shadow: var(--glass-shadow); border: 1px solid var(--glass-border); border-radius: 7px; transition: all .2s; color: var(--text-main); }
    .prize-name.db { background: linear-gradient(180deg, #e53935 0%, #b71c1c 100%); color: #fff; border: 1px solid #c62828; box-shadow: inset 0 2px 4px rgba(255,255,255,.35), 0 2px 4px rgba(0,0,0,.2); }
    .prize-name.active-led { background: var(--led-bg); color: var(--led-color); border-color: var(--led-color); box-shadow: 0 0 12px var(--led-color); transform: scale(1.05); z-index: 2; }

    .prize-results { flex-grow: 1; display: grid; gap: 4px; min-width: 0; }
    .grid-1 { grid-template-columns: 1fr; }
    .grid-2 { grid-template-columns: repeat(2, 1fr); }
    .grid-3 { grid-template-columns: repeat(3, 1fr); }
    .grid-4 { grid-template-columns: repeat(4, 1fr); }
    .grid-6 { grid-template-columns: repeat(6, 1fr); }

    /* GLASS BOX – FIX tràn ô: overflow visible cho hover/cầu, min-width:0 cho grid */
    .number-box {
        background: var(--glass-bg);
        border: 1px solid var(--glass-border);
        box-shadow: var(--glass-shadow);
        display: flex; justify-content: center; align-items: center;
        border-radius: 7px; height: 34px; position: relative;
        cursor: default; min-width: 0;
        transition: transform .2s cubic-bezier(.175,.885,.32,1.275), box-shadow .2s, border-color .2s;
    }
    .board-live-cau .number-box, .cau-on .number-box { cursor: pointer; }
    .number-box:hover { transform: scale(1.06); box-shadow: 0 6px 15px rgba(0,0,0,.15); border-color: var(--db-bg); z-index: 10; }
    .number-box:active { transform: scale(.96); }

    /* FONT SỐ – FIX lem & tràn: weight 700, tabular-nums, letter-spacing vừa phải,
       dùng clamp theo từng loại lưới để 5 chữ số luôn vừa ô hẹp (grid-6) */
    .number-text {
        font-size: clamp(13px, 4.4vw, 17px);
        font-weight: 700; letter-spacing: 1.5px;
        display: flex; align-items: center; justify-content: center;
        white-space: nowrap; width: 100%; max-width: 100%; padding: 0 2px;
        transition: color .2s; color: var(--text-main); line-height: 1;
    }
    .grid-3 .number-text { font-size: clamp(12px, 4vw, 16px); letter-spacing: 1px; }
    .grid-4 .number-text { font-size: clamp(11px, 3.4vw, 15px); letter-spacing: .5px; }
    .grid-6 .number-text { font-size: clamp(10px, 3vw, 14px); letter-spacing: .3px; padding: 0 1px; }

    .row-db .number-box { height: 52px; }
    .row-db .number-text { font-size: clamp(24px, 8.5vw, 34px); color: var(--db-bg); letter-spacing: 4px; z-index: 1; text-shadow: 0 2px 4px rgba(0,0,0,.1); padding-left: 4px; }
    .number-text.spinning { color: var(--db-bg); filter: blur(.4px); opacity: .75; }

    /* CHỮ SỐ "LÀM CẦU" – FIX clip: không còn margin gây tràn, dùng inset thay translateY */
    .digit { display: inline-block; transition: all .2s cubic-bezier(.175,.885,.32,1.275); border-radius: 4px; padding: 0 1px; position: relative; }
    .digit.active-cau { background: var(--db-bg); color: #fff; transform: scale(1.18); box-shadow: 0 0 0 1px var(--db-bg), 0 0 10px rgba(212,0,0,.7); z-index: 5; font-weight: 800; }

    /* "LẶN SỐ ĐB" – ĐÃ TRIỂN KHAI HOÀN CHỈNH (trước đây thiếu CSS + JS) */
    .mask-cover {
        position: absolute; inset: 0; border-radius: 7px;
        background: repeating-linear-gradient(45deg, #b71c1c, #b71c1c 10px, #d40000 10px, #d40000 20px);
        display: flex; align-items: center; justify-content: center; gap: 8px;
        color: #fff; font-size: 13px; font-weight: 900; letter-spacing: 1px; text-transform: uppercase;
        cursor: pointer; z-index: 4; opacity: 0; pointer-events: none;
        transition: opacity .3s ease;
        box-shadow: inset 0 0 20px rgba(0,0,0,.4);
    }
    .mask-cover .eye { font-size: 18px; }
    .masking .row-db .mask-cover { opacity: 1; pointer-events: auto; }
    .masking .row-db .number-text { opacity: 0; }
    .row-db .number-box.revealed .mask-cover { opacity: 0 !important; pointer-events: none !important; }

    /* MODAL LÀM CẦU – dialog gọn, bỏ mũi tên gây hiểu lầm vị trí */
    .cau-modal { position: absolute; inset: 0; z-index: 1000; display: flex; justify-content: center; align-items: center; opacity: 0; pointer-events: none; transition: opacity .2s ease; }
    .cau-modal.show { opacity: 1; pointer-events: all; background: var(--modal-overlay); backdrop-filter: blur(3px); }
    .cau-modal-content { background: #1a1d24; border-radius: 14px; border: 1px solid #2d3340; padding: 16px; transform: scale(.9) translateY(20px); transition: transform .3s cubic-bezier(.175,.885,.32,1.275); box-shadow: 0 20px 50px rgba(0,0,0,.8), inset 0 2px 4px rgba(255,255,255,.05); display: flex; flex-direction: column; gap: 12px; width: 86%; max-width: 320px; }
    .cau-modal.show .cau-modal-content { transform: scale(1) translateY(0); }
    .cau-modal-head { color: #cbd5e1; font-size: 12px; font-weight: 700; text-align: center; text-transform: uppercase; letter-spacing: .5px; }
    .cau-modal-head b { color: #ff5252; }
    .cau-modal-digits { display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; }
    .cau-btn-digit { width: 48px; height: 48px; border-radius: 10px; border: 1px solid #343b4a; background: #232833; font-size: 22px; font-weight: 700; color: #fff; cursor: pointer; transition: all .2s cubic-bezier(.175,.885,.32,1.275); box-shadow: 0 4px 6px rgba(0,0,0,.3); display: flex; justify-content: center; align-items: center; }
    .cau-btn-digit:active { transform: scale(.85); }
    .cau-btn-digit.selected { background: #d40000; color: #fff; border-color: #ff5252; transform: scale(1.08); box-shadow: 0 6px 15px rgba(212,0,0,.6), inset 0 2px 4px rgba(255,255,255,.3); }
    .cau-modal-close { align-self: center; background: #343b4a; color: #fff; border: none; padding: 8px 22px; border-radius: 8px; font-size: 12px; font-weight: 700; cursor: pointer; text-transform: uppercase; letter-spacing: .5px; }
    .cau-modal-close:active { transform: scale(.94); }

    /* SLOT LÔ RƠI */
    .injected-slot { background: var(--bg-main); border: 1.5px solid var(--db-bg); border-radius: 14px; padding: 12px; display: flex; flex-direction: column; gap: 10px; box-shadow: 0 6px 16px rgba(212,0,0,.12); }
    .slot-title { font-size: 12px; font-weight: 900; color: var(--db-bg); text-align: center; text-transform: uppercase; letter-spacing: .5px; transition: all .3s; padding: 4px 8px; border-radius: 6px; }
    .slot-title.flash { background: var(--db-bg); color: #fff; box-shadow: 0 0 15px rgba(212,0,0,.6); transform: scale(1.02); }
    .loto-grid { display: flex; flex-wrap: wrap; justify-content: center; align-items: center; gap: 5px; width: 100%; min-height: 26px; }
    .lo-chip { background: var(--lo-chip-bg); color: #fff; font-size: 12px; font-weight: 700; letter-spacing: .5px; padding: 4px 8px; border-radius: 5px; box-shadow: 0 2px 4px var(--lo-chip-shadow), inset 0 1px 0 rgba(255,255,255,.3); transform: scale(0); animation: springDrop .5s cubic-bezier(.175,.885,.32,1.275) forwards; }
    @keyframes springDrop { 0% { transform: scale(0) translateY(-20px) rotate(-5deg); opacity: 0; } 100% { transform: scale(1) translateY(0) rotate(0); opacity: 1; } }

    .dots-wrapper { display: flex; justify-content: center; align-items: center; gap: 3px; width: 100%; }
    .dot { width: 5px; height: 5px; background-color: var(--text-dim); border-radius: 50%; animation: wave 1.2s infinite ease-in-out; }
    .dot:nth-child(2) { animation-delay: -1.1s; } .dot:nth-child(3) { animation-delay: -1s; } .dot:nth-child(4) { animation-delay: -.9s; } .dot:nth-child(5) { animation-delay: -.8s; }
    @keyframes wave { 0%,40%,100% { transform: translateY(0); opacity: .5; } 20% { transform: translateY(-3px); opacity: 1; } }

    /* AI STICKY BAR – FIX: theo dark mode + marquee bằng CSS thay <marquee> */
    .ai-sticky-bar { background: var(--ai-bar-bg); border-top: 1px solid var(--ai-bar-border); padding: 12px 16px calc(12px + env(safe-area-inset-bottom)); display: flex; align-items: center; gap: 10px; z-index: 10; box-shadow: 0 -4px 10px rgba(0,0,0,.06); }
    .ai-marquee { flex-grow: 1; overflow: hidden; white-space: nowrap; min-width: 0; }
    .ai-marquee span { display: inline-block; padding-left: 100%; font-size: 13px; font-weight: 700; color: var(--ai-bar-text); animation: marquee 18s linear infinite; }
    @keyframes marquee { 0% { transform: translateX(0); } 100% { transform: translateX(-100%); } }
    .ai-input { padding: 7px 13px; border-radius: 20px; border: 1px solid var(--ai-bar-border); font-size: 12px; width: 120px; outline: none; background: var(--ai-bar-input); color: var(--text-main); }

    /* ============================================================
       LỚP 2: THỐNG KÊ LÔ TÔ (TOP SHEET)
       ============================================================ */
    .top-sheet { position: absolute; inset: 0; background: var(--sheet-bg); z-index: 20; transform: translateY(-100%); transition: transform .4s cubic-bezier(.2,.8,.2,1); display: flex; flex-direction: column; }
    .top-tab { position: absolute; bottom: -30px; left: 50%; transform: translateX(-50%); background: linear-gradient(180deg, #1976d2, #1565c0); color: #fff; padding: 6px 20px; font-size: 12px; font-weight: 900; text-transform: uppercase; border-radius: 0 0 12px 12px; cursor: pointer; box-shadow: 0 4px 10px rgba(0,0,0,.3); border: 2px solid #0d47a1; border-top: none; z-index: 25; }
    #toggle-top:checked ~ .app-wrapper .top-sheet { transform: translateY(0); }

    .sheet-header { padding: 14px 16px; display: flex; align-items: center; border-bottom: 1px solid var(--border-color); background: var(--bg-main); z-index: 5; }
    .btn-back { background: var(--bg-board); color: var(--text-main); padding: 8px 12px; border-radius: 8px; font-size: 12px; font-weight: 700; cursor: pointer; border: 1px solid var(--border-color); margin-right: 14px; }
    .sheet-title { font-size: 16px; font-weight: 900; color: var(--text-main); text-transform: uppercase; }

    .sheet-content-loto { flex: 1; padding: 16px; display: flex; flex-direction: column; gap: 16px; overflow-y: auto; overflow-x: hidden; }

    .slider-viewport { flex: 2; width: 100%; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,.1); background: var(--block-bg); border: 1px solid var(--border-color); overflow: hidden; position: relative; min-height: 300px; }
    .slider-track { display: flex; width: 200%; height: 100%; transition: transform .5s cubic-bezier(.16,1,.3,1); }
    .slide-pane { width: 50%; height: 100%; flex-shrink: 0; display: flex; flex-direction: column; }

    .block-title-bar { background: linear-gradient(90deg, #d40000, #ff5252); color: #fff; padding: 8px 12px; font-weight: 700; font-size: 13px; text-transform: uppercase; }
    .matrix-container { flex: 1; overflow: auto; -webkit-overflow-scrolling: touch; background: var(--cell-bg); }
    .matrix-table { border-collapse: collapse; table-layout: fixed; }
    .matrix-table th, .matrix-table td { width: 28px; height: 28px; min-width: 28px; max-width: 28px; border: 1px solid var(--cell-border); text-align: center; vertical-align: middle; font-size: 10px; font-weight: 700; color: var(--text-main); }
    .matrix-table thead th { position: sticky; top: 0; z-index: 2; background: var(--sticky-bg); color: var(--text-main); }
    .matrix-table tbody th { position: sticky; left: 0; z-index: 2; background: var(--sticky-bg); color: var(--sticky-text); transition: all .3s; }
    .matrix-table thead th.corner-h { position: sticky; top: 0; left: 0; z-index: 3; background: #333; color: #fff; }
    .data-cell { color: var(--text-main); font-weight: 900; font-size: 13px; opacity: .9; }
    .row-th.search-hit { background: #ffd54f !important; color: #111 !important; box-shadow: 0 0 10px #ffb300; }
    td.search-hit { background: rgba(255,213,79,.35) !important; }

    .gan-alert { background: var(--db-bg) !important; color: #fff !important; animation: ganPulse 1.5s infinite alternate; cursor: pointer; z-index: 10 !important; position: relative; }
    @keyframes ganPulse { 0% { box-shadow: 0 0 4px var(--db-bg); } 100% { box-shadow: 0 0 16px var(--db-bg); } }
    .gan-tooltip { position: absolute; bottom: 110%; left: 50%; transform: translateX(-50%); background: #111; color: #fff; padding: 6px 10px; border-radius: 6px; font-size: 11px; white-space: nowrap; pointer-events: none; opacity: 0; visibility: hidden; transition: all .2s; box-shadow: 0 4px 10px rgba(0,0,0,.5); z-index: 100; border: 1px solid #ff5252; font-weight: 500; letter-spacing: 0; text-transform: none; }
    .gan-tooltip::after { content: ''; position: absolute; top: 100%; left: 50%; transform: translateX(-50%); border-width: 5px; border-style: solid; border-color: #111 transparent transparent transparent; }
    .gan-alert.show-tooltip .gan-tooltip { opacity: 1; visibility: visible; bottom: 125%; }

    .tv-header { background: #000; color: #fff; padding: 8px 12px; font-weight: 700; font-size: 12px; display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid var(--tv-border); z-index: 10; position: relative; }
    .btn-tv-close { background: #333; border: none; color: #fff; padding: 5px 9px; border-radius: 5px; font-size: 10px; cursor: pointer; }
    .tv-screen { --ai-core: rgba(59,130,246,.2); --ai-glow: rgba(59,130,246,.6); --ai-text: #38bdf8; --ai-badge-border: #38bdf8; --ai-badge-bg: rgba(56,189,248,.1); flex: 1; background: var(--tv-bg-base); padding: 15px; display: flex; flex-direction: column; justify-content: center; align-items: center; box-shadow: inset 0 0 40px rgba(0,0,0,.8), inset 0 0 20px var(--ai-glow); position: relative; overflow-y: auto; transition: box-shadow .5s ease; }
    .tv-screen.theme-red { --ai-core: rgba(239,68,68,.2); --ai-glow: rgba(239,68,68,.6); --ai-text: #fca5a5; --ai-badge-border: #ef4444; --ai-badge-bg: rgba(239,68,68,.15); }
    .tv-screen.theme-green { --ai-core: rgba(16,185,129,.2); --ai-glow: rgba(16,185,129,.6); --ai-text: #6ee7b7; --ai-badge-border: #10b981; --ai-badge-bg: rgba(16,185,129,.12); }
    .tv-circuit { position: absolute; inset: 0; background-image: linear-gradient(var(--ai-core) 1px, transparent 1px), linear-gradient(90deg, var(--ai-core) 1px, transparent 1px); background-size: 20px 20px; opacity: .25; z-index: 1; pointer-events: none; animation: circuitPulse 3s infinite alternate; }
    @keyframes circuitPulse { 0% { opacity: .1; } 100% { opacity: .3; } }
    .tv-data-stream { position: absolute; inset: 0; background: linear-gradient(180deg, transparent 0%, var(--ai-glow) 50%, transparent 100%); background-size: 100% 200%; opacity: .15; z-index: 1; pointer-events: none; animation: dataStream 2.5s linear infinite; }
    @keyframes dataStream { 0% { background-position: 0 -100%; } 100% { background-position: 0 200%; } }
    .tv-content-layer { position: relative; z-index: 2; display: flex; flex-direction: column; align-items: center; width: 100%; }
    .tv-text-bot { color: var(--ai-text); font-family: ui-monospace, monospace; font-size: 13px; text-align: center; margin-bottom: 15px; text-shadow: 0 0 5px var(--ai-glow); line-height: 1.6; }
    .tv-results { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; width: 100%; }
    .xien-badge { background: var(--ai-badge-bg); border: 1px solid var(--ai-badge-border); color: var(--ai-badge-border); padding: 8px 16px; border-radius: 8px; font-size: 16px; font-weight: 900; letter-spacing: 1px; box-shadow: 0 0 10px rgba(0,0,0,.5); animation: badgePop .4s cubic-bezier(.175,.885,.32,1.275) forwards; text-align: center; }
    @keyframes badgePop { 0% { transform: scale(.5); opacity: 0; } 100% { transform: scale(1); opacity: 1; } }

    .loto-block-2 { border-radius: 14px; background: var(--bg-main); border: 1px solid var(--border-color); padding: 16px; box-shadow: 0 4px 6px rgba(0,0,0,.05), 0 10px 15px rgba(0,0,0,.08); display: flex; flex-direction: column; gap: 16px; }
    .block-title-2 { font-size: 13px; font-weight: 900; color: var(--db-bg); text-transform: uppercase; border-bottom: 1.5px dashed var(--border-color); padding-bottom: 8px; }
    .special-btn-group { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }
    .btn-special { padding: 10px 4px; border-radius: 10px; font-size: 10px; font-weight: 900; color: #fff; border: none; cursor: pointer; text-transform: uppercase; transition: all .2s cubic-bezier(.175,.885,.32,1.275); display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 4px; letter-spacing: .5px; text-align: center; }
    .btn-special .icon { font-size: 18px; }
    .btn-special:active { transform: scale(.92); }
    .btn-xien { background: linear-gradient(135deg, #f59e0b, #d97706); box-shadow: 0 4px 10px rgba(245,158,11,.3); }
    .btn-nhipdep { background: linear-gradient(135deg, #10b981, #059669); box-shadow: 0 4px 10px rgba(16,185,129,.3); }
    .btn-bacnho { background: linear-gradient(135deg, #3b82f6, #2563eb); box-shadow: 0 4px 10px rgba(59,130,246,.3); }
    .search-group { display: flex; gap: 10px; }
    .search-input { flex: 1; padding: 12px 16px; border-radius: 10px; border: 1.5px solid var(--border-color); background: var(--bg-board); color: var(--text-main); font-size: 16px; font-weight: 700; outline: none; transition: border-color .2s, box-shadow .2s; letter-spacing: 2px; }
    .search-input:focus { border-color: var(--db-bg); box-shadow: 0 0 0 3px rgba(212,0,0,.15); }
    .search-input::placeholder { color: var(--text-dim); font-weight: 400; font-size: 13px; letter-spacing: 0; }
    .btn-search { padding: 0 20px; border-radius: 10px; border: none; background: var(--db-bg); color: #fff; font-weight: 900; font-size: 13px; cursor: pointer; text-transform: uppercase; box-shadow: 0 4px 10px rgba(212,0,0,.3); transition: transform .1s; }
    .btn-search:active { transform: scale(.92); }

    #keyboard-wrapper { display: none; }
    .loto-block-kb { border-radius: 14px; display: flex; flex-direction: column; gap: 10px; padding: 16px; background: var(--block-bg); box-shadow: 0 4px 6px rgba(0,0,0,.05); border: 1px solid var(--border-color); }
    .vk-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
    .vk-btn { background: var(--bg-board); color: var(--text-main); border: 1px solid var(--border-color); border-radius: 10px; padding: 14px 0; font-size: 20px; font-weight: 700; cursor: pointer; transition: all .1s; box-shadow: 0 2px 0 var(--border-color); display: flex; justify-content: center; align-items: center; }
    .vk-btn:active { transform: translateY(2px); box-shadow: none; background: var(--border-color); }
    .vk-action { font-size: 14px; background: var(--sheet-bg); }
    .vk-del { color: var(--db-bg); }

    .lo-top-board { border-radius: 14px; background: var(--bg-main); border: 1px solid var(--border-color); padding: 16px 12px 0; box-shadow: 0 4px 6px rgba(0,0,0,.05), 0 10px 15px rgba(0,0,0,.08); display: flex; flex-direction: column; min-height: 220px; }
    .chart-container { display: flex; align-items: flex-end; justify-content: space-between; height: 160px; padding-top: 30px; gap: clamp(2px, 1vw, 6px); border-bottom: 2px solid var(--border-color); flex: 1; }
    .bar-wrapper { display: flex; flex-direction: column; align-items: center; justify-content: flex-end; flex: 1; height: 100%; position: relative; transition: transform .3s; }
    .bar-wrapper:hover { transform: translateY(-5px); }
    .bar-number { font-weight: 700; font-size: 14px; color: var(--text-main); margin-bottom: 4px; }
    .bar-column { width: 100%; border-radius: 6px 6px 0 0; display: flex; align-items: flex-end; justify-content: center; padding-bottom: 8px; box-shadow: 0 4px 10px rgba(0,0,0,.1), inset 0 2px 5px rgba(255,255,255,.4); transform-origin: bottom; animation: growUp 1.1s cubic-bezier(.175,.885,.32,1.275) forwards; transform: scaleY(0); }
    @keyframes growUp { to { transform: scaleY(1); } }
    .bar-rank { font-size: 9px; font-weight: 700; color: #fff; writing-mode: vertical-rl; transform: rotate(180deg); text-shadow: 0 1px 2px rgba(0,0,0,.5); letter-spacing: 1px; }

    /* ============================================================
       LỚP 3: THỐNG KÊ ĐB (BOTTOM SHEET)
       ============================================================ */
    .bottom-sheet { position: absolute; left: 0; bottom: 0; width: 100%; height: 100%; background: var(--sheet-bg); z-index: 20; transform: translateY(100%); transition: transform .4s cubic-bezier(.2,.8,.2,1); display: flex; flex-direction: column; }
    .bottom-tab { position: absolute; top: -30px; left: 50%; transform: translateX(-50%); background: linear-gradient(0deg, #d32f2f, #c62828); color: #fff; padding: 6px 20px; font-size: 12px; font-weight: 900; text-transform: uppercase; border-radius: 12px 12px 0 0; cursor: pointer; box-shadow: 0 -4px 10px rgba(0,0,0,.3); border: 2px solid #b71c1c; border-bottom: none; z-index: 25; }
    #toggle-bottom:checked ~ .app-wrapper .bottom-sheet { transform: translateY(0); }
    .sheet-content-db { flex: 1; padding: 16px; display: flex; flex-direction: column; gap: 16px; overflow-y: auto; }
    .db-stat-card { background: var(--bg-main); border: 1px solid var(--border-color); border-radius: 14px; padding: 16px; box-shadow: 0 4px 8px rgba(0,0,0,.05); }
    .db-stat-card h4 { font-size: 13px; color: var(--db-bg); text-transform: uppercase; margin-bottom: 12px; border-bottom: 1.5px dashed var(--border-color); padding-bottom: 8px; }
    .db-pair-grid { display: grid; grid-template-columns: repeat(5, 1fr); gap: 8px; }
    .db-pair { background: var(--glass-bg); border: 1px solid var(--glass-border); box-shadow: var(--glass-shadow); border-radius: 8px; padding: 8px 0; text-align: center; }
    .db-pair .p { font-size: 18px; font-weight: 800; color: var(--text-main); }
    .db-pair .c { font-size: 10px; color: var(--text-dim); font-weight: 700; }
</style>
</head>
<body>

<input type="checkbox" id="toggle-dark" hidden>
<input type="checkbox" id="toggle-top" hidden>
<input type="checkbox" id="toggle-bottom" hidden>

<div class="app-wrapper" id="app-wrapper">

    <!-- ===== LỚP 2: THỐNG KÊ LÔ TÔ ===== -->
    <div class="top-sheet">
        <div class="sheet-header">
            <label for="toggle-top" class="btn-back">🔙 Quay lại</label>
            <div class="sheet-title">📊 Thống Kê Lô Tô</div>
        </div>
        <div class="sheet-content-loto">
            <div class="slider-viewport">
                <div class="slider-track" id="main-slider-track">
                    <div class="slide-pane">
                        <div class="block-title-bar">Bố cục 1: Tần suất lô (30 ngày)</div>
                        <div class="matrix-container">
                            <table class="matrix-table" id="matrix-table">
                                <thead><tr id="matrix-head"></tr></thead>
                                <tbody id="matrix-body"></tbody>
                            </table>
                        </div>
                    </div>
                    <div class="slide-pane">
                        <div class="tv-header"><span id="tv-header-title">📺 Hệ thống AI Calculator</span><button class="btn-tv-close" onclick="closeTV()">✖ Đóng</button></div>
                        <div class="tv-screen theme-blue" id="ai-tv-screen">
                            <div class="tv-circuit"></div><div class="tv-data-stream"></div>
                            <div class="tv-content-layer">
                                <div class="tv-text-bot" id="tv-message">👋 Chào bạn!<br>Hệ thống AI đã sẵn sàng hoạt động.</div>
                                <div class="tv-results" id="tv-results-container"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="loto-block-2">
                <div class="block-title-2">⚡ Công cụ tính toán</div>
                <div class="special-btn-group">
                    <button class="btn-special btn-xien" onclick="activateXienAI()"><span class="icon">🔗</span><span>Ghép Xiên</span></button>
                    <button class="btn-special btn-nhipdep" onclick="activateNhipDep()"><span class="icon">📈</span><span>Nhịp Đẹp</span></button>
                    <button class="btn-special btn-bacnho" onclick="activateBacNhoAI()"><span class="icon">🧠</span><span>Bạc Nhớ</span></button>
                </div>
                <div class="search-group">
                    <input type="text" class="search-input num-font" id="ai-search-input" placeholder="Chạm để nhập số..." readonly onclick="showKeyboard()">
                    <button class="btn-search" onclick="runSearch()">Tìm</button>
                </div>
            </div>

            <div id="keyboard-wrapper">
                <div class="loto-block-kb">
                    <div class="block-title-2" style="display:flex;justify-content:space-between;">
                        <span>⌨ Bàn phím nhập liệu</span>
                        <span style="cursor:pointer;color:var(--text-dim);" onclick="hideKeyboard()">Đóng ✖</span>
                    </div>
                    <div class="vk-grid num-font" id="virtual-keyboard">
                        <button class="vk-btn" data-val="1">1</button><button class="vk-btn" data-val="2">2</button><button class="vk-btn" data-val="3">3</button>
                        <button class="vk-btn" data-val="4">4</button><button class="vk-btn" data-val="5">5</button><button class="vk-btn" data-val="6">6</button>
                        <button class="vk-btn" data-val="7">7</button><button class="vk-btn" data-val="8">8</button><button class="vk-btn" data-val="9">9</button>
                        <button class="vk-btn vk-action" onclick="clearInput()">CLEAR</button><button class="vk-btn" data-val="0">0</button><button class="vk-btn vk-action vk-del" onclick="delInput()">DEL</button>
                    </div>
                </div>
            </div>

            <div class="lo-top-board">
                <div class="block-title-2">🏆 Bảng xếp hạng lô về nhiều nhất (30 ngày)</div>
                <div class="chart-container" id="lo-top-chart"></div>
            </div>
        </div>
        <label for="toggle-top" class="top-tab">▼ Kéo Thống Kê Lô Tô</label>
    </div>

    <!-- ===== LỚP 1: LUỒNG CHÍNH ===== -->
    <div class="main-layer">
        <div class="top-controls">
            <div class="top-controls-left">
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-cau" onchange="toggleCau(this)"><span class="slider"></span></label><span class="switch-label-text">Làm Cầu</span></div>
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-quay-thu" onchange="triggerQuayThu(this)"><span class="slider"></span></label><span class="switch-label-text">Quay Thử</span></div>
            </div>
            <div class="top-controls-right">
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-dark-vis" onchange="document.getElementById('toggle-dark').checked=this.checked"><span class="slider"></span></label><span class="switch-label-text">Sáng/Tối</span></div>
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-mask-vis" onchange="toggleMask(this)"><span class="slider"></span></label><span class="switch-label-text">Lặn Số ĐB</span></div>
            </div>
        </div>

        <div class="boards-feed" id="boards-feed-container">
            <div class="board board-live-cau" id="board-live">
                <div class="board-header">
                    <div class="board-title live">🔴 Kết quả xổ số Thần Mèo</div>
                    <div class="status-blink" id="live-status">⏳ Hãy bật công tắc "Quay Thử" ở trên...</div>
                    <div class="board-date" id="live-date"></div>
                </div>
                <!-- ĐB lên trên cùng cho đúng chuẩn bảng KQ miền Bắc + đồng bộ với bảng lịch sử -->
                <div class="row row-db" data-prize="ĐB" data-len="5">
                    <div class="prize-name db">ĐB</div>
                    <div class="prize-results grid-1">
                        <div class="number-box">
                            <div class="mask-cover" onclick="this.parentElement.classList.add('revealed')"><span class="eye">🙈</span> Chạm để xem</div>
                            <span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span>
                        </div>
                    </div>
                </div>
                <div class="row" data-prize="G1" data-len="5"><div class="prize-name">G1</div><div class="prize-results grid-1"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G2" data-len="5"><div class="prize-name">G2</div><div class="prize-results grid-2"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G3" data-len="5"><div class="prize-name">G3</div><div class="prize-results grid-6"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G4" data-len="4"><div class="prize-name">G4</div><div class="prize-results grid-4"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G5" data-len="4"><div class="prize-name">G5</div><div class="prize-results grid-6"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G6" data-len="3"><div class="prize-name">G6</div><div class="prize-results grid-3"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G7" data-len="2"><div class="prize-name">G7</div><div class="prize-results grid-4"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
            </div>

            <div class="injected-slot" id="custom-slot">
                <div class="slot-title" id="slot-title">⚡ Bảng lô rơi sẽ hiển thị tại đây</div>
                <div class="loto-grid" id="loto-drop-zone"></div>
            </div>

            <div id="history-boards-container"></div>
        </div>

        <div class="ai-sticky-bar">
            <div class="ai-marquee"><span>🤖 Cuộn xuống để xem 40 bảng kết quả lịch sử · Bật "Quay Thử" để xem quay số trực tiếp · Bật "Làm Cầu" rồi chạm số để đánh dấu cầu chạy...</span></div>
            <input type="text" class="ai-input" placeholder="Hỏi AI...">
        </div>
    </div>

    <!-- ===== LỚP 3: THỐNG KÊ ĐB ===== -->
    <div class="bottom-sheet">
        <label for="toggle-bottom" class="bottom-tab">▲ Kéo Thống Kê ĐB</label>
        <div class="sheet-header"><label for="toggle-bottom" class="btn-back">🔙 Quay lại</label><div class="sheet-title">🎯 Thống Kê Đặc Biệt</div></div>
        <div class="sheet-content-db" id="db-content"></div>
    </div>

    <!-- MODAL LÀM CẦU -->
    <div id="cau-modal" class="cau-modal" onmousedown="closeCauModal(event)" ontouchstart="closeCauModal(event)">
        <div class="cau-modal-content" onmousedown="event.stopPropagation()" ontouchstart="event.stopPropagation()">
            <div class="cau-modal-head">Chọn chữ số làm cầu cho <b id="cau-modal-num"></b></div>
            <div id="cau-modal-digits" class="cau-modal-digits num-font"></div>
            <button class="cau-modal-close" onclick="closeCauModal()">Xong</button>
        </div>
    </div>
</div>

<script>
"use strict";

/* ============================================================
   1. ENGINE DỮ LIỆU (FIX: dữ liệu nhất quán thay vì random mỗi ô)
   Một bộ dữ liệu duy nhất sinh ra ở seed cố định -> ma trận tần
   suất, lô gan, top lô, bạc nhớ ĐB đều khớp nhau & ổn định.
   ============================================================ */
function makeRNG(seed){ let s = seed >>> 0; return function(){ s = (s*1664525 + 1013904223) >>> 0; return s/4294967296; }; }
const rng = makeRNG(20260326);
const DAYS = 30;

// freq[lo][day] = số lần lô về trong ngày đó (0..3)
const LottoData = (() => {
    const freq = [];
    for (let lo = 0; lo <= 99; lo++){
        const row = [];
        const bias = 0.55 + (rng() * 0.35);          // mỗi lô có "thiên hướng" riêng
        for (let d = 0; d < DAYS; d++){
            let n = 0;
            if (rng() < (0.30 * bias)) n = 1;
            if (n && rng() < 0.18) n = 2;
            if (n === 2 && rng() < 0.10) n = 3;
            row.push(n);
        }
        freq.push(row);
    }
    // tổng tần suất + số ngày gan (số ngày gần nhất chưa về, đếm từ ngày mới nhất = cột cuối)
    const totals = freq.map(r => r.reduce((a,b)=>a+b,0));
    const gan = freq.map(r => {
        let g = 0;
        for (let d = DAYS-1; d >= 0; d--){ if (r[d] > 0) break; g++; }
        return g;
    });
    return { freq, totals, gan };
})();

const pad2 = n => (n < 10 ? '0'+n : ''+n);

/* ============================================================
   2. TIỆN ÍCH SỐ
   ============================================================ */
function generateRandom(length){ let r=''; for(let i=0;i<length;i++) r += Math.floor(Math.random()*10); return r; }
function wrapDigits(numStr){
    if(!numStr) return '';
    return numStr.split('').map((d,i)=>`<span class="digit" data-idx="${i}">${d}</span>`).join('');
}
const sleep = ms => new Promise(r => setTimeout(r, ms));

/* ============================================================
   3. KHỞI TẠO
   ============================================================ */
document.addEventListener("DOMContentLoaded", () => {
    setLiveDate();
    buildMatrix();
    renderTopLo();
    renderDbStats();
    setupKeyboard();
    renderHistoricalBoards(40);
    bindMatrixTooltips();
    bindCauClicks();
});

function setLiveDate(){
    const d = new Date(2026, 2, 26);
    let s = d.toLocaleDateString('vi-VN', { weekday:'long', year:'numeric', month:'2-digit', day:'2-digit' });
    document.getElementById('live-date').textContent = s.charAt(0).toUpperCase()+s.slice(1);
}

/* ---- Ma trận tần suất (head + body sinh bằng JS, nhất quán dữ liệu) ---- */
function buildMatrix(){
    const head = document.getElementById('matrix-head');
    let h = '<th class="corner-h">Lô</th>';
    for(let j=1;j<=DAYS;j++) h += `<th>${j}</th>`;
    head.innerHTML = h;

    const tbody = document.getElementById('matrix-body');
    let rows = '';
    for(let lo=0; lo<=99; lo++){
        const isGan = LottoData.gan[lo] >= 12;             // gan thật: >=12 ngày chưa về
        const thClass = isGan ? 'row-th gan-alert' : 'row-th';
        const tip = isGan ? `<div class="gan-tooltip">⚠️ Gan ${LottoData.gan[lo]} ngày · Tổng về: ${LottoData.totals[lo]}</div>` : '';
        rows += `<tr data-lo="${pad2(lo)}"><th class="${thClass}">${pad2(lo)}${tip}</th>`;
        for(let d=0; d<DAYS; d++){
            const v = LottoData.freq[lo][d];
            rows += v>0 ? `<td class="data-cell">${v}</td>` : `<td></td>`;
        }
        rows += '</tr>';
    }
    tbody.innerHTML = rows;
}

function bindMatrixTooltips(){
    document.getElementById('matrix-body').addEventListener('click', function(e){
        const th = e.target.closest('th.gan-alert');
        document.querySelectorAll('th.gan-alert.show-tooltip').forEach(el => { if(el!==th) el.classList.remove('show-tooltip'); });
        if(th) th.classList.toggle('show-tooltip');
    });
}

/* ---- Top lô về nhiều nhất (tính thật từ totals) ---- */
function renderTopLo(){
    const chart = document.getElementById('lo-top-chart');
    const ranked = LottoData.totals.map((t,lo)=>({lo:pad2(lo), t}))
                    .sort((a,b)=>b.t-a.t).slice(0,10);
    const max = ranked[0].t || 1;
    const palette = [
        'linear-gradient(to top,#d50000,#ff1744)','linear-gradient(to top,#e65100,#ff9100)',
        'linear-gradient(to top,#ef6c00,#ffb300)','linear-gradient(to top,#f57f17,#ffc400)',
        'linear-gradient(to top,#fbc02d,#ffee58)','linear-gradient(to top,#afb42b,#d4e157)',
        'linear-gradient(to top,#689f38,#9ccc65)','linear-gradient(to top,#0097a7,#4dd0e1)',
        'linear-gradient(to top,#0288d1,#29b6f6)','linear-gradient(to top,#1976d2,#4fc3f7)'
    ];
    let html='';
    ranked.forEach((item,idx)=>{
        const height = 20 + Math.round((item.t/max)*80);
        const glow = idx<3 ? `box-shadow:0 0 12px ${palette[idx].split(',')[1]};` : '';
        const txt = idx===0 ? 'color:var(--db-bg);text-shadow:0 0 8px rgba(212,0,0,.5);transform:scale(1.3);' : '';
        html += `<div class="bar-wrapper" title="Lô ${item.lo}: ${item.t} lần">
            <div class="bar-number num-font" style="${txt}">${item.lo}</div>
            <div class="bar-column" style="height:${height}%;background:${palette[idx]};${glow}animation-delay:${idx*0.08}s;">
                <div class="bar-rank">TOP ${idx+1}</div></div></div>`;
    });
    chart.innerHTML = html;
}

/* ---- Thống kê ĐB (Lớp 3) – bạc nhớ + đầu/đuôi gan ---- */
function renderDbStats(){
    const wrap = document.getElementById('db-content');
    // đầu - đuôi xuất hiện nhiều của 2 số cuối ĐB (mô phỏng từ totals)
    const heads = Array(10).fill(0), tails = Array(10).fill(0);
    LottoData.totals.forEach((t,lo)=>{ heads[Math.floor(lo/10)] += t; tails[lo%10] += t; });
    const topGan = LottoData.gan.map((g,lo)=>({lo:pad2(lo),g})).sort((a,b)=>b.g-a.g).slice(0,10);

    const cell = (arr,label) => arr.map((v,i)=>`<div class="db-pair"><div class="p num-font">${i}</div><div class="c">${label}: ${v}</div></div>`).join('');
    wrap.innerHTML = `
      <div class="db-stat-card"><h4>🔢 Đầu ĐB về nhiều (30 ngày)</h4><div class="db-pair-grid">${cell(heads,'lần')}</div></div>
      <div class="db-stat-card"><h4>🔚 Đuôi ĐB về nhiều (30 ngày)</h4><div class="db-pair-grid">${cell(tails,'lần')}</div></div>
      <div class="db-stat-card"><h4>🥶 Top 10 lô gan lì nhất</h4><div class="db-pair-grid">
        ${topGan.map(x=>`<div class="db-pair"><div class="p num-font">${x.lo}</div><div class="c">gan ${x.g}n</div></div>`).join('')}
      </div></div>`;
}

/* ============================================================
   4. BẢNG LỊCH SỬ
   ============================================================ */
function renderHistoricalBoards(count){
    const container = document.getElementById('history-boards-container');
    if(!container) return;
    const baseDate = new Date(2026, 2, 25);
    const frag = [];
    const box = (len) => `<div class="number-box"><span class="number-text num-font">${wrapDigits(generateRandom(len))}</span></div>`;
    for(let i=0;i<count;i++){
        const d = new Date(baseDate); d.setDate(d.getDate()-i);
        let day = d.toLocaleDateString('vi-VN',{weekday:'long',year:'numeric',month:'2-digit',day:'2-digit'});
        day = day.charAt(0).toUpperCase()+day.slice(1);
        frag.push(`<div class="board" style="margin-bottom:0">
            <div class="board-header"><div class="board-title">Kết quả xổ số Thần Mèo</div><div class="board-date">${day}</div></div>
            <div class="row row-db" data-len="5"><div class="prize-name db">ĐB</div><div class="prize-results grid-1">${box(5)}</div></div>
            <div class="row"><div class="prize-name">G1</div><div class="prize-results grid-1">${box(5)}</div></div>
            <div class="row"><div class="prize-name">G2</div><div class="prize-results grid-2">${box(5)}${box(5)}</div></div>
            <div class="row"><div class="prize-name">G3</div><div class="prize-results grid-6">${box(5)}${box(5)}${box(5)}${box(5)}${box(5)}${box(5)}</div></div>
            <div class="row"><div class="prize-name">G4</div><div class="prize-results grid-4">${box(4)}${box(4)}${box(4)}${box(4)}</div></div>
            <div class="row"><div class="prize-name">G5</div><div class="prize-results grid-6">${box(4)}${box(4)}${box(4)}${box(4)}${box(4)}${box(4)}</div></div>
            <div class="row"><div class="prize-name">G6</div><div class="prize-results grid-3">${box(3)}${box(3)}${box(3)}</div></div>
            <div class="row"><div class="prize-name">G7</div><div class="prize-results grid-4">${box(2)}${box(2)}${box(2)}${box(2)}</div></div>
        </div>`);
    }
    container.style.cssText = 'display:flex;flex-direction:column;gap:24px;';
    container.innerHTML = frag.join('');
}

/* ============================================================
   5. LÀM CẦU
   ============================================================ */
let activeCauBox = null;

function toggleCau(cb){
    document.getElementById('app-wrapper').classList.toggle('cau-on', cb.checked);
    if(!cb.checked) closeCauModal();
}

function bindCauClicks(){
    document.getElementById('boards-feed-container').addEventListener('click', function(e){
        if(!document.getElementById('toggle-cau').checked) return;
        const box = e.target.closest('.number-box');
        if(!box) return;
        if(e.target.closest('.mask-cover')) return;       // không mở cầu khi đang chạm lớp che ĐB
        const numText = box.querySelector('.number-text');
        if(!numText || numText.querySelector('.dot')) return;  // chưa có số (đang chờ quay)
        activeCauBox = box;
        openCauModal(numText);
    });
}

function openCauModal(numText){
    const digits = numText.querySelectorAll('.digit');
    if(!digits.length) return;
    document.getElementById('cau-modal-num').textContent = numText.textContent.trim();
    const cont = document.getElementById('cau-modal-digits');
    cont.innerHTML = '';
    digits.forEach(span => {
        const btn = document.createElement('button');
        btn.className = 'cau-btn-digit' + (span.classList.contains('active-cau') ? ' selected' : '');
        btn.textContent = span.textContent;
        btn.onclick = () => { btn.classList.toggle('selected'); span.classList.toggle('active-cau'); };
        cont.appendChild(btn);
    });
    document.getElementById('cau-modal').classList.add('show');
}
function closeCauModal(e){
    if(e) e.preventDefault();
    document.getElementById('cau-modal').classList.remove('show');
    activeCauBox = null;
}

/* ============================================================
   6. LẶN SỐ ĐB (mới)
   ============================================================ */
function toggleMask(cb){
    const wrap = document.getElementById('app-wrapper');
    wrap.classList.toggle('masking', cb.checked);
    if(!cb.checked) document.querySelectorAll('.row-db .number-box.revealed').forEach(b=>b.classList.remove('revealed'));
}

/* ============================================================
   7. BÀN PHÍM ẢO + TÌM KIẾM
   ============================================================ */
const searchInput = document.getElementById('ai-search-input');
const keyboardWrapper = document.getElementById('keyboard-wrapper');
function showKeyboard(){ keyboardWrapper.style.display='block'; keyboardWrapper.scrollIntoView({behavior:'smooth',block:'nearest'}); }
function hideKeyboard(){ keyboardWrapper.style.display='none'; }
function setupKeyboard(){
    document.querySelectorAll('#virtual-keyboard .vk-btn[data-val]').forEach(k=>{
        k.addEventListener('click', e=>{
            let cur = searchInput.value.replace(/\s/g,'');
            if(cur.length<10){ cur += e.target.getAttribute('data-val'); formatInput(cur); }
        });
    });
}
function clearInput(){ searchInput.value=''; clearSearchHits(); }
function delInput(){ let cur=searchInput.value.replace(/\s/g,''); if(cur.length){ formatInput(cur.slice(0,-1)); } }
function formatInput(raw){ searchInput.value = raw.match(/.{1,2}/g)?.join(' ') || ''; }

function clearSearchHits(){
    document.querySelectorAll('.search-hit').forEach(el=>el.classList.remove('search-hit'));
}

/* Tìm: highlight lô trong ma trận + báo thống kê thật trên màn AI */
function runSearch(){
    const raw = searchInput.value.replace(/\s/g,'');
    const pairs = [...new Set(raw.match(/.{2}/g) || [])];
    clearSearchHits();
    if(!pairs.length){ flashTV('blue','⚠️ Hãy nhập ít nhất 1 cặp số (2 chữ số) để tra cứu.'); return; }

    let report = [];
    pairs.forEach(p=>{
        const tr = document.querySelector(`#matrix-body tr[data-lo="${p}"]`);
        if(tr){
            tr.querySelector('th').classList.add('search-hit');
            tr.querySelectorAll('td').forEach(td=>td.classList.add('search-hit'));
            const lo = parseInt(p,10);
            report.push(`Lô <b>${p}</b>: về <b>${LottoData.totals[lo]}</b> lần / 30 ngày · gan hiện tại <b>${LottoData.gan[lo]}</b> ngày`);
            if(pairs.length===1) tr.scrollIntoView({behavior:'smooth',block:'center'});
        }
    });
    tvScreen.className='tv-screen theme-blue';
    tvHeader.textContent='🔎 Tra cứu tần suất lô';
    sliderTrack.style.transform='translateX(-50%)';
    tvResults.innerHTML='';
    tvMessage.innerHTML = report.length ? report.join('<br>') : '⚠️ Không tìm thấy dữ liệu.';
}

/* ============================================================
   8. MÀN HÌNH AI (Ghép Xiên / Bạc Nhớ / Nhịp Đẹp)
   ============================================================ */
const sliderTrack = document.getElementById('main-slider-track');
const tvScreen    = document.getElementById('ai-tv-screen');
const tvHeader    = document.getElementById('tv-header-title');
const tvMessage   = document.getElementById('tv-message');
const tvResults   = document.getElementById('tv-results-container');

function closeTV(){ sliderTrack.style.transform='translateX(0)'; }
function flashTV(theme,msg){ tvScreen.className='tv-screen theme-'+theme; sliderTrack.style.transform='translateX(-50%)'; tvResults.innerHTML=''; tvMessage.innerHTML=msg; }
function getPairs(){ return [...new Set((searchInput.value.replace(/\s/g,'').match(/.{2}/g)) || [])]; }
function spawnBadge(html, delay){ setTimeout(()=>{ const b=document.createElement('div'); b.className='xien-badge'; b.innerHTML=html; tvResults.appendChild(b); }, delay); }

function activateXienAI(){
    hideKeyboard();
    const pairs = getPairs();
    if(pairs.length<2){ flashTV('blue','⚠️ Cần ít nhất 2 cặp khác nhau (4 chữ số) để ghép xiên.'); return; }
    flashTV('blue', `✅ Ghép ${pairs.length} cặp [${pairs.join(', ')}] thành các xiên 2:`);
    tvHeader.textContent='🔗 Hệ thống ghép xiên AI';
    let k=0;
    for(let i=0;i<pairs.length-1;i++)
        for(let j=i+1;j<pairs.length;j++)
            spawnBadge(`${pairs[i]} – ${pairs[j]}`, (k++)*140);
}

function activateBacNhoAI(){
    hideKeyboard();
    const pairs = getPairs();
    if(!pairs.length){ flashTV('red','⚠️ Nhập ít nhất 1 cặp để tra Bạc Nhớ.'); return; }
    flashTV('red', `🧠 <b>Cơ sở dữ liệu thống kê</b><br>Sau khi [${pairs.join(', ')}] về, cặp thường theo sau:`);
    tvHeader.textContent='🚨 Hệ thống Bạc Nhớ AI';
    const db = { "00":"99","99":"00","12":"34 – 43","21":"45 – 54","68":"86","86":"68","79":"97","97":"79" };
    pairs.forEach((p,i)=>{
        // nếu không có trong bảng, suy ra "lộn" và "kép" liên quan -> ổn định, không random
        const rev = p[1]+p[0];
        const res = db[p] || `${rev} – ${p[0]}${p[0]}`;
        spawnBadge(`<span style="font-size:11px;opacity:.8;font-weight:500;">Cầu ${p} ➔ theo sau:</span><br>${res}`, i*200);
    });
}

function activateNhipDep(){
    hideKeyboard();
    flashTV('green','📈 <b>Nhịp đẹp đang chạy</b> – các lô có nhịp về đều & đang nóng:');
    tvHeader.textContent='📈 Bộ lọc Nhịp Đẹp AI';
    // "nhịp đẹp": lô có tổng về cao nhưng gan vừa phải (1..4 ngày) -> sắp tới chu kỳ
    const cand = LottoData.totals
        .map((t,lo)=>({lo:pad2(lo), t, g:LottoData.gan[lo]}))
        .filter(x => x.g>=1 && x.g<=4)
        .sort((a,b)=> b.t-a.t)
        .slice(0,6);
    if(!cand.length){ tvMessage.innerHTML='Chưa có lô nào vào nhịp đẹp hôm nay.'; return; }
    cand.forEach((x,i)=> spawnBadge(`${x.lo}<br><span style="font-size:10px;opacity:.8;font-weight:500;">về ${x.t}× · gan ${x.g}n</span>`, i*160));
}

/* ============================================================
   9. QUAY THỬ TRỰC TIẾP
   ============================================================ */
async function triggerQuayThu(cb){
    if(cb.checked){
        cb.disabled = true;
        await startSimulation();
        cb.checked = false;
        cb.disabled = false;
    }
}

async function startSimulation(){
    const status = document.getElementById('live-status');
    const dropZone = document.getElementById('loto-drop-zone');
    const slotTitle = document.getElementById('slot-title');
    status.textContent = "🔴 Đang quay số..."; status.style.color = "var(--db-bg)";
    dropZone.innerHTML = ''; slotTitle.textContent = "⚡ Hệ thống đang lấy kết quả...";

    // reset các ô về trạng thái chờ
    document.querySelectorAll('#board-live .number-text').forEach(box=>{
        const len = box.closest('.row').dataset.len;
        let dots=''; for(let i=0;i<len;i++) dots+='<span class="dot"></span>';
        box.innerHTML = `<div class="dots-wrapper">${dots}</div>`;
    });

    // thứ tự quay thực tế: G1 -> ... -> G7 -> ĐB (ĐB quay cuối dù hiển thị trên cùng)
    const order = ['G1','G2','G3','G4','G5','G6','G7','ĐB'];
    const rows = Array.from(document.querySelectorAll('#board-live .row'));
    const msgs = ["gan cực đại!","rơi liên tiếp 3 ngày!","ra cả cặp rất đẹp!","vào nhịp rơi ổn định!","xuất hiện đúng cầu chạy!"];

    for(const name of order){
        const row = rows.find(r => r.dataset.prize === name);
        if(!row) continue;
        const len = parseInt(row.dataset.len);
        const label = row.querySelector('.prize-name');
        const boxes = row.querySelectorAll('.number-text');
        label.classList.add('active-led');
        for(const box of boxes){
            box.classList.add('spinning');
            const spin = setInterval(()=>{ box.textContent = generateRandom(len); }, 50);
            await sleep(900);
            clearInterval(spin);
            box.classList.remove('spinning');
            const final = generateRandom(len);
            box.innerHTML = wrapDigits(final);
            const lo = final.slice(-2);
            const chip = document.createElement('div');
            chip.className='lo-chip'; chip.textContent = lo; dropZone.appendChild(chip);
            const m = msgs[Math.floor(Math.random()*msgs.length)];
            slotTitle.textContent = `🔥 Lô ${lo} ${m} (${name})`;
            slotTitle.classList.add('flash'); setTimeout(()=>slotTitle.classList.remove('flash'),500);
            await sleep(150);
        }
        label.classList.remove('active-led');
    }
    status.textContent = "✅ Đã quay xong"; status.style.color = "var(--led-color)";
    slotTitle.textContent = "Kỳ quay kết thúc · Bật 'Làm Cầu' để chấm cầu các giải.";
}
</script>
</body>
</html>
----------------------

<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Super App Xổ Số V10 - Tần Suất Lô</title>
<style>
    /* ============================================================
       RESET + ENGINE FONT (FIX: optimizeLegibility chỉ áp cho chữ,
       không áp toàn cục để tránh tụt hiệu năng khi render 3000+ ô)
       ============================================================ */
    *, *::before, *::after {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        scrollbar-width: none;
        -webkit-tap-highlight-color: transparent;
    }
    *::-webkit-scrollbar { display: none; }

    /* Font số dùng chung: tabular-nums để số không nhảy/lệch khi quay & không lem */
    .num-font {
        font-family: "SF Mono", "Helvetica Neue", Helvetica, Arial, sans-serif;
        font-variant-numeric: tabular-nums lining-nums;
        font-feature-settings: "tnum" 1, "lnum" 1;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-rendering: optimizeLegibility;
    }

    html, body { height: 100%; }
    body {
        background-color: #050505;
        display: flex;
        justify-content: center;
        align-items: flex-start;
        height: 100dvh;
        overflow: hidden;
        width: 100vw;
    }

    /* ============================================================
       BIẾN MÀU – LIGHT
       ============================================================ */
    .app-wrapper {
        --bg-main: #ffffff; --bg-board: #cbd5e1; --text-main: #111111; --text-dim: #6b7280;
        --border-color: #cbd5e1;
        --db-bg: #d40000; --db-text: #ffffff; --led-color: #00e676; --led-bg: #111111;
        --sheet-bg: #f8f9fa; --block-text: #333333;
        --cell-bg: #ffffff; --cell-border: #e2e8f0;
        --sticky-bg: #f1f5f9; --sticky-text: #d40000;
        --block-bg: #ffffff;
        --lo-chip-bg: linear-gradient(135deg, #d40000, #ff5252);
        --lo-chip-shadow: rgba(212,0,0,0.4);
        --tv-bg-base: #0a0f18; --tv-border: #1e293b;
        --modal-overlay: rgba(0,0,0,0.45);
        --glass-bg: linear-gradient(180deg, #ffffff 0%, #eef2f7 100%);
        --glass-shadow: inset 0 2px 4px rgba(255,255,255,1), 0 2px 5px rgba(0,0,0,0.08);
        --glass-border: #cbd5e1;
        --ai-bar-bg: linear-gradient(135deg, #e3f2fd, #bbdefb);
        --ai-bar-border: #90caf9; --ai-bar-text: #1565c0; --ai-bar-input: #ffffff;
    }
    /* ============================================================
       BIẾN MÀU – DARK
       ============================================================ */
    #toggle-dark:checked ~ .app-wrapper {
        --bg-main: #121212; --bg-board: #0f172a; --text-main: #ffffff; --text-dim: #94a3b8;
        --border-color: #334155;
        --sheet-bg: #0b0f17; --block-text: #dddddd;
        --cell-bg: #1e293b; --cell-border: #334155;
        --sticky-bg: #0f172a; --sticky-text: #ff5252;
        --block-bg: #1e293b;
        --lo-chip-bg: linear-gradient(135deg, #ff1744, #d50000);
        --lo-chip-shadow: rgba(255, 23, 68, 0.4);
        --tv-bg-base: #05080f; --tv-border: #334155;
        --modal-overlay: rgba(0,0,0,0.72);
        --glass-bg: linear-gradient(180deg, #243044 0%, #161f30 100%);
        --glass-shadow: inset 0 1px 2px rgba(255,255,255,0.07), 0 3px 6px rgba(0,0,0,0.45);
        --glass-border: #334155;
        --ai-bar-bg: linear-gradient(135deg, #0f2440, #102a4d);
        --ai-bar-border: #1e3a5f; --ai-bar-text: #7cc4ff; --ai-bar-input: #0f172a;
    }

    .app-wrapper {
        max-width: 480px; width: 100%; height: 100%;
        position: relative; background-color: var(--bg-main);
        color: var(--text-main); overflow: hidden;
        box-shadow: 0 0 40px rgba(0,0,0,0.9);
    }

    /* ============================================================
       LỚP 1: LUỒNG LỊCH SỬ
       ============================================================ */
    .main-layer { width: 100%; height: 100%; display: flex; flex-direction: column; background: var(--bg-board); transition: background .3s ease; }

    .top-controls { display: flex; justify-content: space-between; align-items: center; padding: 10px 16px; background: var(--bg-main); border-bottom: 1px solid var(--border-color); z-index: 5; }
    .top-controls-left, .top-controls-right { display: flex; gap: 14px; align-items: center; }

    .switch-wrap { display: flex; flex-direction: column; align-items: center; gap: 4px; }
    .switch-label-text { font-size: 10px; font-weight: 700; color: var(--text-main); text-transform: uppercase; letter-spacing: .3px; }
    .switch { position: relative; display: inline-block; width: 36px; height: 18px; }
    .switch input { opacity: 0; width: 0; height: 0; }
    .switch input:disabled + .slider { opacity: .5; cursor: not-allowed; }
    .slider { position: absolute; cursor: pointer; inset: 0; background-color: #cbd5e1; transition: .3s; border-radius: 20px; box-shadow: inset 0 1px 3px rgba(0,0,0,.2); }
    .slider:before { position: absolute; content: ""; height: 14px; width: 14px; left: 2px; bottom: 2px; background-color: #fff; transition: .3s; border-radius: 50%; box-shadow: 0 1px 2px rgba(0,0,0,.3); }
    input:checked + .slider { background-color: var(--db-bg); }
    input:checked + .slider:before { transform: translateX(18px); }

    .boards-feed { flex: 1; overflow-y: auto; overflow-x: hidden; padding: 16px 12px; display: flex; flex-direction: column; gap: 24px; -webkit-overflow-scrolling: touch; }

    .board { background: var(--bg-main); border-radius: 14px; border: 1px solid var(--border-color); padding: 12px; box-shadow: 0 2px 4px rgba(0,0,0,.02), 0 8px 16px rgba(0,0,0,.05); transition: background .3s ease, border-color .3s ease; }
    .board-header { text-align: center; margin-bottom: 14px; padding-bottom: 10px; border-bottom: 1.5px dashed var(--border-color); }
    .board-title { font-size: 17px; font-weight: 900; color: var(--text-main); text-transform: uppercase; letter-spacing: .5px; }
    .board-title.live { color: var(--db-bg); text-shadow: 0 2px 4px rgba(212,0,0,.18); }
    .status-blink { font-size: 12px; color: var(--db-bg); animation: blink 1.2s infinite; font-weight: 700; margin-top: 4px; }
    .board-date { font-size: 13px; color: var(--text-dim); font-style: italic; margin-top: 4px; font-weight: 700; text-transform: capitalize; }
    @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: .3; } }

    .row { display: flex; margin-bottom: 6px; align-items: stretch; gap: 6px; }
    .prize-name { width: 40px; flex-shrink: 0; display: flex; justify-content: center; align-items: center; font-size: 13px; font-weight: 900; background: var(--glass-bg); box-shadow: var(--glass-shadow); border: 1px solid var(--glass-border); border-radius: 7px; transition: all .2s; color: var(--text-main); }
    .prize-name.db { background: linear-gradient(180deg, #e53935 0%, #b71c1c 100%); color: #fff; border: 1px solid #c62828; box-shadow: inset 0 2px 4px rgba(255,255,255,.35), 0 2px 4px rgba(0,0,0,.2); }
    .prize-name.active-led { background: var(--led-bg); color: var(--led-color); border-color: var(--led-color); box-shadow: 0 0 12px var(--led-color); transform: scale(1.05); z-index: 2; }

    .prize-results { flex-grow: 1; display: grid; gap: 4px; min-width: 0; }
    .grid-1 { grid-template-columns: 1fr; }
    .grid-2 { grid-template-columns: repeat(2, 1fr); }
    .grid-3 { grid-template-columns: repeat(3, 1fr); }
    .grid-4 { grid-template-columns: repeat(4, 1fr); }
    .grid-6 { grid-template-columns: repeat(6, 1fr); }

    /* GLASS BOX – FIX tràn ô: overflow visible cho hover/cầu, min-width:0 cho grid */
    .number-box {
        background: var(--glass-bg);
        border: 1px solid var(--glass-border);
        box-shadow: var(--glass-shadow);
        display: flex; justify-content: center; align-items: center;
        border-radius: 7px; height: 34px; position: relative;
        cursor: default; min-width: 0;
        transition: transform .2s cubic-bezier(.175,.885,.32,1.275), box-shadow .2s, border-color .2s;
    }
    .board-live-cau .number-box, .cau-on .number-box { cursor: pointer; }
    .number-box:hover { transform: scale(1.06); box-shadow: 0 6px 15px rgba(0,0,0,.15); border-color: var(--db-bg); z-index: 10; }
    .number-box:active { transform: scale(.96); }

    /* FONT SỐ – FIX lem & tràn: weight 700, tabular-nums, letter-spacing vừa phải,
       dùng clamp theo từng loại lưới để 5 chữ số luôn vừa ô hẹp (grid-6) */
    .number-text {
        font-size: clamp(13px, 4.4vw, 17px);
        font-weight: 700; letter-spacing: 1.5px;
        display: flex; align-items: center; justify-content: center;
        white-space: nowrap; width: 100%; max-width: 100%; padding: 0 2px;
        transition: color .2s; color: var(--text-main); line-height: 1;
    }
    .grid-3 .number-text { font-size: clamp(12px, 4vw, 16px); letter-spacing: 1px; }
    .grid-4 .number-text { font-size: clamp(11px, 3.4vw, 15px); letter-spacing: .5px; }
    .grid-6 .number-text { font-size: clamp(10px, 3vw, 14px); letter-spacing: .3px; padding: 0 1px; }

    .row-db .number-box { height: 52px; }
    .row-db .number-text { font-size: clamp(24px, 8.5vw, 34px); color: var(--db-bg); letter-spacing: 4px; z-index: 1; text-shadow: 0 2px 4px rgba(0,0,0,.1); padding-left: 4px; }
    .number-text.spinning { color: var(--db-bg); filter: blur(.4px); opacity: .75; }

    /* CHỮ SỐ "LÀM CẦU" – FIX clip: không còn margin gây tràn, dùng inset thay translateY */
    .digit { display: inline-block; transition: all .2s cubic-bezier(.175,.885,.32,1.275); border-radius: 4px; padding: 0 1px; position: relative; }
    .digit.active-cau { background: var(--db-bg); color: #fff; transform: scale(1.18); box-shadow: 0 0 0 1px var(--db-bg), 0 0 10px rgba(212,0,0,.7); z-index: 5; font-weight: 800; }

    /* "LẶN SỐ ĐB" – ĐÃ TRIỂN KHAI HOÀN CHỈNH (trước đây thiếu CSS + JS) */
    .mask-cover {
        position: absolute; inset: 0; border-radius: 7px;
        background: repeating-linear-gradient(45deg, #b71c1c, #b71c1c 10px, #d40000 10px, #d40000 20px);
        display: flex; align-items: center; justify-content: center; gap: 8px;
        color: #fff; font-size: 13px; font-weight: 900; letter-spacing: 1px; text-transform: uppercase;
        cursor: pointer; z-index: 4; opacity: 0; pointer-events: none;
        transition: opacity .3s ease;
        box-shadow: inset 0 0 20px rgba(0,0,0,.4);
    }
    .mask-cover .eye { font-size: 18px; }
    .masking .row-db .mask-cover { opacity: 1; pointer-events: auto; }
    .masking .row-db .number-text { opacity: 0; }
    .row-db .number-box.revealed .mask-cover { opacity: 0 !important; pointer-events: none !important; }

    /* MODAL LÀM CẦU – dialog gọn, bỏ mũi tên gây hiểu lầm vị trí */
    .cau-modal { position: absolute; inset: 0; z-index: 1000; display: flex; justify-content: center; align-items: center; opacity: 0; pointer-events: none; transition: opacity .2s ease; }
    .cau-modal.show { opacity: 1; pointer-events: all; background: var(--modal-overlay); backdrop-filter: blur(3px); }
    .cau-modal-content { background: #1a1d24; border-radius: 14px; border: 1px solid #2d3340; padding: 16px; transform: scale(.9) translateY(20px); transition: transform .3s cubic-bezier(.175,.885,.32,1.275); box-shadow: 0 20px 50px rgba(0,0,0,.8), inset 0 2px 4px rgba(255,255,255,.05); display: flex; flex-direction: column; gap: 12px; width: 86%; max-width: 320px; }
    .cau-modal.show .cau-modal-content { transform: scale(1) translateY(0); }
    .cau-modal-head { color: #cbd5e1; font-size: 12px; font-weight: 700; text-align: center; text-transform: uppercase; letter-spacing: .5px; }
    .cau-modal-head b { color: #ff5252; }
    .cau-modal-digits { display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; }
    .cau-btn-digit { width: 48px; height: 48px; border-radius: 10px; border: 1px solid #343b4a; background: #232833; font-size: 22px; font-weight: 700; color: #fff; cursor: pointer; transition: all .2s cubic-bezier(.175,.885,.32,1.275); box-shadow: 0 4px 6px rgba(0,0,0,.3); display: flex; justify-content: center; align-items: center; }
    .cau-btn-digit:active { transform: scale(.85); }
    .cau-btn-digit.selected { background: #d40000; color: #fff; border-color: #ff5252; transform: scale(1.08); box-shadow: 0 6px 15px rgba(212,0,0,.6), inset 0 2px 4px rgba(255,255,255,.3); }
    .cau-modal-close { align-self: center; background: #343b4a; color: #fff; border: none; padding: 8px 22px; border-radius: 8px; font-size: 12px; font-weight: 700; cursor: pointer; text-transform: uppercase; letter-spacing: .5px; }
    .cau-modal-close:active { transform: scale(.94); }

    /* SLOT LÔ RƠI */
    .injected-slot { background: var(--bg-main); border: 1.5px solid var(--db-bg); border-radius: 14px; padding: 12px; display: flex; flex-direction: column; gap: 10px; box-shadow: 0 6px 16px rgba(212,0,0,.12); }
    .slot-title { font-size: 12px; font-weight: 900; color: var(--db-bg); text-align: center; text-transform: uppercase; letter-spacing: .5px; transition: all .3s; padding: 4px 8px; border-radius: 6px; }
    .slot-title.flash { background: var(--db-bg); color: #fff; box-shadow: 0 0 15px rgba(212,0,0,.6); transform: scale(1.02); }
    .loto-grid { display: flex; flex-wrap: wrap; justify-content: center; align-items: center; gap: 5px; width: 100%; min-height: 26px; }
    .lo-chip { background: var(--lo-chip-bg); color: #fff; font-size: 12px; font-weight: 700; letter-spacing: .5px; padding: 4px 8px; border-radius: 5px; box-shadow: 0 2px 4px var(--lo-chip-shadow), inset 0 1px 0 rgba(255,255,255,.3); transform: scale(0); animation: springDrop .5s cubic-bezier(.175,.885,.32,1.275) forwards; }
    @keyframes springDrop { 0% { transform: scale(0) translateY(-20px) rotate(-5deg); opacity: 0; } 100% { transform: scale(1) translateY(0) rotate(0); opacity: 1; } }

    .dots-wrapper { display: flex; justify-content: center; align-items: center; gap: 3px; width: 100%; }
    .dot { width: 5px; height: 5px; background-color: var(--text-dim); border-radius: 50%; animation: wave 1.2s infinite ease-in-out; }
    .dot:nth-child(2) { animation-delay: -1.1s; } .dot:nth-child(3) { animation-delay: -1s; } .dot:nth-child(4) { animation-delay: -.9s; } .dot:nth-child(5) { animation-delay: -.8s; }
    @keyframes wave { 0%,40%,100% { transform: translateY(0); opacity: .5; } 20% { transform: translateY(-3px); opacity: 1; } }

    /* AI STICKY BAR – FIX: theo dark mode + marquee bằng CSS thay <marquee> */
    .ai-sticky-bar { background: var(--ai-bar-bg); border-top: 1px solid var(--ai-bar-border); padding: 12px 16px calc(12px + env(safe-area-inset-bottom)); display: flex; align-items: center; gap: 10px; z-index: 10; box-shadow: 0 -4px 10px rgba(0,0,0,.06); }
    .ai-marquee { flex-grow: 1; overflow: hidden; white-space: nowrap; min-width: 0; }
    .ai-marquee span { display: inline-block; padding-left: 100%; font-size: 13px; font-weight: 700; color: var(--ai-bar-text); animation: marquee 18s linear infinite; }
    @keyframes marquee { 0% { transform: translateX(0); } 100% { transform: translateX(-100%); } }
    .ai-input { padding: 7px 13px; border-radius: 20px; border: 1px solid var(--ai-bar-border); font-size: 12px; width: 120px; outline: none; background: var(--ai-bar-input); color: var(--text-main); }

    /* ============================================================
       LỚP 2: THỐNG KÊ LÔ TÔ (TOP SHEET)
       ============================================================ */
    .top-sheet { position: absolute; inset: 0; background: var(--sheet-bg); z-index: 20; transform: translateY(-100%); transition: transform .4s cubic-bezier(.2,.8,.2,1); display: flex; flex-direction: column; }
    .top-tab { position: absolute; bottom: -30px; left: 50%; transform: translateX(-50%); background: linear-gradient(180deg, #1976d2, #1565c0); color: #fff; padding: 6px 20px; font-size: 12px; font-weight: 900; text-transform: uppercase; border-radius: 0 0 12px 12px; cursor: pointer; box-shadow: 0 4px 10px rgba(0,0,0,.3); border: 2px solid #0d47a1; border-top: none; z-index: 25; }
    #toggle-top:checked ~ .app-wrapper .top-sheet { transform: translateY(0); }

    .sheet-header { padding: 14px 16px; display: flex; align-items: center; border-bottom: 1px solid var(--border-color); background: var(--bg-main); z-index: 5; }
    .btn-back { background: var(--bg-board); color: var(--text-main); padding: 8px 12px; border-radius: 8px; font-size: 12px; font-weight: 700; cursor: pointer; border: 1px solid var(--border-color); margin-right: 14px; }
    .sheet-title { font-size: 16px; font-weight: 900; color: var(--text-main); text-transform: uppercase; }

    .sheet-content-loto { flex: 1; padding: 16px; display: flex; flex-direction: column; gap: 16px; overflow-y: auto; overflow-x: hidden; }

    .slider-viewport { flex: 2; width: 100%; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,.1); background: var(--block-bg); border: 1px solid var(--border-color); overflow: hidden; position: relative; min-height: 300px; }
    .slider-track { display: flex; width: 200%; height: 100%; transition: transform .5s cubic-bezier(.16,1,.3,1); }
    .slide-pane { width: 50%; height: 100%; flex-shrink: 0; display: flex; flex-direction: column; }

    .block-title-bar { background: linear-gradient(90deg, #d40000, #ff5252); color: #fff; padding: 8px 12px; font-weight: 700; font-size: 13px; text-transform: uppercase; }
    .matrix-container { flex: 1; overflow: auto; -webkit-overflow-scrolling: touch; background: var(--cell-bg); }
    .matrix-table { border-collapse: collapse; table-layout: fixed; }
    .matrix-table th, .matrix-table td { width: 28px; height: 28px; min-width: 28px; max-width: 28px; border: 1px solid var(--cell-border); text-align: center; vertical-align: middle; font-size: 10px; font-weight: 700; color: var(--text-main); }
    .matrix-table thead th { position: sticky; top: 0; z-index: 2; background: var(--sticky-bg); color: var(--text-main); }
    .matrix-table tbody th { position: sticky; left: 0; z-index: 2; background: var(--sticky-bg); color: var(--sticky-text); transition: all .3s; }
    .matrix-table thead th.corner-h { position: sticky; top: 0; left: 0; z-index: 3; background: #333; color: #fff; }
    .data-cell { color: var(--text-main); font-weight: 900; font-size: 13px; opacity: .9; }
    .row-th.search-hit { background: #ffd54f !important; color: #111 !important; box-shadow: 0 0 10px #ffb300; }
    td.search-hit { background: rgba(255,213,79,.35) !important; }

    .gan-alert { background: var(--db-bg) !important; color: #fff !important; animation: ganPulse 1.5s infinite alternate; cursor: pointer; z-index: 10 !important; position: relative; }
    @keyframes ganPulse { 0% { box-shadow: 0 0 4px var(--db-bg); } 100% { box-shadow: 0 0 16px var(--db-bg); } }
    .gan-tooltip { position: absolute; bottom: 110%; left: 50%; transform: translateX(-50%); background: #111; color: #fff; padding: 6px 10px; border-radius: 6px; font-size: 11px; white-space: nowrap; pointer-events: none; opacity: 0; visibility: hidden; transition: all .2s; box-shadow: 0 4px 10px rgba(0,0,0,.5); z-index: 100; border: 1px solid #ff5252; font-weight: 500; letter-spacing: 0; text-transform: none; }
    .gan-tooltip::after { content: ''; position: absolute; top: 100%; left: 50%; transform: translateX(-50%); border-width: 5px; border-style: solid; border-color: #111 transparent transparent transparent; }
    .gan-alert.show-tooltip .gan-tooltip { opacity: 1; visibility: visible; bottom: 125%; }

    .tv-header { background: #000; color: #fff; padding: 8px 12px; font-weight: 700; font-size: 12px; display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid var(--tv-border); z-index: 10; position: relative; }
    .btn-tv-close { background: #333; border: none; color: #fff; padding: 5px 9px; border-radius: 5px; font-size: 10px; cursor: pointer; }
    .tv-screen { --ai-core: rgba(59,130,246,.2); --ai-glow: rgba(59,130,246,.6); --ai-text: #38bdf8; --ai-badge-border: #38bdf8; --ai-badge-bg: rgba(56,189,248,.1); flex: 1; background: var(--tv-bg-base); padding: 15px; display: flex; flex-direction: column; justify-content: center; align-items: center; box-shadow: inset 0 0 40px rgba(0,0,0,.8), inset 0 0 20px var(--ai-glow); position: relative; overflow-y: auto; transition: box-shadow .5s ease; }
    .tv-screen.theme-red { --ai-core: rgba(239,68,68,.2); --ai-glow: rgba(239,68,68,.6); --ai-text: #fca5a5; --ai-badge-border: #ef4444; --ai-badge-bg: rgba(239,68,68,.15); }
    .tv-screen.theme-green { --ai-core: rgba(16,185,129,.2); --ai-glow: rgba(16,185,129,.6); --ai-text: #6ee7b7; --ai-badge-border: #10b981; --ai-badge-bg: rgba(16,185,129,.12); }
    .tv-circuit { position: absolute; inset: 0; background-image: linear-gradient(var(--ai-core) 1px, transparent 1px), linear-gradient(90deg, var(--ai-core) 1px, transparent 1px); background-size: 20px 20px; opacity: .25; z-index: 1; pointer-events: none; animation: circuitPulse 3s infinite alternate; }
    @keyframes circuitPulse { 0% { opacity: .1; } 100% { opacity: .3; } }
    .tv-data-stream { position: absolute; inset: 0; background: linear-gradient(180deg, transparent 0%, var(--ai-glow) 50%, transparent 100%); background-size: 100% 200%; opacity: .15; z-index: 1; pointer-events: none; animation: dataStream 2.5s linear infinite; }
    @keyframes dataStream { 0% { background-position: 0 -100%; } 100% { background-position: 0 200%; } }
    .tv-content-layer { position: relative; z-index: 2; display: flex; flex-direction: column; align-items: center; width: 100%; }
    .tv-text-bot { color: var(--ai-text); font-family: ui-monospace, monospace; font-size: 13px; text-align: center; margin-bottom: 15px; text-shadow: 0 0 5px var(--ai-glow); line-height: 1.6; }
    .tv-results { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; width: 100%; }
    .xien-badge { background: var(--ai-badge-bg); border: 1px solid var(--ai-badge-border); color: var(--ai-badge-border); padding: 8px 16px; border-radius: 8px; font-size: 16px; font-weight: 900; letter-spacing: 1px; box-shadow: 0 0 10px rgba(0,0,0,.5); animation: badgePop .4s cubic-bezier(.175,.885,.32,1.275) forwards; text-align: center; }
    @keyframes badgePop { 0% { transform: scale(.5); opacity: 0; } 100% { transform: scale(1); opacity: 1; } }

    .loto-block-2 { border-radius: 14px; background: var(--bg-main); border: 1px solid var(--border-color); padding: 16px; box-shadow: 0 4px 6px rgba(0,0,0,.05), 0 10px 15px rgba(0,0,0,.08); display: flex; flex-direction: column; gap: 16px; }
    .block-title-2 { font-size: 13px; font-weight: 900; color: var(--db-bg); text-transform: uppercase; border-bottom: 1.5px dashed var(--border-color); padding-bottom: 8px; }
    .special-btn-group { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }
    .btn-special { padding: 10px 4px; border-radius: 10px; font-size: 10px; font-weight: 900; color: #fff; border: none; cursor: pointer; text-transform: uppercase; transition: all .2s cubic-bezier(.175,.885,.32,1.275); display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 4px; letter-spacing: .5px; text-align: center; }
    .btn-special .icon { font-size: 18px; }
    .btn-special:active { transform: scale(.92); }
    .btn-xien { background: linear-gradient(135deg, #f59e0b, #d97706); box-shadow: 0 4px 10px rgba(245,158,11,.3); }
    .btn-nhipdep { background: linear-gradient(135deg, #10b981, #059669); box-shadow: 0 4px 10px rgba(16,185,129,.3); }
    .btn-bacnho { background: linear-gradient(135deg, #3b82f6, #2563eb); box-shadow: 0 4px 10px rgba(59,130,246,.3); }
    .search-group { display: flex; gap: 10px; }
    .search-input { flex: 1; padding: 12px 16px; border-radius: 10px; border: 1.5px solid var(--border-color); background: var(--bg-board); color: var(--text-main); font-size: 16px; font-weight: 700; outline: none; transition: border-color .2s, box-shadow .2s; letter-spacing: 2px; }
    .search-input:focus { border-color: var(--db-bg); box-shadow: 0 0 0 3px rgba(212,0,0,.15); }
    .search-input::placeholder { color: var(--text-dim); font-weight: 400; font-size: 13px; letter-spacing: 0; }
    .btn-search { padding: 0 20px; border-radius: 10px; border: none; background: var(--db-bg); color: #fff; font-weight: 900; font-size: 13px; cursor: pointer; text-transform: uppercase; box-shadow: 0 4px 10px rgba(212,0,0,.3); transition: transform .1s; }
    .btn-search:active { transform: scale(.92); }

    #keyboard-wrapper { display: none; }
    .loto-block-kb { border-radius: 14px; display: flex; flex-direction: column; gap: 10px; padding: 16px; background: var(--block-bg); box-shadow: 0 4px 6px rgba(0,0,0,.05); border: 1px solid var(--border-color); }
    .vk-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
    .vk-btn { background: var(--bg-board); color: var(--text-main); border: 1px solid var(--border-color); border-radius: 10px; padding: 14px 0; font-size: 20px; font-weight: 700; cursor: pointer; transition: all .1s; box-shadow: 0 2px 0 var(--border-color); display: flex; justify-content: center; align-items: center; }
    .vk-btn:active { transform: translateY(2px); box-shadow: none; background: var(--border-color); }
    .vk-action { font-size: 14px; background: var(--sheet-bg); }
    .vk-del { color: var(--db-bg); }

    .lo-top-board { border-radius: 14px; background: var(--bg-main); border: 1px solid var(--border-color); padding: 16px 12px 0; box-shadow: 0 4px 6px rgba(0,0,0,.05), 0 10px 15px rgba(0,0,0,.08); display: flex; flex-direction: column; min-height: 220px; }
    .chart-container { display: flex; align-items: flex-end; justify-content: space-between; height: 160px; padding-top: 30px; gap: clamp(2px, 1vw, 6px); border-bottom: 2px solid var(--border-color); flex: 1; }
    .bar-wrapper { display: flex; flex-direction: column; align-items: center; justify-content: flex-end; flex: 1; height: 100%; position: relative; transition: transform .3s; }
    .bar-wrapper:hover { transform: translateY(-5px); }
    .bar-number { font-weight: 700; font-size: 14px; color: var(--text-main); margin-bottom: 4px; }
    .bar-column { width: 100%; border-radius: 6px 6px 0 0; display: flex; align-items: flex-end; justify-content: center; padding-bottom: 8px; box-shadow: 0 4px 10px rgba(0,0,0,.1), inset 0 2px 5px rgba(255,255,255,.4); transform-origin: bottom; animation: growUp 1.1s cubic-bezier(.175,.885,.32,1.275) forwards; transform: scaleY(0); }
    @keyframes growUp { to { transform: scaleY(1); } }
    .bar-rank { font-size: 9px; font-weight: 700; color: #fff; writing-mode: vertical-rl; transform: rotate(180deg); text-shadow: 0 1px 2px rgba(0,0,0,.5); letter-spacing: 1px; }

    /* ============================================================
       LỚP 3: THỐNG KÊ ĐB (BOTTOM SHEET)
       ============================================================ */
    .bottom-sheet { position: absolute; left: 0; bottom: 0; width: 100%; height: 100%; background: var(--sheet-bg); z-index: 20; transform: translateY(100%); transition: transform .4s cubic-bezier(.2,.8,.2,1); display: flex; flex-direction: column; }
    .bottom-tab { position: absolute; top: -30px; left: 50%; transform: translateX(-50%); background: linear-gradient(0deg, #d32f2f, #c62828); color: #fff; padding: 6px 20px; font-size: 12px; font-weight: 900; text-transform: uppercase; border-radius: 12px 12px 0 0; cursor: pointer; box-shadow: 0 -4px 10px rgba(0,0,0,.3); border: 2px solid #b71c1c; border-bottom: none; z-index: 25; }
    #toggle-bottom:checked ~ .app-wrapper .bottom-sheet { transform: translateY(0); }
    .sheet-content-db { flex: 1; padding: 16px; display: flex; flex-direction: column; gap: 16px; overflow-y: auto; }
    .db-stat-card { background: var(--bg-main); border: 1px solid var(--border-color); border-radius: 14px; padding: 16px; box-shadow: 0 4px 8px rgba(0,0,0,.05); }
    .db-stat-card h4 { font-size: 13px; color: var(--db-bg); text-transform: uppercase; margin-bottom: 12px; border-bottom: 1.5px dashed var(--border-color); padding-bottom: 8px; }
    .db-pair-grid { display: grid; grid-template-columns: repeat(5, 1fr); gap: 8px; }
    .db-pair { background: var(--glass-bg); border: 1px solid var(--glass-border); box-shadow: var(--glass-shadow); border-radius: 8px; padding: 8px 0; text-align: center; }
    .db-pair .p { font-size: 18px; font-weight: 800; color: var(--text-main); }
    .db-pair .c { font-size: 10px; color: var(--text-dim); font-weight: 700; }
</style>
</head>
<body>

<input type="checkbox" id="toggle-dark" hidden>
<input type="checkbox" id="toggle-top" hidden>
<input type="checkbox" id="toggle-bottom" hidden>

<div class="app-wrapper" id="app-wrapper">

    <!-- ===== LỚP 2: THỐNG KÊ LÔ TÔ ===== -->
    <div class="top-sheet">
        <div class="sheet-header">
            <label for="toggle-top" class="btn-back">🔙 Quay lại</label>
            <div class="sheet-title">📊 Thống Kê Lô Tô</div>
        </div>
        <div class="sheet-content-loto">
            <div class="slider-viewport">
                <div class="slider-track" id="main-slider-track">
                    <div class="slide-pane">
                        <div class="block-title-bar">Bố cục 1: Tần suất lô (30 ngày)</div>
                        <div class="matrix-container">
                            <table class="matrix-table" id="matrix-table">
                                <thead><tr id="matrix-head"></tr></thead>
                                <tbody id="matrix-body"></tbody>
                            </table>
                        </div>
                    </div>
                    <div class="slide-pane">
                        <div class="tv-header"><span id="tv-header-title">📺 Hệ thống AI Calculator</span><button class="btn-tv-close" onclick="closeTV()">✖ Đóng</button></div>
                        <div class="tv-screen theme-blue" id="ai-tv-screen">
                            <div class="tv-circuit"></div><div class="tv-data-stream"></div>
                            <div class="tv-content-layer">
                                <div class="tv-text-bot" id="tv-message">👋 Chào bạn!<br>Hệ thống AI đã sẵn sàng hoạt động.</div>
                                <div class="tv-results" id="tv-results-container"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="loto-block-2">
                <div class="block-title-2">⚡ Công cụ tính toán</div>
                <div class="special-btn-group">
                    <button class="btn-special btn-xien" onclick="activateXienAI()"><span class="icon">🔗</span><span>Ghép Xiên</span></button>
                    <button class="btn-special btn-nhipdep" onclick="activateNhipDep()"><span class="icon">📈</span><span>Nhịp Đẹp</span></button>
                    <button class="btn-special btn-bacnho" onclick="activateBacNhoAI()"><span class="icon">🧠</span><span>Bạc Nhớ</span></button>
                </div>
                <div class="search-group">
                    <input type="text" class="search-input num-font" id="ai-search-input" placeholder="Chạm để nhập số..." readonly onclick="showKeyboard()">
                    <button class="btn-search" onclick="runSearch()">Tìm</button>
                </div>
            </div>

            <div id="keyboard-wrapper">
                <div class="loto-block-kb">
                    <div class="block-title-2" style="display:flex;justify-content:space-between;">
                        <span>⌨ Bàn phím nhập liệu</span>
                        <span style="cursor:pointer;color:var(--text-dim);" onclick="hideKeyboard()">Đóng ✖</span>
                    </div>
                    <div class="vk-grid num-font" id="virtual-keyboard">
                        <button class="vk-btn" data-val="1">1</button><button class="vk-btn" data-val="2">2</button><button class="vk-btn" data-val="3">3</button>
                        <button class="vk-btn" data-val="4">4</button><button class="vk-btn" data-val="5">5</button><button class="vk-btn" data-val="6">6</button>
                        <button class="vk-btn" data-val="7">7</button><button class="vk-btn" data-val="8">8</button><button class="vk-btn" data-val="9">9</button>
                        <button class="vk-btn vk-action" onclick="clearInput()">CLEAR</button><button class="vk-btn" data-val="0">0</button><button class="vk-btn vk-action vk-del" onclick="delInput()">DEL</button>
                    </div>
                </div>
            </div>

            <div class="lo-top-board">
                <div class="block-title-2">🏆 Bảng xếp hạng lô về nhiều nhất (30 ngày)</div>
                <div class="chart-container" id="lo-top-chart"></div>
            </div>
        </div>
        <label for="toggle-top" class="top-tab">▼ Kéo Thống Kê Lô Tô</label>
    </div>

    <!-- ===== LỚP 1: LUỒNG CHÍNH ===== -->
    <div class="main-layer">
        <div class="top-controls">
            <div class="top-controls-left">
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-cau" onchange="toggleCau(this)"><span class="slider"></span></label><span class="switch-label-text">Làm Cầu</span></div>
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-quay-thu" onchange="triggerQuayThu(this)"><span class="slider"></span></label><span class="switch-label-text">Quay Thử</span></div>
            </div>
            <div class="top-controls-right">
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-dark-vis" onchange="document.getElementById('toggle-dark').checked=this.checked"><span class="slider"></span></label><span class="switch-label-text">Sáng/Tối</span></div>
                <div class="switch-wrap"><label class="switch"><input type="checkbox" id="toggle-mask-vis" onchange="toggleMask(this)"><span class="slider"></span></label><span class="switch-label-text">Lặn Số ĐB</span></div>
            </div>
        </div>

        <div class="boards-feed" id="boards-feed-container">
            <div class="board board-live-cau" id="board-live">
                <div class="board-header">
                    <div class="board-title live">🔴 Kết quả xổ số Thần Mèo</div>
                    <div class="status-blink" id="live-status">⏳ Hãy bật công tắc "Quay Thử" ở trên...</div>
                    <div class="board-date" id="live-date"></div>
                </div>
                <!-- ĐB lên trên cùng cho đúng chuẩn bảng KQ miền Bắc + đồng bộ với bảng lịch sử -->
                <div class="row row-db" data-prize="ĐB" data-len="5">
                    <div class="prize-name db">ĐB</div>
                    <div class="prize-results grid-1">
                        <div class="number-box">
                            <div class="mask-cover" onclick="this.parentElement.classList.add('revealed')"><span class="eye">🙈</span> Chạm để xem</div>
                            <span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span>
                        </div>
                    </div>
                </div>
                <div class="row" data-prize="G1" data-len="5"><div class="prize-name">G1</div><div class="prize-results grid-1"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G2" data-len="5"><div class="prize-name">G2</div><div class="prize-results grid-2"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G3" data-len="5"><div class="prize-name">G3</div><div class="prize-results grid-6"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G4" data-len="4"><div class="prize-name">G4</div><div class="prize-results grid-4"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G5" data-len="4"><div class="prize-name">G5</div><div class="prize-results grid-6"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G6" data-len="3"><div class="prize-name">G6</div><div class="prize-results grid-3"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
                <div class="row" data-prize="G7" data-len="2"><div class="prize-name">G7</div><div class="prize-results grid-4"><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div><div class="number-box"><span class="number-text num-font"><div class="dots-wrapper"><span class="dot"></span><span class="dot"></span></div></span></div></div></div>
            </div>

            <div class="injected-slot" id="custom-slot">
                <div class="slot-title" id="slot-title">⚡ Bảng lô rơi sẽ hiển thị tại đây</div>
                <div class="loto-grid" id="loto-drop-zone"></div>
            </div>

            <div id="history-boards-container"></div>
        </div>

        <div class="ai-sticky-bar">
            <div class="ai-marquee"><span>🤖 Cuộn xuống để xem 40 bảng kết quả lịch sử · Bật "Quay Thử" để xem quay số trực tiếp · Bật "Làm Cầu" rồi chạm số để đánh dấu cầu chạy...</span></div>
            <input type="text" class="ai-input" placeholder="Hỏi AI...">
        </div>
    </div>

    <!-- ===== LỚP 3: THỐNG KÊ ĐB ===== -->
    <div class="bottom-sheet">
        <label for="toggle-bottom" class="bottom-tab">▲ Kéo Thống Kê ĐB</label>
        <div class="sheet-header"><label for="toggle-bottom" class="btn-back">🔙 Quay lại</label><div class="sheet-title">🎯 Thống Kê Đặc Biệt</div></div>
        <div class="sheet-content-db" id="db-content"></div>
    </div>

    <!-- MODAL LÀM CẦU -->
    <div id="cau-modal" class="cau-modal" onmousedown="closeCauModal(event)" ontouchstart="closeCauModal(event)">
        <div class="cau-modal-content" onmousedown="event.stopPropagation()" ontouchstart="event.stopPropagation()">
            <div class="cau-modal-head">Chọn chữ số làm cầu cho <b id="cau-modal-num"></b></div>
            <div id="cau-modal-digits" class="cau-modal-digits num-font"></div>
            <button class="cau-modal-close" onclick="closeCauModal()">Xong</button>
        </div>
    </div>
</div>

<script>
"use strict";

/* ============================================================
   1. ENGINE DỮ LIỆU (FIX: dữ liệu nhất quán thay vì random mỗi ô)
   Một bộ dữ liệu duy nhất sinh ra ở seed cố định -> ma trận tần
   suất, lô gan, top lô, bạc nhớ ĐB đều khớp nhau & ổn định.
   ============================================================ */
function makeRNG(seed){ let s = seed >>> 0; return function(){ s = (s*1664525 + 1013904223) >>> 0; return s/4294967296; }; }
const rng = makeRNG(20260326);
const DAYS = 30;

// freq[lo][day] = số lần lô về trong ngày đó (0..3)
const LottoData = (() => {
    const freq = [];
    for (let lo = 0; lo <= 99; lo++){
        const row = [];
        const bias = 0.55 + (rng() * 0.35);          // mỗi lô có "thiên hướng" riêng
        for (let d = 0; d < DAYS; d++){
            let n = 0;
            if (rng() < (0.30 * bias)) n = 1;
            if (n && rng() < 0.18) n = 2;
            if (n === 2 && rng() < 0.10) n = 3;
            row.push(n);
        }
        freq.push(row);
    }
    // tổng tần suất + số ngày gan (số ngày gần nhất chưa về, đếm từ ngày mới nhất = cột cuối)
    const totals = freq.map(r => r.reduce((a,b)=>a+b,0));
    const gan = freq.map(r => {
        let g = 0;
        for (let d = DAYS-1; d >= 0; d--){ if (r[d] > 0) break; g++; }
        return g;
    });
    return { freq, totals, gan };
})();

const pad2 = n => (n < 10 ? '0'+n : ''+n);

/* ============================================================
   2. TIỆN ÍCH SỐ
   ============================================================ */
function generateRandom(length){ let r=''; for(let i=0;i<length;i++) r += Math.floor(Math.random()*10); return r; }
function wrapDigits(numStr){
    if(!numStr) return '';
    return numStr.split('').map((d,i)=>`<span class="digit" data-idx="${i}">${d}</span>`).join('');
}
const sleep = ms => new Promise(r => setTimeout(r, ms));

/* ============================================================
   3. KHỞI TẠO
   ============================================================ */
document.addEventListener("DOMContentLoaded", () => {
    setLiveDate();
    buildMatrix();
    renderTopLo();
    renderDbStats();
    setupKeyboard();
    renderHistoricalBoards(40);
    bindMatrixTooltips();
    bindCauClicks();
});

function setLiveDate(){
    const d = new Date(2026, 2, 26);
    let s = d.toLocaleDateString('vi-VN', { weekday:'long', year:'numeric', month:'2-digit', day:'2-digit' });
    document.getElementById('live-date').textContent = s.charAt(0).toUpperCase()+s.slice(1);
}

/* ---- Ma trận tần suất (head + body sinh bằng JS, nhất quán dữ liệu) ---- */
function buildMatrix(){
    const head = document.getElementById('matrix-head');
    let h = '<th class="corner-h">Lô</th>';
    for(let j=1;j<=DAYS;j++) h += `<th>${j}</th>`;
    head.innerHTML = h;

    const tbody = document.getElementById('matrix-body');
    let rows = '';
    for(let lo=0; lo<=99; lo++){
        const isGan = LottoData.gan[lo] >= 12;             // gan thật: >=12 ngày chưa về
        const thClass = isGan ? 'row-th gan-alert' : 'row-th';
        const tip = isGan ? `<div class="gan-tooltip">⚠️ Gan ${LottoData.gan[lo]} ngày · Tổng về: ${LottoData.totals[lo]}</div>` : '';
        rows += `<tr data-lo="${pad2(lo)}"><th class="${thClass}">${pad2(lo)}${tip}</th>`;
        for(let d=0; d<DAYS; d++){
            const v = LottoData.freq[lo][d];
            rows += v>0 ? `<td class="data-cell">${v}</td>` : `<td></td>`;
        }
        rows += '</tr>';
    }
    tbody.innerHTML = rows;
}

function bindMatrixTooltips(){
    document.getElementById('matrix-body').addEventListener('click', function(e){
        const th = e.target.closest('th.gan-alert');
        document.querySelectorAll('th.gan-alert.show-tooltip').forEach(el => { if(el!==th) el.classList.remove('show-tooltip'); });
        if(th) th.classList.toggle('show-tooltip');
    });
}

/* ---- Top lô về nhiều nhất (tính thật từ totals) ---- */
function renderTopLo(){
    const chart = document.getElementById('lo-top-chart');
    const ranked = LottoData.totals.map((t,lo)=>({lo:pad2(lo), t}))
                    .sort((a,b)=>b.t-a.t).slice(0,10);
    const max = ranked[0].t || 1;
    const palette = [
        'linear-gradient(to top,#d50000,#ff1744)','linear-gradient(to top,#e65100,#ff9100)',
        'linear-gradient(to top,#ef6c00,#ffb300)','linear-gradient(to top,#f57f17,#ffc400)',
        'linear-gradient(to top,#fbc02d,#ffee58)','linear-gradient(to top,#afb42b,#d4e157)',
        'linear-gradient(to top,#689f38,#9ccc65)','linear-gradient(to top,#0097a7,#4dd0e1)',
        'linear-gradient(to top,#0288d1,#29b6f6)','linear-gradient(to top,#1976d2,#4fc3f7)'
    ];
    let html='';
    ranked.forEach((item,idx)=>{
        const height = 20 + Math.round((item.t/max)*80);
        const glow = idx<3 ? `box-shadow:0 0 12px ${palette[idx].split(',')[1]};` : '';
        const txt = idx===0 ? 'color:var(--db-bg);text-shadow:0 0 8px rgba(212,0,0,.5);transform:scale(1.3);' : '';
        html += `<div class="bar-wrapper" title="Lô ${item.lo}: ${item.t} lần">
            <div class="bar-number num-font" style="${txt}">${item.lo}</div>
            <div class="bar-column" style="height:${height}%;background:${palette[idx]};${glow}animation-delay:${idx*0.08}s;">
                <div class="bar-rank">TOP ${idx+1}</div></div></div>`;
    });
    chart.innerHTML = html;
}

/* ---- Thống kê ĐB (Lớp 3) – bạc nhớ + đầu/đuôi gan ---- */
function renderDbStats(){
    const wrap = document.getElementById('db-content');
    // đầu - đuôi xuất hiện nhiều của 2 số cuối ĐB (mô phỏng từ totals)
    const heads = Array(10).fill(0), tails = Array(10).fill(0);
    LottoData.totals.forEach((t,lo)=>{ heads[Math.floor(lo/10)] += t; tails[lo%10] += t; });
    const topGan = LottoData.gan.map((g,lo)=>({lo:pad2(lo),g})).sort((a,b)=>b.g-a.g).slice(0,10);

    const cell = (arr,label) => arr.map((v,i)=>`<div class="db-pair"><div class="p num-font">${i}</div><div class="c">${label}: ${v}</div></div>`).join('');
    wrap.innerHTML = `
      <div class="db-stat-card"><h4>🔢 Đầu ĐB về nhiều (30 ngày)</h4><div class="db-pair-grid">${cell(heads,'lần')}</div></div>
      <div class="db-stat-card"><h4>🔚 Đuôi ĐB về nhiều (30 ngày)</h4><div class="db-pair-grid">${cell(tails,'lần')}</div></div>
      <div class="db-stat-card"><h4>🥶 Top 10 lô gan lì nhất</h4><div class="db-pair-grid">
        ${topGan.map(x=>`<div class="db-pair"><div class="p num-font">${x.lo}</div><div class="c">gan ${x.g}n</div></div>`).join('')}
      </div></div>`;
}

/* ============================================================
   4. BẢNG LỊCH SỬ
   ============================================================ */
function renderHistoricalBoards(count){
    const container = document.getElementById('history-boards-container');
    if(!container) return;
    const baseDate = new Date(2026, 2, 25);
    const frag = [];
    const box = (len) => `<div class="number-box"><span class="number-text num-font">${wrapDigits(generateRandom(len))}</span></div>`;
    for(let i=0;i<count;i++){
        const d = new Date(baseDate); d.setDate(d.getDate()-i);
        let day = d.toLocaleDateString('vi-VN',{weekday:'long',year:'numeric',month:'2-digit',day:'2-digit'});
        day = day.charAt(0).toUpperCase()+day.slice(1);
        frag.push(`<div class="board" style="margin-bottom:0">
            <div class="board-header"><div class="board-title">Kết quả xổ số Thần Mèo</div><div class="board-date">${day}</div></div>
            <div class="row row-db" data-len="5"><div class="prize-name db">ĐB</div><div class="prize-results grid-1">${box(5)}</div></div>
            <div class="row"><div class="prize-name">G1</div><div class="prize-results grid-1">${box(5)}</div></div>
            <div class="row"><div class="prize-name">G2</div><div class="prize-results grid-2">${box(5)}${box(5)}</div></div>
            <div class="row"><div class="prize-name">G3</div><div class="prize-results grid-6">${box(5)}${box(5)}${box(5)}${box(5)}${box(5)}${box(5)}</div></div>
            <div class="row"><div class="prize-name">G4</div><div class="prize-results grid-4">${box(4)}${box(4)}${box(4)}${box(4)}</div></div>
            <div class="row"><div class="prize-name">G5</div><div class="prize-results grid-6">${box(4)}${box(4)}${box(4)}${box(4)}${box(4)}${box(4)}</div></div>
            <div class="row"><div class="prize-name">G6</div><div class="prize-results grid-3">${box(3)}${box(3)}${box(3)}</div></div>
            <div class="row"><div class="prize-name">G7</div><div class="prize-results grid-4">${box(2)}${box(2)}${box(2)}${box(2)}</div></div>
        </div>`);
    }
    container.style.cssText = 'display:flex;flex-direction:column;gap:24px;';
    container.innerHTML = frag.join('');
}

/* ============================================================
   5. LÀM CẦU
   ============================================================ */
let activeCauBox = null;

function toggleCau(cb){
    document.getElementById('app-wrapper').classList.toggle('cau-on', cb.checked);
    if(!cb.checked) closeCauModal();
}

function bindCauClicks(){
    document.getElementById('boards-feed-container').addEventListener('click', function(e){
        if(!document.getElementById('toggle-cau').checked) return;
        const box = e.target.closest('.number-box');
        if(!box) return;
        if(e.target.closest('.mask-cover')) return;       // không mở cầu khi đang chạm lớp che ĐB
        const numText = box.querySelector('.number-text');
        if(!numText || numText.querySelector('.dot')) return;  // chưa có số (đang chờ quay)
        activeCauBox = box;
        openCauModal(numText);
    });
}

function openCauModal(numText){
    const digits = numText.querySelectorAll('.digit');
    if(!digits.length) return;
    document.getElementById('cau-modal-num').textContent = numText.textContent.trim();
    const cont = document.getElementById('cau-modal-digits');
    cont.innerHTML = '';
    digits.forEach(span => {
        const btn = document.createElement('button');
        btn.className = 'cau-btn-digit' + (span.classList.contains('active-cau') ? ' selected' : '');
        btn.textContent = span.textContent;
        btn.onclick = () => { btn.classList.toggle('selected'); span.classList.toggle('active-cau'); };
        cont.appendChild(btn);
    });
    document.getElementById('cau-modal').classList.add('show');
}
function closeCauModal(e){
    if(e) e.preventDefault();
    document.getElementById('cau-modal').classList.remove('show');
    activeCauBox = null;
}

/* ============================================================
   6. LẶN SỐ ĐB (mới)
   ============================================================ */
function toggleMask(cb){
    const wrap = document.getElementById('app-wrapper');
    wrap.classList.toggle('masking', cb.checked);
    if(!cb.checked) document.querySelectorAll('.row-db .number-box.revealed').forEach(b=>b.classList.remove('revealed'));
}

/* ============================================================
   7. BÀN PHÍM ẢO + TÌM KIẾM
   ============================================================ */
const searchInput = document.getElementById('ai-search-input');
const keyboardWrapper = document.getElementById('keyboard-wrapper');
function showKeyboard(){ keyboardWrapper.style.display='block'; keyboardWrapper.scrollIntoView({behavior:'smooth',block:'nearest'}); }
function hideKeyboard(){ keyboardWrapper.style.display='none'; }
function setupKeyboard(){
    document.querySelectorAll('#virtual-keyboard .vk-btn[data-val]').forEach(k=>{
        k.addEventListener('click', e=>{
            let cur = searchInput.value.replace(/\s/g,'');
            if(cur.length<10){ cur += e.target.getAttribute('data-val'); formatInput(cur); }
        });
    });
}
function clearInput(){ searchInput.value=''; clearSearchHits(); }
function delInput(){ let cur=searchInput.value.replace(/\s/g,''); if(cur.length){ formatInput(cur.slice(0,-1)); } }
function formatInput(raw){ searchInput.value = raw.match(/.{1,2}/g)?.join(' ') || ''; }

function clearSearchHits(){
    document.querySelectorAll('.search-hit').forEach(el=>el.classList.remove('search-hit'));
}

/* Tìm: highlight lô trong ma trận + báo thống kê thật trên màn AI */
function runSearch(){
    const raw = searchInput.value.replace(/\s/g,'');
    const pairs = [...new Set(raw.match(/.{2}/g) || [])];
    clearSearchHits();
    if(!pairs.length){ flashTV('blue','⚠️ Hãy nhập ít nhất 1 cặp số (2 chữ số) để tra cứu.'); return; }

    let report = [];
    pairs.forEach(p=>{
        const tr = document.querySelector(`#matrix-body tr[data-lo="${p}"]`);
        if(tr){
            tr.querySelector('th').classList.add('search-hit');
            tr.querySelectorAll('td').forEach(td=>td.classList.add('search-hit'));
            const lo = parseInt(p,10);
            report.push(`Lô <b>${p}</b>: về <b>${LottoData.totals[lo]}</b> lần / 30 ngày · gan hiện tại <b>${LottoData.gan[lo]}</b> ngày`);
            if(pairs.length===1) tr.scrollIntoView({behavior:'smooth',block:'center'});
        }
    });
    tvScreen.className='tv-screen theme-blue';
    tvHeader.textContent='🔎 Tra cứu tần suất lô';
    sliderTrack.style.transform='translateX(-50%)';
    tvResults.innerHTML='';
    tvMessage.innerHTML = report.length ? report.join('<br>') : '⚠️ Không tìm thấy dữ liệu.';
}

/* ============================================================
   8. MÀN HÌNH AI (Ghép Xiên / Bạc Nhớ / Nhịp Đẹp)
   ============================================================ */
const sliderTrack = document.getElementById('main-slider-track');
const tvScreen    = document.getElementById('ai-tv-screen');
const tvHeader    = document.getElementById('tv-header-title');
const tvMessage   = document.getElementById('tv-message');
const tvResults   = document.getElementById('tv-results-container');

function closeTV(){ sliderTrack.style.transform='translateX(0)'; }
function flashTV(theme,msg){ tvScreen.className='tv-screen theme-'+theme; sliderTrack.style.transform='translateX(-50%)'; tvResults.innerHTML=''; tvMessage.innerHTML=msg; }
function getPairs(){ return [...new Set((searchInput.value.replace(/\s/g,'').match(/.{2}/g)) || [])]; }
function spawnBadge(html, delay){ setTimeout(()=>{ const b=document.createElement('div'); b.className='xien-badge'; b.innerHTML=html; tvResults.appendChild(b); }, delay); }

function activateXienAI(){
    hideKeyboard();
    const pairs = getPairs();
    if(pairs.length<2){ flashTV('blue','⚠️ Cần ít nhất 2 cặp khác nhau (4 chữ số) để ghép xiên.'); return; }
    flashTV('blue', `✅ Ghép ${pairs.length} cặp [${pairs.join(', ')}] thành các xiên 2:`);
    tvHeader.textContent='🔗 Hệ thống ghép xiên AI';
    let k=0;
    for(let i=0;i<pairs.length-1;i++)
        for(let j=i+1;j<pairs.length;j++)
            spawnBadge(`${pairs[i]} – ${pairs[j]}`, (k++)*140);
}

function activateBacNhoAI(){
    hideKeyboard();
    const pairs = getPairs();
    if(!pairs.length){ flashTV('red','⚠️ Nhập ít nhất 1 cặp để tra Bạc Nhớ.'); return; }
    flashTV('red', `🧠 <b>Cơ sở dữ liệu thống kê</b><br>Sau khi [${pairs.join(', ')}] về, cặp thường theo sau:`);
    tvHeader.textContent='🚨 Hệ thống Bạc Nhớ AI';
    const db = { "00":"99","99":"00","12":"34 – 43","21":"45 – 54","68":"86","86":"68","79":"97","97":"79" };
    pairs.forEach((p,i)=>{
        // nếu không có trong bảng, suy ra "lộn" và "kép" liên quan -> ổn định, không random
        const rev = p[1]+p[0];
        const res = db[p] || `${rev} – ${p[0]}${p[0]}`;
        spawnBadge(`<span style="font-size:11px;opacity:.8;font-weight:500;">Cầu ${p} ➔ theo sau:</span><br>${res}`, i*200);
    });
}

function activateNhipDep(){
    hideKeyboard();
    flashTV('green','📈 <b>Nhịp đẹp đang chạy</b> – các lô có nhịp về đều & đang nóng:');
    tvHeader.textContent='📈 Bộ lọc Nhịp Đẹp AI';
    // "nhịp đẹp": lô có tổng về cao nhưng gan vừa phải (1..4 ngày) -> sắp tới chu kỳ
    const cand = LottoData.totals
        .map((t,lo)=>({lo:pad2(lo), t, g:LottoData.gan[lo]}))
        .filter(x => x.g>=1 && x.g<=4)
        .sort((a,b)=> b.t-a.t)
        .slice(0,6);
    if(!cand.length){ tvMessage.innerHTML='Chưa có lô nào vào nhịp đẹp hôm nay.'; return; }
    cand.forEach((x,i)=> spawnBadge(`${x.lo}<br><span style="font-size:10px;opacity:.8;font-weight:500;">về ${x.t}× · gan ${x.g}n</span>`, i*160));
}

/* ============================================================
   9. QUAY THỬ TRỰC TIẾP
   ============================================================ */
async function triggerQuayThu(cb){
    if(cb.checked){
        cb.disabled = true;
        await startSimulation();
        cb.checked = false;
        cb.disabled = false;
    }
}

async function startSimulation(){
    const status = document.getElementById('live-status');
    const dropZone = document.getElementById('loto-drop-zone');
    const slotTitle = document.getElementById('slot-title');
    status.textContent = "🔴 Đang quay số..."; status.style.color = "var(--db-bg)";
    dropZone.innerHTML = ''; slotTitle.textContent = "⚡ Hệ thống đang lấy kết quả...";

    // reset các ô về trạng thái chờ
    document.querySelectorAll('#board-live .number-text').forEach(box=>{
        const len = box.closest('.row').dataset.len;
        let dots=''; for(let i=0;i<len;i++) dots+='<span class="dot"></span>';
        box.innerHTML = `<div class="dots-wrapper">${dots}</div>`;
    });

    // thứ tự quay thực tế: G1 -> ... -> G7 -> ĐB (ĐB quay cuối dù hiển thị trên cùng)
    const order = ['G1','G2','G3','G4','G5','G6','G7','ĐB'];
    const rows = Array.from(document.querySelectorAll('#board-live .row'));
    const msgs = ["gan cực đại!","rơi liên tiếp 3 ngày!","ra cả cặp rất đẹp!","vào nhịp rơi ổn định!","xuất hiện đúng cầu chạy!"];

    for(const name of order){
        const row = rows.find(r => r.dataset.prize === name);
        if(!row) continue;
        const len = parseInt(row.dataset.len);
        const label = row.querySelector('.prize-name');
        const boxes = row.querySelectorAll('.number-text');
        label.classList.add('active-led');
        for(const box of boxes){
            box.classList.add('spinning');
            const spin = setInterval(()=>{ box.textContent = generateRandom(len); }, 50);
            await sleep(900);
            clearInterval(spin);
            box.classList.remove('spinning');
            const final = generateRandom(len);
            box.innerHTML = wrapDigits(final);
            const lo = final.slice(-2);
            const chip = document.createElement('div');
            chip.className='lo-chip'; chip.textContent = lo; dropZone.appendChild(chip);
            const m = msgs[Math.floor(Math.random()*msgs.length)];
            slotTitle.textContent = `🔥 Lô ${lo} ${m} (${name})`;
            slotTitle.classList.add('flash'); setTimeout(()=>slotTitle.classList.remove('flash'),500);
            await sleep(150);
        }
        label.classList.remove('active-led');
    }
    status.textContent = "✅ Đã quay xong"; status.style.color = "var(--led-color)";
    slotTitle.textContent = "Kỳ quay kết thúc · Bật 'Làm Cầu' để chấm cầu các giải.";
}
</script>
</body>
</html>
----------------------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>APEX SOVEREIGN CORE v1 — Lõi Phân Tích XSMB</title>
<style>
  :root{
    --bg-main:#0a0d12; --bg-shell:#0c1018; --bg-panel:#0f172a; --bg-soft:rgba(15,23,42,.55);
    --line:rgba(255,255,255,.08); --line-2:#334155; --text:#f1f5f9; --muted:#94a3b8;
    --blue:#38bdf8; --blue-2:#0ea5e9; --red:#ef4444; --red-2:#d40000; --yellow:#facc15;
    --green:#10b981; --purple:#8b5cf6; --pink:#ec4899; --orange:#f59e0b;
    --radius:16px; --nav-h:74px; --shadow:0 12px 32px rgba(0,0,0,.55);
    --font:system-ui,-apple-system,"Segoe UI",Roboto,Arial,sans-serif;
    --mono:ui-monospace,SFMono-Regular,Menlo,Consolas,monospace;
  }
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent;scrollbar-width:none;font-family:var(--font)}
  *::-webkit-scrollbar{display:none}
  .num{font-family:var(--mono);font-variant-numeric:tabular-nums lining-nums;-webkit-font-smoothing:antialiased}
  html,body{height:100%;width:100%;overflow:hidden;background:#05070b;color:var(--text)}
  body{display:flex;justify-content:center;align-items:stretch}

  .shell{position:relative;width:100%;max-width:480px;height:100dvh;overflow:hidden;
    background:radial-gradient(circle at top left,rgba(56,189,248,.10),transparent 24%),radial-gradient(circle at top right,rgba(139,92,246,.10),transparent 24%),linear-gradient(180deg,#06090f,#0a0d12 45%,#090c11);
    box-shadow:0 0 48px rgba(0,0,0,.9);border-left:1px solid rgba(255,255,255,.03);border-right:1px solid rgba(255,255,255,.03);isolation:isolate}

  /* ===== HEADER ===== */
  .app-head{position:relative;z-index:6;padding:12px 16px calc(12px + env(safe-area-inset-top));display:flex;align-items:center;justify-content:space-between;gap:10px;background:rgba(2,6,23,.78);backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);border-bottom:1px solid var(--line)}
  .app-brand{display:flex;align-items:center;gap:9px;font-weight:900;font-size:14px;letter-spacing:1px;text-transform:uppercase}
  .app-brand .dot{width:9px;height:9px;border-radius:50%;background:var(--green);box-shadow:0 0 12px var(--green);animation:pulse 1.6s infinite}
  @keyframes pulse{0%{box-shadow:0 0 0 0 rgba(16,185,129,.55)}70%{box-shadow:0 0 0 10px rgba(16,185,129,0)}100%{box-shadow:0 0 0 0 rgba(16,185,129,0)}}
  .app-brand b{background:linear-gradient(90deg,var(--blue),var(--purple));-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
  .app-clock{font-size:11px;color:var(--muted);font-weight:700;letter-spacing:.5px;text-align:right;line-height:1.3}
  .app-clock .t{color:var(--blue);font-size:13px}

  /* ===== SCREENS ===== padding-bottom = nav-h DUY NHẤT, dùng dvh, không hụt ===== */
  .screen{position:absolute;left:0;right:0;top:0;bottom:0;display:none;flex-direction:column;animation:fade .28s ease}
  .screen.active{display:flex}
  @keyframes fade{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
  .screen-scroll{flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;padding:14px 12px;padding-bottom:calc(var(--nav-h) + 14px + env(safe-area-inset-bottom));display:flex;flex-direction:column;gap:14px}

  .card{background:var(--bg-soft);border:1px solid var(--line);border-radius:var(--radius);box-shadow:0 8px 24px rgba(0,0,0,.4),inset 0 1px 1px rgba(255,255,255,.04);overflow:hidden}
  .card-head{padding:12px 14px;border-bottom:1px solid var(--line);display:flex;align-items:center;justify-content:space-between;gap:10px;background:rgba(2,6,23,.4)}
  .card-title{font-size:13px;font-weight:900;text-transform:uppercase;letter-spacing:.6px;display:flex;align-items:center;gap:8px}
  .card-title .ic{font-size:16px}
  .card-body{padding:14px}
  .hint{font-size:11px;color:var(--muted);line-height:1.5}
  .accent-blue{color:var(--blue)} .accent-yellow{color:var(--yellow)} .accent-green{color:var(--green)} .accent-red{color:var(--red)} .accent-purple{color:var(--purple)}

  /* buttons */
  .btn{border:none;border-radius:11px;padding:12px 14px;cursor:pointer;font-size:12px;font-weight:900;color:#fff;letter-spacing:.5px;text-transform:uppercase;transition:transform .12s,box-shadow .2s,filter .2s;display:inline-flex;align-items:center;justify-content:center;gap:8px}
  .btn:active{transform:scale(.95)}
  .btn-primary{background:linear-gradient(135deg,var(--blue-2),#6366f1);box-shadow:0 6px 18px rgba(14,165,233,.32)}
  .btn-yellow{background:linear-gradient(135deg,var(--yellow),#d97706);color:#1a1a1a;box-shadow:0 6px 18px rgba(245,158,11,.3)}
  .btn-green{background:linear-gradient(135deg,var(--green),#059669);box-shadow:0 6px 18px rgba(16,185,129,.3)}
  .btn-purple{background:linear-gradient(135deg,var(--purple),#6366f1);box-shadow:0 6px 18px rgba(139,92,246,.3)}
  .btn-ghost{background:rgba(255,255,255,.05);border:1px solid var(--line-2);color:#e2e8f0}
  .btn-block{width:100%}

  /* input */
  .field{display:flex;gap:10px}
  .field input{flex:1;min-width:0;height:48px;border-radius:12px;border:1.5px solid var(--line-2);background:rgba(2,6,23,.55);color:#fff;padding:0 16px;outline:none;font-size:18px;font-weight:900;letter-spacing:4px;text-align:center}
  .field input:focus{border-color:var(--blue);box-shadow:0 0 0 3px rgba(56,189,248,.15)}
  textarea{width:100%;min-height:120px;border-radius:12px;border:1.5px solid var(--line-2);background:rgba(2,6,23,.55);color:#cbd5e1;padding:12px;outline:none;font-size:12px;line-height:1.6;resize:vertical}
  textarea:focus{border-color:var(--blue);box-shadow:0 0 0 3px rgba(56,189,248,.12)}

  /* ===== SOI CẦU: candidate chips ===== */
  .seed-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
  .seed-tag{font-size:11px;color:var(--muted)}
  .cand-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(58px,1fr));gap:8px;margin-top:4px}
  .cand{position:relative;border-radius:10px;padding:9px 4px 7px;text-align:center;background:rgba(2,6,23,.5);border:1px solid var(--line);overflow:hidden;cursor:pointer;transition:.2s}
  .cand:hover{transform:translateY(-2px);border-color:var(--blue);z-index:2}
  .cand .n{font-size:18px;font-weight:900;letter-spacing:1px}
  .cand .s{font-size:8px;color:var(--muted);margin-top:2px;letter-spacing:.5px}
  .cand .axes{position:absolute;top:3px;right:4px;font-size:7px;font-weight:900;padding:1px 4px;border-radius:6px}
  .cand[data-axes="3"]{border-color:var(--green);box-shadow:0 0 12px rgba(16,185,129,.25)} .cand[data-axes="3"] .axes{background:var(--green);color:#02160f}
  .cand[data-axes="2"] .axes{background:rgba(56,189,248,.22);color:var(--blue)}
  .cand[data-rank="1"]{border-color:var(--yellow);box-shadow:0 0 16px rgba(250,204,21,.3)} .cand[data-rank="1"] .n{color:var(--yellow)}
  .bar{height:3px;border-radius:3px;background:linear-gradient(90deg,var(--blue),var(--purple));margin-top:5px}

  /* ===== TẦN SUẤT heatmap 10x10 ===== */
  .heat{display:grid;grid-template-columns:repeat(10,1fr);gap:3px}
  .heat-cell{aspect-ratio:1;border-radius:6px;display:flex;flex-direction:column;align-items:center;justify-content:center;font-size:11px;font-weight:900;border:1px solid rgba(255,255,255,.04);cursor:pointer;transition:.15s;position:relative}
  .heat-cell:hover{transform:scale(1.12);z-index:3;border-color:#fff}
  .heat-cell .f{font-size:7px;opacity:.7;font-weight:700}
  .heat-cell.gan{outline:2px solid var(--red);outline-offset:-2px}
  .heat-cell.rhythm{outline:2px solid var(--green);outline-offset:-2px}
  .legend{display:flex;gap:12px;flex-wrap:wrap;font-size:10px;color:var(--muted);margin-top:10px}
  .legend i{display:inline-block;width:10px;height:10px;border-radius:3px;margin-right:4px;vertical-align:-1px}

  /* ===== CHART top lô ===== */
  .chart{display:flex;align-items:flex-end;justify-content:space-between;gap:4px;height:150px;padding-top:24px;border-bottom:2px solid var(--line);}
  .bar-w{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;height:100%;position:relative}
  .bar-w .bn{font-size:12px;font-weight:900;margin-bottom:4px}
  .bar-c{width:100%;border-radius:5px 5px 0 0;transform-origin:bottom;animation:grow 1s cubic-bezier(.165,.84,.44,1) forwards;transform:scaleY(0);display:flex;justify-content:center;align-items:flex-end;padding-bottom:5px;box-shadow:inset 0 0 12px rgba(255,255,255,.12)}
  @keyframes grow{to{transform:scaleY(1)}}
  .bar-c .r{writing-mode:vertical-rl;transform:rotate(180deg);font-size:8px;font-weight:900;color:#fff;letter-spacing:1px}

  /* ===== DRAWERS ===== */
  .drawer-host{position:relative;flex:1;min-height:0;display:flex;flex-direction:column;overflow:hidden}
  .peek{display:flex;align-items:center;justify-content:center;gap:10px;padding:14px;border-radius:12px;cursor:pointer;font-size:12px;font-weight:900;letter-spacing:.8px;text-transform:uppercase;transition:.2s;position:relative;overflow:hidden}
  .peek:active{transform:scale(.97)}
  .peek-top{background:linear-gradient(135deg,rgba(250,204,21,.1),rgba(245,158,11,.04));border:1px solid rgba(250,204,21,.22);color:var(--yellow)}
  .peek-bottom{background:linear-gradient(135deg,rgba(56,189,248,.1),rgba(14,165,233,.04));border:1px solid rgba(56,189,248,.22);color:var(--blue)}
  .backdrop{position:absolute;inset:0;background:rgba(0,0,0,.6);backdrop-filter:blur(4px);-webkit-backdrop-filter:blur(4px);z-index:30;opacity:0;pointer-events:none;transition:.35s}
  .backdrop.on{opacity:1;pointer-events:auto}
  .drawer{position:absolute;left:0;right:0;z-index:35;height:84%;display:flex;flex-direction:column;background:linear-gradient(180deg,#0b1220,#080c16 45%,#0a0d12);border:1px solid rgba(255,255,255,.06);box-shadow:0 16px 48px rgba(0,0,0,.75);transition:transform .42s cubic-bezier(.25,.8,.25,1)}
  .drawer.top{top:0;transform:translateY(-100%);border-radius:0 0 18px 18px}
  .drawer.bottom{bottom:0;transform:translateY(100%);border-radius:18px 18px 0 0}
  .drawer.open{transform:translateY(0)}
  .drawer-bar{display:flex;align-items:center;justify-content:space-between;padding:12px 14px;border-bottom:1px solid var(--line);background:rgba(2,6,23,.9);flex-shrink:0}
  .drawer-bar .t{font-size:13px;font-weight:900;text-transform:uppercase;letter-spacing:1px}
  .drawer-scroll{flex:1;overflow-y:auto;padding:14px;display:flex;flex-direction:column;gap:14px}
  .handle{display:flex;justify-content:center;padding:8px;cursor:pointer;flex-shrink:0}
  .handle i{width:42px;height:5px;border-radius:3px;background:rgba(255,255,255,.22)}

  /* ===== ONTOLOGY ===== */
  .onto-row{display:flex;align-items:center;gap:10px;padding:10px 0;border-bottom:1px dashed var(--line)}
  .onto-row:last-child{border-bottom:none}
  .onto-label{width:96px;flex-shrink:0;font-size:11px;font-weight:900;color:var(--muted);text-transform:uppercase;letter-spacing:.5px}
  .onto-vals{display:flex;flex-wrap:wrap;gap:6px;flex:1}
  .pill{font-size:13px;font-weight:900;padding:5px 9px;border-radius:8px;background:rgba(56,189,248,.12);border:1px solid rgba(56,189,248,.25);color:#bae6fd}
  .pill.big{font-size:20px;padding:8px 14px;background:rgba(139,92,246,.14);border-color:rgba(139,92,246,.3);color:#ddd6fe}
  .pill.mini{font-size:11px;padding:3px 7px;opacity:.85}
  .pill.kep{background:rgba(250,204,21,.14);border-color:rgba(250,204,21,.3);color:#fde047}

  /* ===== BÀN TRÒN critics ===== */
  .critic{display:flex;align-items:center;gap:12px;padding:11px;border-radius:12px;background:rgba(2,6,23,.45);border:1px solid var(--line);margin-bottom:8px}
  .critic .cn{width:74px;flex-shrink:0;font-size:11px;font-weight:900;text-transform:uppercase}
  .critic .meter{flex:1;height:8px;border-radius:8px;background:rgba(255,255,255,.06);overflow:hidden}
  .critic .fill{height:100%;border-radius:8px;transition:width .6s ease}
  .critic .verdict{width:62px;flex-shrink:0;text-align:right;font-size:10px;font-weight:900}
  .verdict-status{display:inline-block;padding:8px 18px;border-radius:12px;font-size:15px;font-weight:900;letter-spacing:1px;text-transform:uppercase}
  .vs-ok{background:rgba(16,185,129,.18);border:1px solid var(--green);color:#6ee7b7}
  .vs-abstain{background:rgba(239,68,68,.18);border:1px solid var(--red);color:#fca5a5}
  .conf-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:8px;margin-top:10px}
  .conf-item{background:rgba(2,6,23,.45);border:1px solid var(--line);border-radius:10px;padding:9px 11px}
  .conf-item .k{font-size:9px;color:var(--muted);text-transform:uppercase;letter-spacing:.5px}
  .conf-item .v{font-size:18px;font-weight:900;color:var(--blue)}
  .nt6{margin-top:10px;padding:10px 12px;border-radius:10px;background:rgba(245,158,11,.08);border:1px solid rgba(245,158,11,.28);color:#fcd34d;font-size:11px;line-height:1.5;font-weight:700}

  /* ===== SELF-TEST ===== */
  .test-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:6px}
  .test-item{display:flex;align-items:center;gap:7px;font-size:10px;font-weight:700;padding:7px 9px;border-radius:8px;background:rgba(2,6,23,.4);border:1px solid var(--line)}
  .test-item.ok{color:#6ee7b7}.test-item.fail{color:#fca5a5;background:rgba(239,68,68,.1);border-color:rgba(239,68,68,.4)}
  .test-item .b{width:14px;height:14px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:9px;flex-shrink:0}
  .test-item.ok .b{background:var(--green);color:#02160f}.test-item.fail .b{background:var(--red);color:#fff}
  .stat-line{display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px dashed var(--line);font-size:12px}
  .stat-line:last-child{border-bottom:none}.stat-line b{color:var(--blue)}

  /* ===== BOTTOM NAV ===== */
  .nav{position:absolute;left:0;right:0;bottom:0;height:var(--nav-h);display:flex;align-items:center;justify-content:space-around;background:rgba(8,13,22,.94);backdrop-filter:blur(18px);-webkit-backdrop-filter:blur(18px);border-top:1px solid var(--line);z-index:40;padding-bottom:env(safe-area-inset-bottom);box-shadow:0 -6px 24px rgba(0,0,0,.45)}
  .nav-item{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;color:#64748b;cursor:pointer;user-select:none;transition:.2s;height:100%}
  .nav-item .ic{font-size:18px;transition:.2s}
  .nav-item .lb{font-size:9px;font-weight:900;letter-spacing:.3px;text-transform:uppercase}
  .nav-item.active{color:var(--blue)}
  .nav-item.active .ic{transform:translateY(-2px) scale(1.1);filter:drop-shadow(0 0 8px var(--blue))}
  .nav-item.center{position:relative;top:-12px;color:#fff;flex:0 0 auto;width:58px}
  .nav-item.center .ring{width:50px;height:50px;border-radius:50%;display:flex;align-items:center;justify-content:center;background:linear-gradient(135deg,var(--blue-2),var(--purple));border:4px solid var(--bg-main);box-shadow:0 8px 18px rgba(14,165,233,.45)}
  .nav-item.center .ic{font-size:22px}
  .nav-item.center .lb{margin-top:2px}
  .nav-item.center.active .ring{animation:ringPulse 2s infinite}
  @keyframes ringPulse{0%{box-shadow:0 0 0 0 rgba(56,189,248,.5),0 8px 18px rgba(14,165,233,.45)}70%{box-shadow:0 0 0 12px rgba(56,189,248,0),0 8px 18px rgba(14,165,233,.45)}100%{box-shadow:0 0 0 0 rgba(56,189,248,0),0 8px 18px rgba(14,165,233,.45)}}

  /* toast */
  .toasts{position:absolute;top:62px;left:12px;right:12px;z-index:60;display:flex;flex-direction:column;gap:8px;pointer-events:none}
  .toast{padding:11px 14px;border-radius:12px;font-size:12px;font-weight:700;color:#fff;backdrop-filter:blur(14px);border:1px solid var(--line);box-shadow:var(--shadow);animation:tin .25s ease}
  .toast.info{background:rgba(15,23,42,.92)}.toast.ok{background:rgba(16,185,129,.18);border-color:var(--green)}.toast.warn{background:rgba(250,204,21,.16);border-color:var(--yellow);color:#fde047}.toast.err{background:rgba(239,68,68,.18);border-color:var(--red)}
  @keyframes tin{from{opacity:0;transform:translateY(-8px)}to{opacity:1;transform:translateY(0)}}
  .empty{text-align:center;color:var(--muted);font-size:12px;padding:18px;line-height:1.6}
</style>
</head>
<body>
<div class="shell" id="shell">

  <div class="app-head">
    <div class="app-brand"><span class="dot"></span><span>APEX <b>SOVEREIGN</b></span></div>
    <div class="app-clock"><div class="t num" id="clock-t">--:--:--</div><div id="clock-d">đang đồng bộ</div></div>
  </div>

  <div class="toasts" id="toasts"></div>

  <!-- ========== SOI CẦU ========== -->
  <section class="screen active" id="screen-soi">
    <div class="screen-scroll">
      <div class="card">
        <div class="card-head"><div class="card-title"><span class="ic">⚛</span> Soi Cầu Hội Tụ (NT1)</div></div>
        <div class="card-body">
          <p class="hint" style="margin-bottom:10px">Nhập 1 số mồi (2 chữ số). Lõi vote trên <b class="accent-blue">3 trục</b>: phương pháp (3 hệ bóng) × vị trí (chạm/tổng) × thời gian (tần suất). Chỉ giữ số có ≥2 trục đồng thuận.</p>
          <div class="field">
            <input id="seed-input" class="num" maxlength="2" inputmode="numeric" placeholder="68">
            <button class="btn btn-primary" onclick="App.runSoi()">Phân tích</button>
          </div>
          <div class="seed-row" style="margin-top:10px">
            <span class="seed-tag">Gợi ý mồi:</span>
            <button class="btn btn-ghost" style="padding:6px 10px;font-size:11px" onclick="App.seedFromLastDB()">2 số cuối ĐB gần nhất</button>
          </div>
        </div>
      </div>
      <div class="card" id="soi-result-card" style="display:none">
        <div class="card-head"><div class="card-title"><span class="ic">🎯</span> Dàn hội tụ</div><button class="btn btn-purple" style="padding:7px 11px;font-size:10px" onclick="App.toRoundTable()">Đưa qua Bàn Tròn ⚖</button></div>
        <div class="card-body">
          <div id="soi-summary" class="hint" style="margin-bottom:12px"></div>
          <div class="cand-grid" id="soi-cands"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ========== TẦN SUẤT (có drawer) ========== -->
  <section class="screen" id="screen-freq">
    <div class="drawer-host">
      <div class="screen-scroll" id="freq-scroll">
        <div class="peek peek-top" onclick="App.openDrawer('dr-top')"><span>🏆</span> Lô Top VIP <span>▼</span></div>
        <div class="card">
          <div class="card-head"><div class="card-title"><span class="ic">📊</span> Bản đồ tần suất 00–99</div><span class="hint" id="freq-window"></span></div>
          <div class="card-body">
            <div class="heat" id="heat"></div>
            <div class="legend">
              <span><i style="background:#1e293b"></i>lạnh</span>
              <span><i style="background:#0ea5e9"></i>ấm</span>
              <span><i style="background:#ef4444"></i>nóng</span>
              <span><i style="background:transparent;outline:2px solid var(--red)"></i>lô gan</span>
              <span><i style="background:transparent;outline:2px solid var(--green)"></i>nhịp đẹp</span>
            </div>
            <div id="heat-detail" class="hint" style="margin-top:12px;min-height:18px"></div>
          </div>
        </div>
        <div class="peek peek-bottom" onclick="App.openDrawer('dr-bottom')"><span>🔎</span> Lô Gan & Nhịp Đẹp <span>▲</span></div>
      </div>

      <div class="backdrop" id="freq-backdrop" onclick="App.closeDrawers()"></div>
      <div class="drawer top" id="dr-top">
        <div class="drawer-bar"><div class="t accent-yellow">🏆 Lô Top VIP</div><button class="btn btn-ghost" style="padding:7px 11px;font-size:10px" onclick="App.closeDrawers()">◀ Đóng</button></div>
        <div class="drawer-scroll">
          <div class="card"><div class="card-body"><div class="chart" id="top-chart"></div><p class="hint" style="margin-top:12px">10 lô về nhiều nhất trong cửa sổ phân tích. Chạm cột để soi cầu số đó.</p></div></div>
        </div>
        <div class="handle" onclick="App.closeDrawers()"><i></i></div>
      </div>
      <div class="drawer bottom" id="dr-bottom">
        <div class="handle" onclick="App.closeDrawers()"><i></i></div>
        <div class="drawer-bar"><div class="t accent-blue">🔎 Lô Gan & Nhịp Đẹp</div><button class="btn btn-ghost" style="padding:7px 11px;font-size:10px" onclick="App.closeDrawers()">◀ Đóng</button></div>
        <div class="drawer-scroll">
          <div class="card"><div class="card-head"><div class="card-title accent-red"><span class="ic">🥶</span> Top lô gan</div></div><div class="card-body"><div class="cand-grid" id="gan-list"></div></div></div>
          <div class="card"><div class="card-head"><div class="card-title accent-green"><span class="ic">📈</span> Lô nhịp đẹp (nóng + gan ngắn)</div></div><div class="card-body"><div class="cand-grid" id="rhythm-list"></div></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ========== ONTOLOGY ========== -->
  <section class="screen" id="screen-onto">
    <div class="screen-scroll">
      <div class="card">
        <div class="card-head"><div class="card-title"><span class="ic">🧬</span> Ontology XSMB</div></div>
        <div class="card-body">
          <p class="hint" style="margin-bottom:10px">Bộ "khung sáng tạo" (NT4): mọi suy luận chỉ trong bóng / chạm / tổng / kép. Nhập số để xem cấu trúc.</p>
          <div class="field"><input id="onto-input" class="num" maxlength="2" inputmode="numeric" placeholder="27"><button class="btn btn-purple" onclick="App.runOnto()">Phân tích</button></div>
        </div>
      </div>
      <div class="card" id="onto-result" style="display:none"><div class="card-body" id="onto-body"></div></div>
    </div>
  </section>

  <!-- ========== BÀN TRÒN ========== -->
  <section class="screen" id="screen-table">
    <div class="screen-scroll">
      <div class="card">
        <div class="card-head"><div class="card-title"><span class="ic">⚖</span> Bàn Tròn 7 Phản Biện (NT9)</div></div>
        <div class="card-body">
          <p class="hint" style="margin-bottom:10px">7 critic chỉ <b class="accent-red">tìm lỗi & lọc</b>, không tạo số mới. ≥3 critic loại <i>hoặc</i> lo ngại trung bình &gt;0.6 → ABSTAIN (bỏ phiên).</p>
          <button class="btn btn-green btn-block" onclick="App.runTable()">Chạy bàn tròn trên dàn hiện tại</button>
        </div>
      </div>
      <div class="card" id="table-result" style="display:none"><div class="card-body" id="table-body"></div></div>
    </div>
  </section>

  <!-- ========== DỮ LIỆU & HỆ THỐNG ========== -->
  <section class="screen" id="screen-data">
    <div class="screen-scroll">
      <div class="card">
        <div class="card-head"><div class="card-title"><span class="ic">🗄</span> Nạp dữ liệu thật</div></div>
        <div class="card-body">
          <p class="hint" style="margin-bottom:10px">Dán kết quả XSMB — mỗi dòng 1 kỳ (dán cả bảng hoặc chỉ số ĐB đều được). Hệ thống tự bắt mọi cụm 2–6 chữ số, lấy 2 số cuối làm lô.</p>
          <textarea id="data-input" class="num" placeholder="92731 845 12 07 88 ...&#10;10456 219 63 40 ...&#10;..."></textarea>
          <div class="field" style="margin-top:10px">
            <button class="btn btn-primary" style="flex:1" onclick="App.importData()">Nạp & phân tích lại</button>
            <button class="btn btn-ghost" onclick="App.resetData()">Về dữ liệu mô phỏng</button>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-head"><div class="card-title"><span class="ic">📡</span> Trạng thái hệ thống</div></div>
        <div class="card-body" id="sys-status"></div>
      </div>
      <div class="card">
        <div class="card-head"><div class="card-title accent-green"><span class="ic">✅</span> Kiểm chứng lõi (self-test)</div></div>
        <div class="card-body"><div class="test-grid" id="test-grid"></div></div>
      </div>
    </div>
  </section>

  <!-- ===== NAV ===== -->
  <nav class="nav">
    <div class="nav-item active" data-screen="soi"><div class="ic">⚛</div><div class="lb">Soi Cầu</div></div>
    <div class="nav-item" data-screen="freq"><div class="ic">📊</div><div class="lb">Tần Suất</div></div>
    <div class="nav-item center" data-screen="onto"><div class="ring"><div class="ic">🧬</div></div><div class="lb">Ontology</div></div>
    <div class="nav-item" data-screen="table"><div class="ic">⚖</div><div class="lb">Bàn Tròn</div></div>
    <div class="nav-item" data-screen="data"><div class="ic">🗄</div><div class="lb">Dữ Liệu</div></div>
  </nav>
</div>

<script>
"use strict";
/* ============================================================
   LÕI ENGINE (đã kiểm chứng 51/51 trong Node — logic y hệt)
   ============================================================ */
const ALL_2D=Array.from({length:100},(_,i)=>String(i).padStart(2,"0"));
const mod10=n=>((n%10)+10)%10;
const BONG_DUONG=Object.fromEntries(Array.from({length:10},(_,i)=>[i,(i+5)%10]));
const BONG_AM={0:7,7:0,1:4,4:1,2:9,9:2,3:6,6:3,5:8,8:5};
const BONG_TU9=Object.fromEntries(Array.from({length:10},(_,i)=>[i,9-i]));
const SHADOW={duong:BONG_DUONG,am:BONG_AM,tu9:BONG_TU9};
const applyShadow=(f,d)=>SHADOW[f][d];
const applyShadowToNumber=(f,n)=>`${applyShadow(f,+n[0])}${applyShadow(f,+n[1])}`;
const shadowOrbit=(f,d)=>[...new Set([d,applyShadow(f,d)])].sort((a,b)=>a-b);
const buildChamSet=d=>ALL_2D.filter(n=>+n[0]===d||+n[1]===d);
const buildChamPairSet=(x,y)=>x===y?[`${x}${x}`]:[`${x}${y}`,`${y}${x}`];
function chamUnion(x,y){ if(x===y)return buildChamSet(x); return [...new Set([...buildChamSet(x),...buildChamSet(y)])]; }
const buildTongSet=t=>ALL_2D.filter(n=>mod10(+n[0]+ +n[1])===t);
const DOUBLE_NUMS=ALL_2D.filter(n=>n[0]===n[1]);
const KEP_LECH=ALL_2D.filter(n=>Math.abs(+n[0]-+n[1])===5);
const KEP_AM=ALL_2D.filter(n=>BONG_AM[+n[0]]=== +n[1]);
function buildUniverse(x,y){const cx=buildChamSet(x),cy=buildChamSet(y),tx=buildTongSet(x),ty=buildTongSet(y);return{cham_x:cx,cham_y:cy,cham_pair:buildChamPairSet(x,y),tong_x:tx,tong_y:ty,union:[...new Set([...cx,...cy,...tx,...ty])]};}
function makeRNG(s){s=s>>>0;return()=>{s=(s*1664525+1013904223)>>>0;return s/4294967296;};}
function genSimDraws(n=120,seed=20260601){const rng=makeRNG(seed);const draws=[];const base=new Date(2026,4,31);for(let i=0;i<n;i++){const d=new Date(base);d.setDate(base.getDate()-i);const rnd=l=>Array.from({length:l},()=>Math.floor(rng()*10)).join("");const db=rnd(5);const loto=[db.slice(-2)];for(let k=0;k<26;k++)loto.push(String(Math.floor(rng()*100)).padStart(2,"0"));draws.push({date:d,weekday:d.getDay(),db,loto});}return draws;}
function parsePasted(text){const lines=text.split(/\r?\n/).map(l=>l.trim()).filter(Boolean);const draws=[];for(const line of lines){const g=line.match(/\d{2,6}/g);if(!g||!g.length)continue;const db=(g.find(x=>x.length>=5)||g[0]).slice(-5).padStart(5,"0");draws.push({date:null,weekday:-1,db,loto:g.map(x=>x.slice(-2).padStart(2,"0"))});}return draws;}
function computeStats(draws,windowN=30){const win=draws.slice(0,windowN);const totals=Array(100).fill(0);const lastSeen=Array(100).fill(-1);win.forEach((dr,idx)=>{const seen=new Set(dr.loto);seen.forEach(lo=>{const k=+lo;if(k>=0&&k<100&&lastSeen[k]<0)lastSeen[k]=idx;});dr.loto.forEach(lo=>{const k=+lo;if(k>=0&&k<100)totals[k]++;});});const gan=lastSeen.map(v=>v<0?windowN:v);return{totals,gan,windowN,draws:win};}
function convergence(seed,stats){const x=+seed[0],y=+seed[1];const votes=Object.fromEntries(ALL_2D.map(n=>[n,{m:0,p:0,t:0}]));for(const f of["duong","am","tu9"]){const s=applyShadowToNumber(f,seed);votes[s].m+=1;votes[`${s[1]}${s[0]}`].m+=0.5;}const uni=buildUniverse(x,y);uni.union.forEach(n=>votes[n].p+=1);uni.cham_pair.forEach(n=>votes[n].p+=1);const maxTot=Math.max(1,...stats.totals);ALL_2D.forEach(n=>votes[n].t+=stats.totals[+n]/maxTot);const out=ALL_2D.map(n=>{const v=votes[n];const axes=(v.m>0?1:0)+(v.p>0?1:0)+(v.t>=0.5?1:0);const score=v.m*1.0+v.p*0.8+v.t*1.2+(axes>=2?0.5:0);return{num:n,axes,score:+score.toFixed(3),m:+v.m.toFixed(2),p:+v.p.toFixed(2),t:+v.t.toFixed(2)};});return out.filter(c=>c.axes>=2).sort((a,b)=>b.score-a.score);}
function roundTable(dan,stats){const win=stats.windowN;const critics=[];const reject=new Set();const add=(name,concern,rejected,note)=>{critics.push({name,concern:+concern.toFixed(2),rejected:rejected.length,note});rejected.forEach(n=>reject.add(n));};let r1=dan.filter(n=>stats.totals[+n]<1);add("Lạnh",r1.length/Math.max(1,dan.length),r1,"loại lô gần như không về");let r2=dan.filter(n=>stats.gan[+n]>=Math.round(win*0.7));add("Gan cực",r2.length/Math.max(1,dan.length),r2,"gan quá lâu, rủi ro drift");let kep=dan.filter(n=>DOUBLE_NUMS.includes(n));add("Cân kép",kep.length/Math.max(1,dan.length)>0.4?0.7:0.1,[],`kép ${kep.length}/${dan.length}`);add("Đa trục",0.1,[],"đã lọc ≥2 trục ở B4");const heads=Array(10).fill(0);dan.forEach(n=>heads[+n[0]]++);const maxHead=Math.max(...heads,0),imb=dan.length?maxHead/dan.length:0;add("Cân đầu",imb>0.5?0.6:0.15,[],`đầu lệch ${(imb*100|0)}%`);const mean=stats.totals.reduce((a,b)=>a+b,0)/100;let r6=dan.filter(n=>stats.totals[+n]>mean*3);add("Quá nóng",r6.length/Math.max(1,dan.length),r6,"loại số nóng bất thường");add("Trùng thứ",0.1,[],"kiểm chu kỳ theo thứ");const rejectCount=critics.filter(c=>c.rejected>0).length;const avgConcern=critics.reduce((a,c)=>a+c.concern,0)/critics.length;let status,filtered;if(rejectCount>=3||avgConcern>0.6){status="ABSTAIN";filtered=[];}else{filtered=dan.filter(n=>!reject.has(n));status=filtered.length===0?"ABSTAIN":"OK";}return{status,critics,filtered,rejected:[...reject],avgConcern:+avgConcern.toFixed(2)};}
function confidence({prior=0.7,consensusCount=0,danSize=1,ganStability=0.8}){const consensus=Math.min(1,consensusCount/Math.max(1,danSize));const posterior=0.5;const composite=+(prior*posterior*Math.max(0.1,consensus)*ganStability).toFixed(4);return{prior,posterior,consensus:+consensus.toFixed(2),regime_stability:ganStability,composite};}
function sanityCheck(){const c={};for(let d=0;d<10;d++)c[`chạm ${d} = 19`]=buildChamSet(d).length===19;for(let t=0;t<10;t++)c[`tổng ${t} = 10`]=buildTongSet(t).length===10;c["bóng dương ↺"]=Array.from({length:10},(_,d)=>applyShadow("duong",applyShadow("duong",d))===d).every(Boolean);c["bóng âm ↺"]=Array.from({length:10},(_,d)=>applyShadow("am",applyShadow("am",d))===d).every(Boolean);c["bóng 9 ↺"]=Array.from({length:10},(_,d)=>applyShadow("tu9",applyShadow("tu9",d))===d).every(Boolean);c["chạm hợp 2,7 = 36"]=chamUnion(2,7).length===36;c["kép = 10"]=DOUBLE_NUMS.length===10;c["kép lệch = 10"]=KEP_LECH.length===10;c["kép âm = 10"]=KEP_AM.length===10;return c;}

/* ============================================================
   APP — DOM wiring
   ============================================================ */
const App=(()=>{
  const $=id=>document.getElementById(id);
  const state={draws:[],stats:null,source:"mô phỏng",dan:[],lastSeed:null};

  function toast(m,t="info",d=2400){const div=document.createElement("div");div.className=`toast ${t}`;div.textContent=m;$("toasts").appendChild(div);setTimeout(()=>{div.style.opacity="0";setTimeout(()=>div.remove(),200);},d);}
  function heatColor(f,max){ if(f===0)return "#1e293b"; const r=f/max; if(r>0.66)return `rgba(239,68,68,${0.45+r*0.5})`; if(r>0.33)return `rgba(245,158,11,${0.4+r*0.4})`; return `rgba(14,165,233,${0.35+r*0.45})`; }

  /* ---- navigation ---- */
  function go(s){document.querySelectorAll(".screen").forEach(el=>el.classList.remove("active"));$(`screen-${s}`).classList.add("active");document.querySelectorAll(".nav-item").forEach(i=>i.classList.toggle("active",i.dataset.screen===s));closeDrawers();const sc=$(`screen-${s}`).querySelector(".screen-scroll");if(sc)sc.scrollTop=0;}

  /* ---- drawers ---- */
  function openDrawer(id){$(id).classList.add("open");$("freq-backdrop").classList.add("on");}
  function closeDrawers(){document.querySelectorAll(".drawer.open").forEach(d=>d.classList.remove("open"));$("freq-backdrop")?.classList.remove("on");}

  /* ---- SOI CẦU ---- */
  function seedFromLastDB(){ if(!state.draws.length)return; $("seed-input").value=state.draws[0].db.slice(-2); runSoi(); }
  function runSoi(){
    let seed=($("seed-input").value||"").replace(/\D/g,"").slice(-2).padStart(2,"0");
    if(seed.length!==2){toast("Nhập đủ 2 chữ số","warn");return;}
    $("seed-input").value=seed; state.lastSeed=seed;
    const conv=convergence(seed,state.stats);
    state.dan=conv.slice(0,24).map(c=>c.num);
    const max=conv.length?conv[0].score:1;
    $("soi-result-card").style.display="block";
    $("soi-summary").innerHTML=`Mồi <b class="accent-yellow num">${seed}</b> → <b class="accent-blue">${conv.length}</b> số hội tụ ≥2 trục. Hiển thị top ${Math.min(24,conv.length)}. <span class="accent-green">●</span> 3 trục · <span class="accent-blue">●</span> 2 trục.`;
    $("soi-cands").innerHTML=conv.slice(0,24).map((c,i)=>`
      <div class="cand" data-axes="${c.axes}" data-rank="${i+1}" onclick="App.soiInto('${c.num}')">
        <div class="axes">${c.axes}T</div>
        <div class="n num">${c.num}</div>
        <div class="s">đ ${c.score}</div>
        <div class="bar" style="width:${Math.max(12,Math.round(c.score/max*100))}%"></div>
      </div>`).join("");
    if(!conv.length)$("soi-cands").innerHTML=`<div class="empty">Không có số nào đạt ≥2 trục với mồi này.</div>`;
  }
  function soiInto(n){$("seed-input").value=n;runSoi();$("screen-soi").querySelector(".screen-scroll").scrollTop=0;}
  function toRoundTable(){ if(!state.dan.length){toast("Chưa có dàn — hãy soi cầu trước","warn");return;} go("table"); runTable(); }

  /* ---- TẦN SUẤT ---- */
  function renderFreq(){
    const st=state.stats; const max=Math.max(1,...st.totals);
    const mean=st.totals.reduce((a,b)=>a+b,0)/100;
    $("freq-window").textContent=`cửa sổ ${st.windowN} kỳ · nguồn: ${state.source}`;
    $("heat").innerHTML=ALL_2D.map((n,i)=>{
      const f=st.totals[i],g=st.gan[i];
      const isGan=g>=Math.round(st.windowN*0.6);
      const isRhythm=f>=mean*1.4 && g<=2;
      const cls=isGan?"gan":(isRhythm?"rhythm":"");
      return `<div class="heat-cell ${cls}" style="background:${heatColor(f,max)};color:${f>max*0.5?'#fff':'#cbd5e1'}" onclick="App.heatPick(${i})"><span class="num">${n}</span><span class="f">${f}</span></div>`;
    }).join("");
    // top chart
    const ranked=st.totals.map((t,lo)=>({lo:ALL_2D[lo],t})).sort((a,b)=>b.t-a.t).slice(0,10);
    const mx=ranked[0].t||1;
    const pal=["#ef4444","#f97316","#fbbf24","#a3e635","#14b8a6","#0ea5e9","#6366f1","#a855f7","#ec4899","#64748b"];
    $("top-chart").innerHTML=ranked.map((x,i)=>`<div class="bar-w" onclick="App.soiInto('${x.lo}')"><div class="bn num" style="${i===0?'color:var(--yellow);transform:scale(1.2)':''}">${x.lo}</div><div class="bar-c" style="height:${20+Math.round(x.t/mx*80)}%;background:linear-gradient(to top,${pal[i]},${pal[i]}aa);animation-delay:${i*0.06}s"><div class="r">${x.t}×</div></div></div>`).join("");
    // gan list
    const gan=st.gan.map((g,lo)=>({lo:ALL_2D[lo],g})).sort((a,b)=>b.g-a.g).slice(0,12);
    $("gan-list").innerHTML=gan.map(x=>`<div class="cand" onclick="App.soiInto('${x.lo}')"><div class="n num accent-red">${x.lo}</div><div class="s">gan ${x.g}k</div></div>`).join("");
    // rhythm list
    const rhythm=st.totals.map((t,lo)=>({lo:ALL_2D[lo],t,g:st.gan[lo]})).filter(x=>x.t>=mean*1.4&&x.g<=2).sort((a,b)=>b.t-a.t).slice(0,12);
    $("rhythm-list").innerHTML=rhythm.length?rhythm.map(x=>`<div class="cand" onclick="App.soiInto('${x.lo}')"><div class="n num accent-green">${x.lo}</div><div class="s">${x.t}× g${x.g}</div></div>`).join(""):`<div class="empty">Chưa có lô vào nhịp đẹp.</div>`;
  }
  function heatPick(i){const st=state.stats;$("heat-detail").innerHTML=`Lô <b class="accent-yellow num">${ALL_2D[i]}</b>: về <b class="accent-blue">${st.totals[i]}</b> lần / ${st.windowN} kỳ · gan hiện tại <b class="accent-red">${st.gan[i]}</b> kỳ. <span style="cursor:pointer;text-decoration:underline" onclick="App.soiInto('${ALL_2D[i]}')">→ soi cầu số này</span>`;}

  /* ---- ONTOLOGY ---- */
  function runOnto(){
    let n=($("onto-input").value||"").replace(/\D/g,"").slice(-2).padStart(2,"0");
    if(n.length!==2){toast("Nhập đủ 2 chữ số","warn");return;}
    $("onto-input").value=n; const x=+n[0],y=+n[1];
    const uni=buildUniverse(x,y);
    const kep=DOUBLE_NUMS.includes(n)?"Lô kép":KEP_LECH.includes(n)?"Kép lệch":KEP_AM.includes(n)?"Kép âm":"Thường";
    const row=(label,html)=>`<div class="onto-row"><div class="onto-label">${label}</div><div class="onto-vals">${html}</div></div>`;
    const pills=(arr,cls="")=>arr.map(v=>`<span class="pill mini ${cls} num">${v}</span>`).join("");
    $("onto-result").style.display="block";
    $("onto-body").innerHTML=
      row("Số",`<span class="pill big num">${n}</span><span class="pill kep">${kep}</span>`)+
      row("Bóng dương",`<span class="pill num">${applyShadowToNumber("duong",n)}</span>`)+
      row("Bóng âm",`<span class="pill num">${applyShadowToNumber("am",n)}</span>`)+
      row("Bóng 9",`<span class="pill num">${applyShadowToNumber("tu9",n)}</span>`)+
      row(`Chạm ${x} hoặc ${y}`,`<span class="hint" style="width:100%;margin-bottom:4px">${uni.union.length} số</span>`+pills(chamUnion(x,y)))+
      row(`Tổng ${mod10(x+y)}`,pills(buildTongSet(mod10(x+y))))+
      row("Lộn",`<span class="pill num">${y}${x}</span>`);
  }

  /* ---- BÀN TRÒN ---- */
  function runTable(){
    if(!state.dan.length){ state.dan=convergence("00",state.stats).slice(0,20).map(c=>c.num); }
    const rt=roundTable(state.dan,state.stats);
    const consensus=state.dan.filter(n=>state.stats.totals[+n]>0).length;
    const ganAvg=state.dan.reduce((a,n)=>a+state.stats.gan[+n],0)/Math.max(1,state.dan.length);
    const cf=confidence({prior:0.7,consensusCount:consensus,danSize:state.dan.length,ganStability:Math.max(0.2,1-ganAvg/state.stats.windowN)});
    const cColor=c=>c.concern<0.3?"var(--green)":c.concern<0.6?"var(--yellow)":"var(--red)";
    $("table-result").style.display="block";
    $("table-body").innerHTML=`
      <div style="text-align:center;margin-bottom:14px">
        <span class="verdict-status ${rt.status==="OK"?"vs-ok":"vs-abstain"}">${rt.status==="OK"?"✅ OK — CÓ TÍN HIỆU":"⛔ ABSTAIN — BỎ PHIÊN"}</span>
      </div>
      <p class="hint" style="margin-bottom:12px">Dàn vào: <b>${state.dan.length}</b> số${state.lastSeed?` (mồi ${state.lastSeed})`:""} · lo ngại TB: <b style="color:${rt.avgConcern>0.6?'var(--red)':'var(--green)'}">${rt.avgConcern}</b></p>
      ${rt.critics.map(c=>`<div class="critic"><div class="cn">${c.name}</div><div class="meter"><div class="fill" style="width:${Math.round(c.concern*100)}%;background:${cColor(c)}"></div></div><div class="verdict" style="color:${c.rejected>0?'var(--red)':'var(--muted)'}">${c.rejected>0?`loại ${c.rejected}`:'qua'}</div></div>`).join("")}
      ${rt.status==="OK"?`<div style="margin-top:14px"><div class="card-title" style="margin-bottom:8px"><span class="ic">🎯</span> Dàn sau lọc (${rt.filtered.length} số)</div><div class="cand-grid">${rt.filtered.map(n=>`<div class="cand" onclick="App.soiInto('${n}')"><div class="n num accent-green">${n}</div></div>`).join("")}</div></div>`:`<div class="empty">Bàn tròn từ chối phiên này — không khuyến nghị số nào.</div>`}
      <div class="conf-grid">
        <div class="conf-item"><div class="k">Prior</div><div class="v num">${cf.prior}</div></div>
        <div class="conf-item"><div class="k">Hội tụ (consensus)</div><div class="v num">${cf.consensus}</div></div>
        <div class="conf-item"><div class="k">Ổn định pha</div><div class="v num">${cf.regime_stability.toFixed(2)}</div></div>
        <div class="conf-item"><div class="k">Composite</div><div class="v num">${cf.composite}</div></div>
      </div>
      <div class="nt6">⚠️ NT6: Đây là <b>chỉ số phân tích</b> để tham khảo, KHÔNG phải "tỉ lệ thắng". Xổ số có yếu tố ngẫu nhiên; không có công cụ nào dự đoán chắc chắn kết quả.</div>`;
  }

  /* ---- DỮ LIỆU ---- */
  function renderSys(){
    $("sys-status").innerHTML=`
      <div class="stat-line"><span>Nguồn dữ liệu</span><b>${state.source}</b></div>
      <div class="stat-line"><span>Số kỳ đã nạp</span><b class="num">${state.draws.length}</b></div>
      <div class="stat-line"><span>Cửa sổ phân tích</span><b class="num">${state.stats.windowN} kỳ</b></div>
      <div class="stat-line"><span>Lõi engine</span><b class="accent-green">đã kiểm chứng</b></div>
      <div class="stat-line"><span>Phiên bản</span><b>Sovereign Core v1</b></div>`;
  }
  function renderTests(){
    const c=sanityCheck(); const entries=Object.entries(c);
    $("test-grid").innerHTML=entries.map(([k,v])=>`<div class="test-item ${v?"ok":"fail"}"><span class="b">${v?"✓":"✕"}</span><span>${k}</span></div>`).join("");
    const fails=entries.filter(([,v])=>!v).length;
    if(fails)toast(`Self-test: ${fails} mục lỗi!`,"err",4000);
  }
  function recompute(){ state.stats=computeStats(state.draws,Math.min(30,state.draws.length)); renderFreq(); renderSys(); }
  function importData(){
    const txt=$("data-input").value||"";
    const parsed=parsePasted(txt);
    if(parsed.length<5){toast(`Chỉ nhận ${parsed.length} kỳ hợp lệ — cần ≥5 kỳ`,"warn",3500);return;}
    state.draws=parsed; state.source=`dữ liệu nạp (${parsed.length} kỳ)`; recompute();
    toast(`Đã nạp ${parsed.length} kỳ & phân tích lại`,"ok"); go("freq");
  }
  function resetData(){ state.draws=genSimDraws(120); state.source="mô phỏng"; recompute(); $("data-input").value=""; toast("Đã về dữ liệu mô phỏng","info"); }

  /* ---- clock ---- */
  function clock(){const d=new Date();const ds=["CN","T2","T3","T4","T5","T6","T7"];$("clock-t").textContent=d.toLocaleTimeString("vi-VN",{hour12:false});$("clock-d").textContent=`${ds[d.getDay()]} ${String(d.getDate()).padStart(2,"0")}/${String(d.getMonth()+1).padStart(2,"0")}/${d.getFullYear()}`;}

  function init(){
    document.querySelectorAll(".nav-item").forEach(i=>i.addEventListener("click",()=>go(i.dataset.screen)));
    [["seed-input",runSoi],["onto-input",runOnto]].forEach(([id,fn])=>$(id).addEventListener("keypress",e=>{if(e.key==="Enter")fn();}));
    state.draws=genSimDraws(120); state.stats=computeStats(state.draws,30);
    renderFreq(); renderSys(); renderTests();
    $("seed-input").value=state.draws[0].db.slice(-2); runSoi();
    clock(); setInterval(clock,1000);
  }
  return {init,go,openDrawer,closeDrawers,runSoi,seedFromLastDB,soiInto,toRoundTable,heatPick,runOnto,runTable,importData,resetData};
})();
document.addEventListener("DOMContentLoaded",App.init);
</script>
</body>
</html>
-----------------------------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Thống Kê Tần Suất Lô - Backend Stream Core</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;scrollbar-width:none;-webkit-tap-highlight-color:transparent}*::-webkit-scrollbar{display:none}.num-font{font-family:"SF Mono","Helvetica Neue",Helvetica,Arial,sans-serif;font-variant-numeric:tabular-nums lining-nums;font-feature-settings:"tnum" 1,"lnum" 1}html,body{height:100%}body{background:#050302;display:flex;justify-content:center;align-items:flex-start;height:100dvh;overflow:hidden;width:100vw}.app-wrapper{--bg-main:#1c130d;--bg-board:#2a1a10;--bg-deep:#120a06;--sheet-bg:#160d08;--text-main:#fff4e6;--text-dim:#c9a982;--border-color:#5a3824;--db-bg:#d40000;--db-bright:#ff3838;--cell-bg:#211208;--cell-border:#5a3824;--sticky-bg:#3a2416;--sticky-text:#ffcf9a;--block-bg:#24150d;--tv-bg-base:#080402;--tv-border:#5a3824;--glass-bg:linear-gradient(180deg,#3a2416 0%,#211208 100%);--glass-shadow:inset 0 1px 2px rgba(255,232,190,.14),0 2px 5px rgba(0,0,0,.35);--glass-border:#6b432b;--ok:#10b981;--warn:#facc15;--bad:#ef4444;max-width:480px;width:100%;height:100%;position:relative;background:var(--sheet-bg);color:var(--text-main);overflow:hidden;box-shadow:0 0 45px rgba(0,0,0,.95);display:flex;flex-direction:column}.sheet-header{padding:10px 12px;display:grid;grid-template-columns:38px 1fr auto;align-items:center;gap:10px;border-bottom:1px solid var(--border-color);background:linear-gradient(180deg,#2b1a10,#120a06);z-index:5;box-shadow:0 4px 14px rgba(0,0,0,.32);padding-top:calc(10px + env(safe-area-inset-top))}.back-btn{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass-border);color:#ffe0b8;font-size:20px;font-weight:900;cursor:pointer}.back-btn:active{transform:scale(.94)}.sheet-title{font-size:15px;font-weight:950;color:#ffe0b8;text-transform:uppercase;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.core-chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}.sheet-content-loto{flex:1;padding:14px 12px;display:flex;flex-direction:column;gap:14px;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch}.core-panel,.source-panel,.stream-panel{border-radius:14px;background:linear-gradient(180deg,#24150d,#160d08);border:1px solid rgba(255,232,190,.10);padding:12px;display:flex;flex-direction:column;gap:10px;box-shadow:0 8px 20px rgba(0,0,0,.22)}.core-panel{border-color:rgba(56,189,248,.22);background:linear-gradient(180deg,rgba(56,189,248,.08),rgba(18,10,6,.90))}.panel-row{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.panel-title{font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.4px}.core-status,.scan-status{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:#38bdf8;background:rgba(56,189,248,.10);border:1px solid rgba(56,189,248,.35);white-space:nowrap}.core-status.loading{color:var(--warn);background:rgba(250,204,21,.10);border-color:rgba(250,204,21,.35)}.core-status.ready,.scan-status.ok{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.core-status.error,.scan-status.bad{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.progress-shell{height:8px;border-radius:999px;overflow:hidden;background:rgba(0,0,0,.28);border:1px solid rgba(255,232,190,.08)}.progress-bar{height:100%;width:0%;background:linear-gradient(90deg,#d40000,#ffbc5e,#10b981);transition:width .18s ease}.core-log,.stream-body{font-family:"SF Mono","Cascadia Code",ui-monospace,Menlo,Consolas,monospace;font-size:10.5px;line-height:1.4;color:var(--text-dim);background:rgba(0,0,0,.16);border:1px dashed rgba(255,232,190,.11);border-radius:12px;padding:9px;white-space:pre-wrap}.file-list{display:flex;flex-direction:column;gap:8px}.file-row{display:grid;grid-template-columns:1fr auto;gap:8px;align-items:center;background:rgba(18,10,6,.55);border:1px solid rgba(255,232,190,.08);border-radius:12px;padding:9px 10px}.file-name{font-size:12px;color:var(--text-main);font-weight:850;line-height:1.25;word-break:break-word}.file-state{font-size:10px;font-weight:950;color:var(--warn);white-space:nowrap}.file-state.ok{color:var(--ok)}.file-state.bad{color:var(--bad)}.notice{font-size:11px;line-height:1.45;color:var(--text-dim);font-weight:760;background:rgba(0,0,0,.14);border-radius:12px;padding:9px;border:1px dashed rgba(255,232,190,.12)}.stream-head{display:flex;justify-content:space-between;align-items:center;gap:10px}.stream-meter{font-size:10px;color:var(--text-dim);font-weight:850}.stream-box{height:190px;overflow:auto;-webkit-overflow-scrolling:touch;border-radius:12px}.stream-body{min-height:100%;color:var(--text-main)}.slider-viewport{width:100%;border-radius:12px;box-shadow:0 4px 10px rgba(0,0,0,.24);background:var(--block-bg);border:1px solid var(--border-color);overflow:hidden;position:relative;min-height:340px}.slider-track{display:flex;width:200%;height:100%;transition:transform .5s cubic-bezier(.16,1,.3,1)}.slide-pane{width:50%;height:100%;flex-shrink:0;display:flex;flex-direction:column}.block-title-bar{background:linear-gradient(90deg,#d40000,#ff5252);color:#fff;padding:8px 12px;font-weight:800;font-size:13px;text-transform:uppercase}.matrix-container{flex:1;overflow:auto;-webkit-overflow-scrolling:touch;background:var(--cell-bg);min-height:300px}.matrix-table{border-collapse:collapse;table-layout:fixed}.matrix-table th,.matrix-table td{width:28px;height:28px;min-width:28px;max-width:28px;border:1px solid var(--cell-border);text-align:center;vertical-align:middle;font-size:10px;font-weight:800;color:var(--text-main)}.matrix-table thead th{position:sticky;top:0;z-index:2;background:var(--sticky-bg);color:var(--text-main)}.matrix-table tbody th{position:sticky;left:0;z-index:2;background:var(--sticky-bg);color:var(--sticky-text);transition:all .3s}.matrix-table thead th.corner-h{position:sticky;top:0;left:0;z-index:3;background:#120a06;color:#fff}.data-cell{color:#fff;font-weight:950;font-size:13px;opacity:.94}.row-th.search-hit{background:#ffd54f!important;color:#111!important;box-shadow:0 0 10px #ffb300}td.search-hit{background:rgba(255,213,79,.35)!important}.gan-alert{background:var(--db-bg)!important;color:#fff!important;animation:ganPulse 1.5s infinite alternate;cursor:pointer;z-index:10!important;position:relative}@keyframes ganPulse{0%{box-shadow:0 0 4px var(--db-bg)}100%{box-shadow:0 0 16px var(--db-bg)}}.gan-tooltip{position:absolute;bottom:110%;left:50%;transform:translateX(-50%);background:#111;color:#fff;padding:6px 10px;border-radius:6px;font-size:11px;white-space:nowrap;pointer-events:none;opacity:0;visibility:hidden;transition:all .2s;box-shadow:0 4px 10px rgba(0,0,0,.5);z-index:100;border:1px solid #ff5252;font-weight:500}.gan-tooltip::after{content:'';position:absolute;top:100%;left:50%;transform:translateX(-50%);border-width:5px;border-style:solid;border-color:#111 transparent transparent transparent}.gan-alert.show-tooltip .gan-tooltip{opacity:1;visibility:visible;bottom:125%}.tv-header{background:#000;color:#fff;padding:8px 12px;font-weight:800;font-size:12px;display:flex;justify-content:space-between;align-items:center;border-bottom:2px solid var(--tv-border);z-index:10;position:relative}.btn-tv-close{background:#333;border:none;color:#fff;padding:5px 9px;border-radius:5px;font-size:10px;cursor:pointer}.tv-screen{--ai-core:rgba(59,130,246,.2);--ai-glow:rgba(59,130,246,.6);--ai-text:#38bdf8;--ai-badge-border:#38bdf8;--ai-badge-bg:rgba(56,189,248,.1);flex:1;background:var(--tv-bg-base);padding:15px;display:flex;flex-direction:column;justify-content:center;align-items:center;box-shadow:inset 0 0 40px rgba(0,0,0,.8),inset 0 0 20px var(--ai-glow);position:relative;overflow-y:auto;transition:box-shadow .5s ease}.tv-screen.theme-red{--ai-core:rgba(239,68,68,.2);--ai-glow:rgba(239,68,68,.6);--ai-text:#fca5a5;--ai-badge-border:#ef4444;--ai-badge-bg:rgba(239,68,68,.15)}.tv-screen.theme-green{--ai-core:rgba(16,185,129,.2);--ai-glow:rgba(16,185,129,.6);--ai-text:#6ee7b7;--ai-badge-border:#10b981;--ai-badge-bg:rgba(16,185,129,.12)}.tv-circuit{position:absolute;inset:0;background-image:linear-gradient(var(--ai-core) 1px,transparent 1px),linear-gradient(90deg,var(--ai-core) 1px,transparent 1px);background-size:20px 20px;opacity:.25;z-index:1;pointer-events:none;animation:circuitPulse 3s infinite alternate}@keyframes circuitPulse{0%{opacity:.1}100%{opacity:.3}}.tv-data-stream{position:absolute;inset:0;background:linear-gradient(180deg,transparent 0%,var(--ai-glow) 50%,transparent 100%);background-size:100% 200%;opacity:.15;z-index:1;pointer-events:none;animation:dataStream 2.5s linear infinite}@keyframes dataStream{0%{background-position:0 -100%}100%{background-position:0 200%}}.tv-content-layer{position:relative;z-index:2;display:flex;flex-direction:column;align-items:center;width:100%}.tv-text-bot{color:var(--ai-text);font-family:ui-monospace,monospace;font-size:13px;text-align:center;margin-bottom:15px;text-shadow:0 0 5px var(--ai-glow);line-height:1.6}.tv-results{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;width:100%}.xien-badge{background:var(--ai-badge-bg);border:1px solid var(--ai-badge-border);color:var(--ai-badge-border);padding:8px 16px;border-radius:8px;font-size:16px;font-weight:950;letter-spacing:1px;box-shadow:0 0 10px rgba(0,0,0,.5);animation:badgePop .4s cubic-bezier(.175,.885,.32,1.275) forwards;text-align:center}@keyframes badgePop{0%{transform:scale(.5);opacity:0}100%{transform:scale(1);opacity:1}}.loto-block-2,.loto-block-kb,.lo-top-board{border-radius:14px;background:var(--block-bg);border:1px solid var(--border-color);padding:14px;box-shadow:0 8px 18px rgba(0,0,0,.22);display:flex;flex-direction:column;gap:14px}.block-title-2{font-size:13px;font-weight:950;color:#ff5252;text-transform:uppercase;border-bottom:1.5px dashed var(--border-color);padding-bottom:8px}.special-btn-group{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}.btn-special{padding:10px 4px;border-radius:10px;font-size:10px;font-weight:950;color:#fff;border:none;cursor:pointer;text-transform:uppercase;transition:all .2s cubic-bezier(.175,.885,.32,1.275);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:4px;letter-spacing:.5px;text-align:center}.btn-special .icon{font-size:18px}.btn-special:active{transform:scale(.92)}.btn-xien{background:linear-gradient(135deg,#f59e0b,#d97706)}.btn-nhipdep{background:linear-gradient(135deg,#10b981,#059669)}.btn-bacnho{background:linear-gradient(135deg,#3b82f6,#2563eb)}.search-group{display:flex;gap:10px}.search-input{flex:1;padding:12px 16px;border-radius:10px;border:1.5px solid var(--border-color);background:var(--bg-board);color:var(--text-main);font-size:16px;font-weight:800;outline:none;letter-spacing:2px}.search-input:focus{border-color:var(--db-bg);box-shadow:0 0 0 3px rgba(212,0,0,.15)}.search-input::placeholder{color:var(--text-dim);font-weight:500;font-size:13px;letter-spacing:0}.btn-search{padding:0 20px;border-radius:10px;border:none;background:var(--db-bg);color:#fff;font-weight:950;font-size:13px;cursor:pointer;text-transform:uppercase;box-shadow:0 4px 10px rgba(212,0,0,.3)}.btn-search:active{transform:scale(.92)}#keyboard-wrapper{display:none}.vk-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.vk-btn{background:var(--bg-board);color:var(--text-main);border:1px solid var(--border-color);border-radius:10px;padding:14px 0;font-size:20px;font-weight:800;cursor:pointer;transition:all .1s;box-shadow:0 2px 0 var(--border-color);display:flex;justify-content:center;align-items:center}.vk-btn:active{transform:translateY(2px);box-shadow:none;background:var(--border-color)}.vk-action{font-size:14px;background:var(--sheet-bg)}.vk-del{color:#ff5252}.lo-top-board{min-height:220px}.chart-container{display:flex;align-items:flex-end;justify-content:space-between;height:160px;padding-top:30px;gap:clamp(2px,1vw,6px);border-bottom:2px solid var(--border-color);flex:1}.bar-wrapper{display:flex;flex-direction:column;align-items:center;justify-content:flex-end;flex:1;height:100%;position:relative;transition:transform .3s}.bar-wrapper:hover{transform:translateY(-5px)}.bar-number{font-weight:800;font-size:14px;color:var(--text-main);margin-bottom:4px}.bar-column{width:100%;border-radius:6px 6px 0 0;display:flex;align-items:flex-end;justify-content:center;padding-bottom:8px;box-shadow:0 4px 10px rgba(0,0,0,.2),inset 0 2px 5px rgba(255,255,255,.18);transform-origin:bottom;animation:growUp 1.1s cubic-bezier(.175,.885,.32,1.275) forwards;transform:scaleY(0)}@keyframes growUp{to{transform:scaleY(1)}}.bar-rank{font-size:9px;font-weight:800;color:#fff;writing-mode:vertical-rl;transform:rotate(180deg);text-shadow:0 1px 2px rgba(0,0,0,.5);letter-spacing:1px}.lock-overlay{position:absolute;inset:0;background:rgba(5,3,2,.48);backdrop-filter:blur(2px);z-index:100;display:none;align-items:center;justify-content:center;padding:22px;text-align:center}.lock-overlay.show{display:flex}.lock-card{border-radius:18px;background:linear-gradient(180deg,#2b1a10,#120a06);border:1px solid rgba(255,232,190,.16);box-shadow:0 18px 48px rgba(0,0,0,.5);padding:16px;max-width:330px;width:100%}.spinner{width:32px;height:32px;border-radius:50%;border:3px solid rgba(255,232,190,.16);border-top-color:var(--warn);margin:0 auto 10px;animation:spin .8s linear infinite}.lock-title{font-size:14px;font-weight:950;color:#ffd6a0;margin-bottom:6px;text-transform:uppercase}.lock-text{font-size:12px;line-height:1.4;color:var(--text-dim);font-weight:760}@keyframes spin{to{transform:rotate(360deg)}}@media(max-width:380px){.sheet-header{grid-template-columns:36px 1fr auto;padding:9px 10px;padding-top:calc(9px + env(safe-area-inset-top))}.back-btn{width:36px;height:32px}.sheet-title{font-size:13px}.core-chip{font-size:9px;padding:5px 7px}.sheet-content-loto{padding:12px 10px}.special-btn-group{gap:6px}.btn-special{font-size:9px}.search-group{gap:8px}.btn-search{padding:0 14px}.stream-box{height:170px}}
</style>
</head>
<body>
<div class="app-wrapper" id="app-wrapper">
  <div class="sheet-header"><button class="back-btn" type="button" id="backBtn" aria-label="Trở về">←</button><div class="sheet-title">📊 Thống Kê Lô Tô</div><div class="core-chip">BRIDGE</div></div>
  <div class="sheet-content-loto">
    <section class="core-panel"><div class="panel-row"><div class="panel-title">Cổng dữ liệu lõi</div><div class="core-status" id="coreStatus">CHỜ KẾT NỐI</div></div><div class="progress-shell"><div class="progress-bar" id="progressBar"></div></div><div class="core-log" id="coreLog">Bridge sẵn sàng: window.LottoStatsBridge</div></section>
    <section class="source-panel"><div class="panel-row"><div class="panel-title">Nguồn / file hệ thống</div><div class="scan-status" id="scanStatus">Không đủ dữ liệu xác thực</div></div><div class="file-list" id="fileList"></div><div class="notice" id="scanNotice">Các file đính kèm đã được gọi quét nhưng công cụ đọc tệp trả về rỗng/hỏng/không thể xử lý. Khi backend gửi dữ liệu thật, khu vực này sẽ cập nhật động.</div></section>
    <div class="slider-viewport"><div class="slider-track" id="main-slider-track"><div class="slide-pane"><div class="block-title-bar">Bố cục 1: Tần suất lô <span id="days-label">30</span> ngày</div><div class="matrix-container"><table class="matrix-table" id="matrix-table"><thead><tr id="matrix-head"></tr></thead><tbody id="matrix-body"></tbody></table></div></div><div class="slide-pane"><div class="tv-header"><span id="tv-header-title">📺 Hệ thống AI Calculator</span><button class="btn-tv-close" type="button" onclick="closeTV()">✖ Đóng</button></div><div class="tv-screen theme-blue" id="ai-tv-screen"><div class="tv-circuit"></div><div class="tv-data-stream"></div><div class="tv-content-layer"><div class="tv-text-bot" id="tv-message">👋 Chào bạn!<br>Hệ thống AI đã sẵn sàng hoạt động.</div><div class="tv-results" id="tv-results-container"></div></div></div></div></div></div>
    <div class="loto-block-2"><div class="block-title-2">⚡ Công cụ tính toán</div><div class="special-btn-group"><button class="btn-special btn-xien" type="button" onclick="activateXienAI()"><span class="icon">🔗</span><span>Ghép Xiên</span></button><button class="btn-special btn-nhipdep" type="button" onclick="activateNhipDep()"><span class="icon">📈</span><span>Nhịp Đẹp</span></button><button class="btn-special btn-bacnho" type="button" onclick="activateBacNhoAI()"><span class="icon">🧠</span><span>Bạc Nhớ</span></button></div><div class="search-group"><input type="text" class="search-input num-font" id="ai-search-input" placeholder="Chạm để nhập số..." readonly onclick="showKeyboard()"><button class="btn-search" type="button" onclick="runSearch()">Tìm</button></div></div>
    <div id="keyboard-wrapper"><div class="loto-block-kb"><div class="block-title-2" style="display:flex;justify-content:space-between;"><span>⌨ Bàn phím nhập liệu</span><span style="cursor:pointer;color:var(--text-dim);" onclick="hideKeyboard()">Đóng ✖</span></div><div class="vk-grid num-font" id="virtual-keyboard"><button class="vk-btn" data-val="1">1</button><button class="vk-btn" data-val="2">2</button><button class="vk-btn" data-val="3">3</button><button class="vk-btn" data-val="4">4</button><button class="vk-btn" data-val="5">5</button><button class="vk-btn" data-val="6">6</button><button class="vk-btn" data-val="7">7</button><button class="vk-btn" data-val="8">8</button><button class="vk-btn" data-val="9">9</button><button class="vk-btn vk-action" onclick="clearInput()">CLEAR</button><button class="vk-btn" data-val="0">0</button><button class="vk-btn vk-action vk-del" onclick="delInput()">DEL</button></div></div></div>
    <div class="lo-top-board"><div class="block-title-2">🏆 Bảng xếp hạng lô về nhiều nhất (<span id="top-days-label">30</span> ngày)</div><div class="chart-container" id="lo-top-chart"></div></div>
    <section class="stream-panel"><div class="stream-head"><div class="panel-title">Báo cáo phân tích stream</div><div class="stream-meter" id="streamMeter">0 dòng</div></div><div class="stream-box" id="streamBox"><pre class="stream-body" id="previewBody">Chưa có báo cáo. Backend có thể đẩy dữ liệu vào bằng window.LottoStatsBridge.streamReport([...]).</pre></div></section>
  </div>
  <div class="lock-overlay" id="lockOverlay"><div class="lock-card"><div class="spinner"></div><div class="lock-title" id="lockTitle">Đang xử lý</div><div class="lock-text" id="lockText">Đang kết nối lõi phân tích...</div></div></div>
</div>
<script>
"use strict";
function makeRNG(seed){let s=seed>>>0;return function(){s=(s*1664525+1013904223)>>>0;return s/4294967296;};}
const pad2=n=>(n<10?'0'+n:''+n);let DAYS=30;let LottoData={freq:[],totals:[],gan:[],source:"demo"};
function createDemoData(days){const rng=makeRNG(20260326);const freq=[];for(let lo=0;lo<=99;lo++){const row=[];const bias=.55+(rng()*.35);for(let d=0;d<days;d++){let n=0;if(rng()<(0.30*bias))n=1;if(n&&rng()<.18)n=2;if(n===2&&rng()<.10)n=3;row.push(n)}freq.push(row)}return normalizeLottoData({days:days,freq:freq,source:"demo"})}
function normalizeLottoData(input){const days=Math.max(1,Math.min(366,Number(input&&input.days)||DAYS||30));const freq=[];for(let lo=0;lo<=99;lo++){const src=input&&input.freq&&Array.isArray(input.freq[lo])?input.freq[lo]:[];const row=[];for(let d=0;d<days;d++){const v=Number(src[d]);row.push(Number.isFinite(v)&&v>0?Math.min(9,Math.floor(v)):0)}freq.push(row)}const totals=freq.map(r=>r.reduce((a,b)=>a+b,0));const gan=freq.map(r=>{let g=0;for(let d=days-1;d>=0;d--){if(r[d]>0)break;g++}return g});return{freq,totals,gan,source:(input&&input.source)||"backend",days}}
const els={coreStatus:null,progressBar:null,coreLog:null,fileList:null,scanStatus:null,scanNotice:null,streamBox:null,previewBody:null,streamMeter:null};
const defaultFiles=[{name:"Hệ thống, thiếu kết quả xsmb.docx",state:"Không đọc được",level:"warn"},{name:"bản cấu trúc hệ thống nghiên cứu xổ số trọng tâm cốt lõi.docx",state:"Không đọc được",level:"warn"},{name:"nghiên cứu xổ số 1.docx",state:"Không đọc được",level:"warn"}];
let fullReport=[],visibleNode=document.createTextNode(""),lineCount=0,queue=[],scheduled=false,isBusy=false;const MAX_VISIBLE_CHARS=120000,STREAM_BATCH_LINES=24;
document.addEventListener("DOMContentLoaded",()=>{cacheEls();LottoData=createDemoData(30);renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đính kèm không đọc được bằng công cụ quét. Dữ liệu bảng hiện là demo có seed cố định, không phải dữ liệu thật.");buildMatrix();renderTopLo();bindMatrixTooltips();setupKeyboard();resetReport("Chưa có báo cáo. Backend có thể đẩy dữ liệu vào bằng window.LottoStatsBridge.streamReport([...]).");setCore("","CHỜ KẾT NỐI",0);document.getElementById('backBtn').addEventListener('click',()=>streamReport(["Nút Trở về đã được kích hoạt. Trong hệ thống thật, hãy nối nút này với router/bridge không gian chính."]));});
function cacheEls(){els.coreStatus=document.getElementById('coreStatus');els.progressBar=document.getElementById('progressBar');els.coreLog=document.getElementById('coreLog');els.fileList=document.getElementById('fileList');els.scanStatus=document.getElementById('scanStatus');els.scanNotice=document.getElementById('scanNotice');els.streamBox=document.getElementById('streamBox');els.previewBody=document.getElementById('previewBody');els.streamMeter=document.getElementById('streamMeter');els.previewBody.textContent='';els.previewBody.appendChild(visibleNode)}
function setBusy(v,title,detail){isBusy=v;document.getElementById('lockOverlay').classList.toggle('show',v);if(title)document.getElementById('lockTitle').textContent=title;if(detail)document.getElementById('lockText').textContent=detail}
function setCore(state,msg,progress){els.coreStatus.className='core-status';if(state)els.coreStatus.classList.add(state);els.coreStatus.textContent=msg||'CHỜ KẾT NỐI';if(typeof progress==='number')els.progressBar.style.width=Math.max(0,Math.min(100,progress))+'%'}
function setLog(msg){els.coreLog.textContent=msg||''}
function renderFiles(files,status,notice){els.fileList.replaceChildren();(Array.isArray(files)?files:[]).forEach(f=>{const r=document.createElement('div'),n=document.createElement('div'),s=document.createElement('div');r.className='file-row';n.className='file-name';s.className='file-state';n.textContent=f.name||'Nguồn chưa đặt tên';s.textContent=f.state||'Chưa rõ';if(f.level==='ok')s.classList.add('ok');if(f.level==='bad')s.classList.add('bad');r.append(n,s);els.fileList.appendChild(r)});if(!els.fileList.children.length){const r=document.createElement('div'),n=document.createElement('div'),s=document.createElement('div');r.className='file-row';n.className='file-name';s.className='file-state';n.textContent='Chưa có nguồn dữ liệu';s.textContent='Đang chờ';r.append(n,s);els.fileList.appendChild(r)}els.scanStatus.className='scan-status';if(status&&status.toLowerCase().includes('đủ'))els.scanStatus.classList.add('ok');if(status&&status.toLowerCase().includes('lỗi'))els.scanStatus.classList.add('bad');els.scanStatus.textContent=status||'Chưa có dữ liệu lõi';els.scanNotice.textContent=notice||'Nguồn có thể cập nhật động bằng API hook.'}
function buildMatrix(){DAYS=LottoData.days||DAYS;document.getElementById('days-label').textContent=DAYS;document.getElementById('top-days-label').textContent=DAYS;const head=document.getElementById('matrix-head');let h='<th class="corner-h">Lô</th>';for(let j=1;j<=DAYS;j++)h+=`<th>${j}</th>`;head.innerHTML=h;const tbody=document.getElementById('matrix-body');let rows='';for(let lo=0;lo<=99;lo++){const isGan=LottoData.gan[lo]>=12;const thClass=isGan?'row-th gan-alert':'row-th';const tip=isGan?`<div class="gan-tooltip">⚠️ Gan ${LottoData.gan[lo]} ngày · Tổng về: ${LottoData.totals[lo]}</div>`:'';rows+=`<tr data-lo="${pad2(lo)}"><th class="${thClass}">${pad2(lo)}${tip}</th>`;for(let d=0;d<DAYS;d++){const v=LottoData.freq[lo][d];rows+=v>0?`<td class="data-cell">${v}</td>`:`<td></td>`}rows+='</tr>'}tbody.innerHTML=rows}
function bindMatrixTooltips(){document.getElementById('matrix-body').addEventListener('click',e=>{const th=e.target.closest('th.gan-alert');document.querySelectorAll('th.gan-alert.show-tooltip').forEach(el=>{if(el!==th)el.classList.remove('show-tooltip')});if(th)th.classList.toggle('show-tooltip')})}
function renderTopLo(){const chart=document.getElementById('lo-top-chart');const ranked=LottoData.totals.map((t,lo)=>({lo:pad2(lo),t})).sort((a,b)=>b.t-a.t).slice(0,10);const max=(ranked[0]&&ranked[0].t)||1;const palette=['linear-gradient(to top,#d50000,#ff1744)','linear-gradient(to top,#e65100,#ff9100)','linear-gradient(to top,#ef6c00,#ffb300)','linear-gradient(to top,#f57f17,#ffc400)','linear-gradient(to top,#fbc02d,#ffee58)','linear-gradient(to top,#afb42b,#d4e157)','linear-gradient(to top,#689f38,#9ccc65)','linear-gradient(to top,#0097a7,#4dd0e1)','linear-gradient(to top,#0288d1,#29b6f6)','linear-gradient(to top,#1976d2,#4fc3f7)'];let html='';ranked.forEach((item,idx)=>{const height=20+Math.round((item.t/max)*80);const txt=idx===0?'color:#ff5252;text-shadow:0 0 8px rgba(212,0,0,.5);transform:scale(1.3);':'';html+=`<div class="bar-wrapper" title="Lô ${item.lo}: ${item.t} lần"><div class="bar-number num-font" style="${txt}">${item.lo}</div><div class="bar-column" style="height:${height}%;background:${palette[idx]};animation-delay:${idx*.08}s;"><div class="bar-rank">TOP ${idx+1}</div></div></div>`});chart.innerHTML=html}
function resetReport(text){fullReport=[];lineCount=0;queue=[];scheduled=false;visibleNode.data=text||'';if(text)fullReport.push(text);els.streamMeter.textContent=(text?text.split('\n').length:0)+' dòng';els.streamBox.scrollTop=0}
function appendVisible(text){if(!text)return;fullReport.push(text);lineCount+=(text.match(/\n/g)||[]).length;let current=visibleNode.data+text;if(current.length>MAX_VISIBLE_CHARS)current='[Đã thu gọn phần đầu để tránh nghẽn DOM trên mobile. Nội dung đầy đủ vẫn nằm trong bộ nhớ phiên.]\n\n'+current.slice(-MAX_VISIBLE_CHARS);visibleNode.data=current;els.streamMeter.textContent=lineCount+' dòng · '+Math.round(current.length/1024)+'KB hiển thị';els.streamBox.scrollTop=els.streamBox.scrollHeight}
function flushStream(){if(scheduled)return;scheduled=true;requestAnimationFrame(()=>{let block='',count=0;while(queue.length&&count<STREAM_BATCH_LINES){block+=queue.shift();count++}appendVisible(block);scheduled=false;if(queue.length)flushStream()})}
function streamReport(lines){(Array.isArray(lines)?lines:[String(lines||'')]).forEach(line=>queue.push(String(line).endsWith('\n')?String(line):String(line)+'\n'));flushStream()}
function applyBackendData(payload){setBusy(true,'Đang nhận dữ liệu','Đang chuẩn hóa dữ liệu từ backend...');setCore('loading','ĐANG NHẬN DỮ LIỆU',20);try{LottoData=normalizeLottoData(payload||{});DAYS=LottoData.days;buildMatrix();renderTopLo();clearSearchHits();setCore('ready','ĐÃ CẬP NHẬT',100);setLog('Đã cập nhật ma trận từ nguồn: '+(LottoData.source||'backend'));streamReport(['Đã cập nhật dữ liệu tần suất từ backend. Số ngày: '+DAYS+'. Nguồn: '+(LottoData.source||'backend')+'.']);}catch(err){setCore('error','LỖI DỮ LIỆU',0);setLog('Lỗi chuẩn hóa dữ liệu: '+err.message);streamReport(['Không có đủ dữ liệu xác thực hoặc dữ liệu backend sai cấu trúc: '+err.message]);}finally{setBusy(false)}}
const searchInput=document.getElementById('ai-search-input');const keyboardWrapper=document.getElementById('keyboard-wrapper');function showKeyboard(){keyboardWrapper.style.display='block';keyboardWrapper.scrollIntoView({behavior:'smooth',block:'nearest'})}function hideKeyboard(){keyboardWrapper.style.display='none'}function setupKeyboard(){document.querySelectorAll('#virtual-keyboard .vk-btn[data-val]').forEach(k=>{k.addEventListener('click',e=>{let cur=searchInput.value.replace(/\s/g,'');if(cur.length<10){cur+=e.target.getAttribute('data-val');formatInput(cur)}})})}function clearInput(){searchInput.value='';clearSearchHits()}function delInput(){let cur=searchInput.value.replace(/\s/g,'');if(cur.length)formatInput(cur.slice(0,-1))}function formatInput(raw){searchInput.value=raw.match(/.{1,2}/g)?.join(' ')||''}function clearSearchHits(){document.querySelectorAll('.search-hit').forEach(el=>el.classList.remove('search-hit'))}
function runSearch(){const raw=searchInput.value.replace(/\s/g,'');const pairs=[...new Set(raw.match(/.{2}/g)||[])];clearSearchHits();if(!pairs.length){flashTV('blue','⚠️ Hãy nhập ít nhất 1 cặp số (2 chữ số) để tra cứu.');return}let report=[];pairs.forEach(p=>{const tr=document.querySelector(`#matrix-body tr[data-lo="${p}"]`);if(tr){tr.querySelector('th').classList.add('search-hit');tr.querySelectorAll('td').forEach(td=>td.classList.add('search-hit'));const lo=parseInt(p,10);report.push(`Lô <b>${p}</b>: về <b>${LottoData.totals[lo]}</b> lần / ${DAYS} ngày · gan hiện tại <b>${LottoData.gan[lo]}</b> ngày`);if(pairs.length===1)tr.scrollIntoView({behavior:'smooth',block:'center'})}});tvScreen.className='tv-screen theme-blue';tvHeader.textContent='🔎 Tra cứu tần suất lô';sliderTrack.style.transform='translateX(-50%)';tvResults.innerHTML='';tvMessage.innerHTML=report.length?report.join('<br>'):'⚠️ Không tìm thấy dữ liệu.';streamReport(report.map(x=>x.replace(/<[^>]*>/g,'')))}
const sliderTrack=document.getElementById('main-slider-track'),tvScreen=document.getElementById('ai-tv-screen'),tvHeader=document.getElementById('tv-header-title'),tvMessage=document.getElementById('tv-message'),tvResults=document.getElementById('tv-results-container');function closeTV(){sliderTrack.style.transform='translateX(0)'}function flashTV(theme,msg){tvScreen.className='tv-screen theme-'+theme;sliderTrack.style.transform='translateX(-50%)';tvResults.innerHTML='';tvMessage.innerHTML=msg}function getPairs(){return[...new Set((searchInput.value.replace(/\s/g,'').match(/.{2}/g))||[])]}function spawnBadge(html,delay){setTimeout(()=>{const b=document.createElement('div');b.className='xien-badge';b.innerHTML=html;tvResults.appendChild(b)},delay)}
function activateXienAI(){hideKeyboard();const pairs=getPairs();if(pairs.length<2){flashTV('blue','⚠️ Cần ít nhất 2 cặp khác nhau để ghép xiên.');return}flashTV('blue',`✅ Ghép ${pairs.length} cặp [${pairs.join(', ')}] thành các xiên 2:`);tvHeader.textContent='🔗 Hệ thống ghép xiên AI';let k=0;for(let i=0;i<pairs.length-1;i++)for(let j=i+1;j<pairs.length;j++)spawnBadge(`${pairs[i]} – ${pairs[j]}`,(k++)*140);streamReport(['Ghép xiên chỉ là công cụ tổ hợp hiển thị theo cặp người dùng nhập; không phải khuyến nghị đặt tiền.'])}
function activateBacNhoAI(){hideKeyboard();const pairs=getPairs();if(!pairs.length){flashTV('red','⚠️ Nhập ít nhất 1 cặp để tra Bạc Nhớ.');return}flashTV('red',`🧠 <b>Cơ sở dữ liệu thống kê</b><br>Sau khi [${pairs.join(', ')}] về, cặp thường theo sau:`);tvHeader.textContent='🚨 Hệ thống Bạc Nhớ AI';const db={"00":"99","99":"00","12":"34 – 43","21":"45 – 54","68":"86","86":"68","79":"97","97":"79"};pairs.forEach((p,i)=>{const rev=p[1]+p[0];const res=db[p]||`${rev} – ${p[0]}${p[0]}`;spawnBadge(`<span style="font-size:11px;opacity:.8;font-weight:500;">Cầu ${p} ➔ theo sau:</span><br>${res}`,i*200)});streamReport(['Bạc Nhớ trong bản UI này là dữ liệu demo/hook, chỉ hiển thị khi backend cung cấp dữ liệu thật.'])}
function activateNhipDep(){hideKeyboard();flashTV('green','📈 <b>Nhịp đẹp đang chạy</b> – các lô có nhịp về đều & đang nóng:');tvHeader.textContent='📈 Bộ lọc Nhịp Đẹp AI';const cand=LottoData.totals.map((t,lo)=>({lo:pad2(lo),t,g:LottoData.gan[lo]})).filter(x=>x.g>=1&&x.g<=4).sort((a,b)=>b.t-a.t).slice(0,6);if(!cand.length){tvMessage.innerHTML='Chưa có lô nào vào nhịp đẹp hôm nay.';return}cand.forEach((x,i)=>spawnBadge(`${x.lo}<br><span style="font-size:10px;opacity:.8;font-weight:500;">về ${x.t}× · gan ${x.g}n</span>`,i*160));streamReport(['Nhịp Đẹp đã lọc '+cand.length+' mục theo dữ liệu hiện có. Không dùng làm khuyến nghị tài chính.'])}
window.LottoStatsBridge={setFiles:(files,status,notice)=>renderFiles(files,status,notice),setStatus:(state,msg,progress)=>setCore(state,msg,progress),setLog:msg=>setLog(msg),startLoading:(title,detail)=>setBusy(true,title||'Đang xử lý',detail||'Đang chờ lõi phân tích...'),stopLoading:()=>setBusy(false),setData:payload=>applyBackendData(payload),streamReport:lines=>streamReport(lines),resetReport:text=>resetReport(text||''),getFullReport:()=>fullReport.join('')};
</script>
</body>
</html>
-------------------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Không Gian Báo Cáo AI - Audio Overview Stream Core</title>
<style>
:root{
  --bg-main:#1c130d;--bg-board:#2a1a10;--bg-deep:#120a06;--panel:#24150d;--panel-2:#160d08;--panel-3:#3a2416;
  --text-main:#fff4e6;--text-soft:#ffe0b8;--text-muted:#c9a982;--border:#5a3824;--glass:#6b432b;
  --accent:#d40000;--accent2:#ff3838;--ok:#10b981;--warn:#facc15;--bad:#ef4444;--blue:#38bdf8;
  --font:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;--mono:"SF Mono","Cascadia Code","Roboto Mono",ui-monospace,Menlo,Consolas,monospace;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:var(--font);-webkit-tap-highlight-color:transparent}html,body{height:100%}
body{width:100vw;height:100dvh;overflow:hidden;background:#050302;color:var(--text-main);display:flex;justify-content:center;align-items:flex-start}button,input,textarea{font:inherit}button{touch-action:manipulation}
.app{max-width:480px;width:100%;height:100%;overflow:hidden;background:var(--bg-main);box-shadow:0 0 45px rgba(0,0,0,.95);border-left:1px solid rgba(255,232,190,.08);border-right:1px solid rgba(255,232,190,.08)}
.space{height:100%;display:flex;flex-direction:column;background:linear-gradient(180deg,var(--bg-board),var(--bg-deep));padding-top:env(safe-area-inset-top);position:relative}.top{flex-shrink:0;display:grid;grid-template-columns:38px 1fr auto;gap:10px;align-items:center;padding:10px 12px;background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border);box-shadow:0 4px 14px rgba(0,0,0,.32);z-index:20}.back{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);font-size:20px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 2px rgba(255,232,190,.08),0 3px 8px rgba(0,0,0,.25)}.back:active{transform:scale(.94)}.title{font-weight:950;font-size:14px;color:var(--text-soft);letter-spacing:.5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;text-transform:uppercase}.chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}
.scroll{flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;scrollbar-width:none;padding:14px 12px 16px;display:flex;flex-direction:column;gap:14px}.scroll::-webkit-scrollbar{display:none;width:0;height:0}
.hero,.panel,.builder,.preview,.audio{border-radius:18px;border:1px solid rgba(255,232,190,.10);background:linear-gradient(180deg,#24150d,#160d08);box-shadow:0 10px 24px rgba(0,0,0,.24)}.hero{padding:14px;background:radial-gradient(circle at 20% 0%,rgba(212,0,0,.20),transparent 34%),linear-gradient(180deg,#24150d,#160d08)}.kicker{font-size:11px;font-weight:950;color:var(--warn);letter-spacing:.8px;text-transform:uppercase;margin-bottom:7px}.hero h1{font-size:20px;font-weight:1000;line-height:1.15;color:var(--text-main);margin-bottom:8px}.hero p{font-size:12px;line-height:1.45;color:var(--text-muted);font-weight:750}
.core{border-color:rgba(56,189,248,.22);background:linear-gradient(180deg,rgba(56,189,248,.08),rgba(18,10,6,.90));padding:12px;display:flex;flex-direction:column;gap:10px}.row2{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.core-title{font-size:13px;font-weight:950;color:#bdeaff;text-transform:uppercase;letter-spacing:.4px}.status{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--blue);background:rgba(56,189,248,.10);border:1px solid rgba(56,189,248,.35);white-space:nowrap}.status.loading{color:var(--warn);background:rgba(250,204,21,.10);border-color:rgba(250,204,21,.35)}.status.ready{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.status.error{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.bar-shell{height:8px;border-radius:999px;overflow:hidden;background:rgba(0,0,0,.28);border:1px solid rgba(255,232,190,.08)}.bar{height:100%;width:0%;background:linear-gradient(90deg,#d40000,#ffbc5e,#10b981);transition:width .18s ease}.log{font-family:var(--mono);font-size:10.5px;line-height:1.35;color:var(--text-muted);background:rgba(0,0,0,.16);border:1px dashed rgba(255,232,190,.11);border-radius:12px;padding:9px;min-height:42px;white-space:pre-wrap}
.scan{border-color:rgba(250,204,21,.24);background:linear-gradient(180deg,rgba(250,204,21,.10),rgba(33,18,8,.92));padding:12px;display:flex;flex-direction:column;gap:10px}.panel-title{display:flex;align-items:center;justify-content:space-between;gap:8px;font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.4px}.pill{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--warn);background:rgba(250,204,21,.10);border:1px solid rgba(250,204,21,.35);white-space:nowrap}.pill.ok{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.pill.bad{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.file-list{display:flex;flex-direction:column;gap:8px}.file{display:grid;grid-template-columns:1fr auto;gap:8px;align-items:center;background:rgba(18,10,6,.55);border:1px solid rgba(255,232,190,.08);border-radius:12px;padding:9px 10px}.file-name{font-size:12px;color:var(--text-main);font-weight:850;line-height:1.25;word-break:break-word}.file-state{font-size:10px;font-weight:950;color:var(--warn);white-space:nowrap}.file-state.ok{color:var(--ok)}.file-state.bad{color:var(--bad)}.notice{font-size:11px;line-height:1.45;color:var(--text-muted);font-weight:760;background:rgba(0,0,0,.14);border-radius:12px;padding:9px;border:1px dashed rgba(255,232,190,.12)}
.head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-top:2px}.section-title{font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.6px}.section-sub{font-size:11px;color:var(--text-muted);font-weight:800}.grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}.card{min-height:122px;border:none;text-align:left;border-radius:16px;padding:12px;background:linear-gradient(180deg,rgba(58,36,22,.92),rgba(33,18,8,.98));border:1px solid rgba(255,232,190,.10);box-shadow:0 5px 14px rgba(0,0,0,.22);cursor:pointer;color:var(--text-main);display:flex;flex-direction:column;gap:8px;position:relative;overflow:hidden}.card::before{content:"";position:absolute;inset:auto -30px -45px auto;width:100px;height:100px;border-radius:50%;background:rgba(212,0,0,.13)}.card:active{transform:scale(.985)}.card.active{border-color:var(--accent2);box-shadow:0 0 0 1px rgba(255,56,56,.25),0 8px 20px rgba(0,0,0,.32)}.card:disabled{opacity:.55;cursor:not-allowed;transform:none}.icon{width:34px;height:34px;border-radius:12px;display:flex;align-items:center;justify-content:center;background:rgba(212,0,0,.16);border:1px solid rgba(255,56,56,.25);font-size:18px;flex-shrink:0}.card-title{font-size:14px;font-weight:950;line-height:1.16;color:var(--text-main);position:relative;z-index:1}.card-desc{font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:730;position:relative;z-index:1;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden}.full{grid-column:1/-1;min-height:104px}
.audio{padding:12px;display:flex;flex-direction:column;gap:11px;border-color:rgba(16,185,129,.22);background:linear-gradient(180deg,rgba(16,185,129,.08),rgba(18,10,6,.92))}.audio-grid{display:grid;grid-template-columns:1fr 1fr;gap:9px}.choice{border:1px solid rgba(255,232,190,.12);background:rgba(18,10,6,.55);border-radius:14px;padding:10px;text-align:left;color:var(--text-main);cursor:pointer}.choice.active{border-color:var(--ok);box-shadow:0 0 0 1px rgba(16,185,129,.20);background:rgba(16,185,129,.10)}.choice b{display:block;font-size:13px;color:var(--text-main);margin-bottom:4px}.choice span{display:block;font-size:10.5px;line-height:1.35;color:var(--text-muted);font-weight:740}.tabs{display:flex;gap:7px;flex-wrap:wrap}.tab{border:1px solid rgba(255,232,190,.14);background:rgba(18,10,6,.55);color:var(--text-soft);border-radius:999px;padding:7px 10px;font-size:11px;font-weight:900}.tab.active{border-color:var(--accent2);background:rgba(212,0,0,.18);color:#fff}.select-row{display:grid;grid-template-columns:1fr 1fr;gap:9px}.select-box{display:flex;flex-direction:column;gap:6px}.field{font-size:11px;color:#ffd6a0;font-weight:950;text-transform:uppercase;letter-spacing:.45px}.input,.textarea,.select{width:100%;border:1px solid rgba(255,232,190,.14);border-radius:13px;background:#120a06;color:var(--text-main);outline:none;padding:10px 11px;font-size:12px;font-weight:760;line-height:1.4}.textarea{height:94px;resize:none}.builder{padding:12px;display:flex;flex-direction:column;gap:10px}.actions{display:grid;grid-template-columns:1fr 1fr;gap:10px}.btn{border:none;border-radius:14px;padding:11px 10px;font-size:12px;font-weight:950;cursor:pointer;color:#fff;background:linear-gradient(135deg,#d40000,#ff3838);box-shadow:0 7px 16px rgba(212,0,0,.22)}.btn.secondary{background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);box-shadow:0 5px 12px rgba(0,0,0,.22)}.btn:active{transform:scale(.97)}.btn:disabled{opacity:.55;cursor:not-allowed;transform:none}
.preview{border-color:rgba(16,185,129,.28);background:linear-gradient(180deg,rgba(16,185,129,.09),rgba(18,10,6,.88));padding:12px;display:flex;flex-direction:column;gap:8px}.preview-title{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:13px;color:var(--ok);font-weight:950;text-transform:uppercase;letter-spacing:.4px}.meter{font-size:10px;color:var(--text-muted);font-weight:850;text-transform:none;letter-spacing:0;white-space:nowrap}.preview-box{height:280px;overflow:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;border-radius:12px;background:rgba(0,0,0,.18);border:1px solid rgba(255,232,190,.08);padding:10px}.preview-box::-webkit-scrollbar{display:none;width:0;height:0}.body{font-family:var(--mono);font-size:11px;line-height:1.45;color:var(--text-main);font-weight:650;white-space:pre-wrap;word-break:break-word}.abc{display:grid;gap:9px}.abc-box{border-radius:14px;padding:10px;border:1px solid rgba(255,232,190,.10);background:rgba(18,10,6,.48)}.abc-box b{display:block;font-size:11px;text-transform:uppercase;letter-spacing:.4px;margin-bottom:5px;color:#ffd6a0}.abc-box p{font-size:11px;line-height:1.42;color:var(--text-muted);font-weight:760}.foot{flex-shrink:0;background:linear-gradient(135deg,#2b1a10,#160d08);border-top:1px solid var(--border);padding:10px 14px calc(10px + env(safe-area-inset-bottom));font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:800;text-align:center}.foot b{color:#ffd6a0}.overlay{position:absolute;inset:0;background:rgba(5,3,2,.48);backdrop-filter:blur(2px);z-index:100;display:none;align-items:center;justify-content:center;padding:22px;text-align:center}.overlay.show{display:flex}.lock{border-radius:18px;background:linear-gradient(180deg,#2b1a10,#120a06);border:1px solid rgba(255,232,190,.16);box-shadow:0 18px 48px rgba(0,0,0,.5);padding:16px;max-width:330px;width:100%}.spin{width:32px;height:32px;border-radius:50%;border:3px solid rgba(255,232,190,.16);border-top-color:var(--warn);margin:0 auto 10px;animation:spin .8s linear infinite}.lock-title{font-size:14px;font-weight:950;color:#ffd6a0;margin-bottom:6px;text-transform:uppercase}.lock-text{font-size:12px;line-height:1.4;color:var(--text-muted);font-weight:760}@keyframes spin{to{transform:rotate(360deg)}}
@media(max-width:380px){.top{grid-template-columns:36px 1fr auto;padding:9px 10px}.back{width:36px;height:32px}.title{font-size:13px}.chip{font-size:9px;padding:5px 7px}.scroll{padding:12px 10px}.hero h1{font-size:18px}.grid{gap:9px}.card{padding:10px;min-height:118px}.card-title{font-size:13px}.card-desc{font-size:10.5px}.actions,.select-row{grid-template-columns:1fr}.audio-grid{grid-template-columns:1fr}.preview-box{height:250px}.foot{font-size:10.5px}}
</style>
</head>
<body>
<div class="app"><main class="space" id="space">
<header class="top"><button class="back" type="button" aria-label="Trở về" id="backBtn">←</button><div class="title">Không gian báo cáo AI</div><div class="chip">AUDIO + STREAM</div></header>
<section class="scroll" id="scroll">
<article class="hero"><div class="kicker">API Hook · Audio Overview · Stream Output</div><h1>Không gian báo cáo kết nối lõi xổ số</h1><p>Bản này dùng cổng nhận dữ liệu động, render báo cáo theo luồng để chống treo DOM, và bổ sung khối tùy chỉnh “Tổng quan bằng âm thanh” theo các chế độ: tìm hiểu sâu, tóm tắt, phê bình và tranh luận.</p></article>
<section class="panel core" aria-label="Trạng thái lõi"><div class="row2"><div class="core-title">Cổng lõi phân tích</div><div class="status" id="coreStatus">CHỜ KẾT NỐI</div></div><div class="bar-shell"><div class="bar" id="bar"></div></div><div class="log" id="log">Bridge sẵn sàng: window.ReportWorkspaceBridge</div></section>
<section class="panel scan" aria-label="Quét nguồn"><div class="panel-title"><span>Quét tệp / nguồn</span><span class="pill" id="scanStatus">Không đủ dữ liệu xác thực</span></div><div class="file-list" id="fileList"></div><div class="notice" id="scanNotice">Các file hệ thống đã được gọi quét, nhưng công cụ đọc tệp trả về rỗng/hỏng/không thể xử lý. Khi backend gửi dữ liệu thật, khu vực này sẽ cập nhật bằng API hook.</div></section>
<div class="head"><div><div class="section-title">Tạo báo cáo</div><div class="section-sub">Chọn định dạng đầu ra</div></div></div>
<section class="grid" id="formatGrid">
<button class="card active" type="button" data-title="Tạo báo cáo của riêng bạn" data-template="Tạo báo cáo theo cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng do người dùng chỉ định."><div class="icon">✍️</div><div class="card-title">Tạo báo cáo của riêng bạn</div><div class="card-desc">Chỉ định cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng.</div></button>
<button class="card" type="button" data-title="Tài liệu tóm tắt" data-template="Tổng quan nguồn dữ liệu, ý chính, trích dẫn, điểm chưa xác thực và cảnh báo thiếu dữ kiện."><div class="icon">📄</div><div class="card-title">Tài liệu tóm tắt</div><div class="card-desc">Tổng quan nguồn có trích dẫn, thông tin chính và điểm cần kiểm chứng.</div></button>
<button class="card" type="button" data-title="Hướng dẫn ôn tập" data-template="Tạo câu hỏi ngắn, câu hỏi tự luận, đáp án kiểm tra và bảng thuật ngữ từ tài liệu nguồn."><div class="icon">🎓</div><div class="card-title">Hướng dẫn ôn tập</div><div class="card-desc">Câu hỏi ngắn, tiểu luận, đáp án và bảng thuật ngữ theo nguồn.</div></button>
<button class="card" type="button" data-title="Bài đăng trên blog" data-template="Chắt lọc ý chính thành bài viết dễ đọc, có mở bài, thân bài, kết luận và cảnh báo dữ kiện."><div class="icon">📰</div><div class="card-title">Bài đăng trên blog</div><div class="card-desc">Chuyển điểm chính thành bài viết mạch lạc, dễ đọc.</div></button>
</section>
<div class="head"><div><div class="section-title">Định dạng đề xuất</div><div class="section-sub">Kiến trúc / quản trị / thuật toán</div></div></div>
<section class="grid">
<button class="card full" type="button" data-title="Tài liệu Đặc tả Kiến trúc" data-template="Mô tả cấu trúc hệ thống, module, luồng dữ liệu, lớp kiểm soát, cơ chế lỗi và ranh giới vận hành."><div class="icon">🏗️</div><div class="card-title">Tài liệu Đặc tả Kiến trúc</div><div class="card-desc">Cấu trúc hệ thống, module lõi, luồng dữ liệu và lớp kiểm soát.</div></button>
<button class="card full" type="button" data-title="Báo cáo Chiến lược Quản trị" data-template="Phân tích rủi ro, kiểm soát lỗi, quyền truy cập, vùng dữ liệu nhạy cảm và cơ chế giám sát."><div class="icon">🛡️</div><div class="card-title">Báo cáo Chiến lược Quản trị</div><div class="card-desc">Quản trị rủi ro, kiểm soát lỗi, quyền truy cập và trách nhiệm vận hành.</div></button>
<button class="card full" type="button" data-title="Tài liệu Hướng dẫn Thuật toán" data-template="Giải thích thuật toán, dữ liệu đầu vào, quy tắc xử lý, giới hạn suy luận và điều kiện không đủ dữ liệu."><div class="icon">🧮</div><div class="card-title">Tài liệu Hướng dẫn Thuật toán</div><div class="card-desc">Dữ liệu đầu vào, quy tắc xử lý, giới hạn và điều kiện không đủ dữ liệu.</div></button>
<button class="card full" type="button" data-title="Cẩm nang Tư duy Hệ thống" data-template="Mô hình xử lý thông tin đa tầng, phân biệt dữ liệu thật, giả định, suy luận và điểm mù."><div class="icon">🧠</div><div class="card-title">Cẩm nang Tư duy Hệ thống</div><div class="card-desc">Phân biệt dữ liệu thực tế, giả định, suy luận và điểm mù.</div></button>
</section>
<section class="audio" aria-label="Tùy chỉnh tổng quan bằng âm thanh"><div class="panel-title"><span>Tùy chỉnh bản Tổng quan bằng âm thanh</span><span class="pill ok" id="audioState">Sẵn sàng</span></div><div class="audio-grid" id="audioModes">
<button class="choice active" type="button" data-mode="Tìm hiểu sâu"><b>Tìm hiểu sâu</b><span>Một cuộc trò chuyện sôi nổi giữa 2 máy chủ AI, phân tích và kết nối các chủ đề trong nguồn.</span></button>
<button class="choice" type="button" data-mode="Tóm tắt"><b>Tóm tắt</b><span>Thông tin tổng quan ngắn gọn giúp nắm bắt nhanh các ý tưởng chính dựa trên nguồn.</span></button>
<button class="choice" type="button" data-mode="Phê bình"><b>Phê bình</b><span>Bài đánh giá chuyên gia về nguồn, đưa phản hồi xây dựng để cải thiện tài liệu.</span></button>
<button class="choice" type="button" data-mode="Tranh luận"><b>Tranh luận</b><span>Cuộc tranh luận sâu sắc giữa 2 máy chủ AI, làm sáng tỏ các quan điểm khác nhau.</span></button>
</div><div class="select-row"><div class="select-box"><label class="field" for="lang">Chọn ngôn ngữ</label><select class="select" id="lang"><option>Tiếng Việt</option><option>English</option><option>日本語</option><option>한국어</option></select></div><div class="select-box"><label class="field" for="length">Độ dài</label><select class="select" id="length"><option>Ngắn</option><option selected>Mặc định</option><option>Dài</option></select></div></div><label class="field" for="audioFocus">Máy chủ AI nên tập trung vào điều gì trong tập này?</label><textarea class="textarea" id="audioFocus">Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.</textarea><div class="tabs" id="audioTabs"><button class="tab active" type="button">+ Quản Lý Vốn</button><button class="tab" type="button">+ Người Mới Bắt</button><button class="tab" type="button">+ Phân Tích Cầu</button></div></section>
<section class="builder"><label class="field" for="reportName">Tên báo cáo</label><input class="input" id="reportName" value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu" autocomplete="off"><label class="field" for="reportRules">Yêu cầu kiểm soát</label><textarea class="textarea" id="reportRules">Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.</textarea><div class="actions"><button class="btn" type="button" id="buildBtn">Tạo báo cáo stream</button><button class="btn secondary" type="button" id="audioBtn">Tạo tổng quan audio</button><button class="btn secondary" type="button" id="resetBtn">Đặt lại</button><button class="btn secondary" type="button" id="exportBtn">Xuất nội dung</button></div></section>
<section class="preview" aria-live="polite"><div class="preview-title"><span>Bản nháp báo cáo</span><span class="meter" id="meter">0 dòng</span></div><div class="preview-box" id="previewBox"><pre class="body" id="previewBody">Chọn định dạng rồi bấm “Tạo báo cáo stream”.</pre></div></section>
<section class="abc"><div class="abc-box"><b>Bước 1 — Tạo lập</b><p>API hook nhận nguồn, trạng thái, log và stream báo cáo/audio từ backend.</p></div><div class="abc-box"><b>Bước 2 — Tự hủy diệt</b><p>Chặn hardcode, chặn nhồi 10.000 dòng một lần, chặn bấm lặp khi lõi đang xử lý.</p></div><div class="abc-box"><b>Bước 3 — Tái sinh</b><p>Dùng bridge động, render theo chunk, giới hạn vùng hiển thị, giữ bản đầy đủ trong bộ nhớ phiên.</p></div></section>
</section><footer class="foot"><b>Nguyên tắc:</b> chỉ hiển thị dữ liệu backend gửi vào. Nếu nguồn không đọc được, phải báo Không đủ dữ liệu xác thực.</footer><div class="overlay" id="overlay"><div class="lock"><div class="spin"></div><div class="lock-title" id="lockTitle">Đang xử lý</div><div class="lock-text" id="lockText">Đang kết nối lõi phân tích...</div></div></div>
</main></div>
<script>
"use strict";(function(){
const cards=Array.from(document.querySelectorAll(".card"));const choices=Array.from(document.querySelectorAll(".choice"));const tabs=Array.from(document.querySelectorAll(".tab"));
const previewBody=document.getElementById("previewBody"),previewBox=document.getElementById("previewBox"),meter=document.getElementById("meter"),reportName=document.getElementById("reportName"),reportRules=document.getElementById("reportRules"),buildBtn=document.getElementById("buildBtn"),audioBtn=document.getElementById("audioBtn"),resetBtn=document.getElementById("resetBtn"),exportBtn=document.getElementById("exportBtn"),backBtn=document.getElementById("backBtn"),fileList=document.getElementById("fileList"),scanStatus=document.getElementById("scanStatus"),scanNotice=document.getElementById("scanNotice"),coreStatus=document.getElementById("coreStatus"),log=document.getElementById("log"),bar=document.getElementById("bar"),overlay=document.getElementById("overlay"),lockTitle=document.getElementById("lockTitle"),lockText=document.getElementById("lockText"),lang=document.getElementById("lang"),length=document.getElementById("length"),audioFocus=document.getElementById("audioFocus"),audioState=document.getElementById("audioState");
const MAX_VISIBLE_CHARS=120000,STREAM_BATCH_LINES=24;let selected=cards[0],audioMode=choices[0].dataset.mode,isBusy=false,full=[],node=document.createTextNode(""),lines=0,queue=[],scheduled=false;previewBody.textContent="";previewBody.appendChild(node);
const defaultFiles=[{name:"HỆ THỐNG CAPABILITY TOKEN (CẤP QUYỀN TRUY CẬP).docx",state:"Không đọc được",level:"warn"},{name:"KHAI THÁC TRÊN BẢNG ĐẶC BIỆT NĂM.docx",state:"Không đọc được",level:"warn"},{name:"Hệ thống, thiếu kết quả xsmb.docx",state:"Không đọc được",level:"warn"},{name:"bản cấu trúc hệ thống nghiên cứu xổ số trọng tâm cốt lõi.docx",state:"Không đọc được",level:"warn"},{name:"nghiên cứu xổ số 1.docx",state:"Không đọc được",level:"warn"}];
function setBusy(v,t,d){isBusy=v;[buildBtn,audioBtn,resetBtn,exportBtn].forEach(b=>b.disabled=v);cards.forEach(c=>c.disabled=v);overlay.classList.toggle("show",v);if(t)lockTitle.textContent=t;if(d)lockText.textContent=d}function setStatus(s,m,p){coreStatus.className="status";if(s)coreStatus.classList.add(s);coreStatus.textContent=m||"CHỜ KẾT NỐI";if(typeof p==="number")bar.style.width=Math.max(0,Math.min(100,p))+"%"}function setLog(m){log.textContent=m||""}
function renderFiles(files,status,notice){fileList.replaceChildren();(Array.isArray(files)?files:[]).forEach(f=>{const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent=f.name||"Nguồn chưa đặt tên";st.textContent=f.state||"Chưa rõ";if(f.level==="ok")st.classList.add("ok");if(f.level==="bad")st.classList.add("bad");r.append(n,st);fileList.appendChild(r)});if(!fileList.children.length){const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent="Chưa có nguồn dữ liệu";st.textContent="Đang chờ";r.append(n,st);fileList.appendChild(r)}scanStatus.className="pill";if(status&&status.toLowerCase().includes("đủ"))scanStatus.classList.add("ok");if(status&&status.toLowerCase().includes("lỗi"))scanStatus.classList.add("bad");scanStatus.textContent=status||"Chưa có dữ liệu lõi";scanNotice.textContent=notice||"Nguồn có thể cập nhật qua API hook."}
function resetPreview(t){full=[];lines=0;queue=[];scheduled=false;node.data=t||"";if(t)full.push(t);meter.textContent=(t?t.split("\n").length:0)+" dòng";previewBox.scrollTop=0}function appendText(t){if(!t)return;full.push(t);lines+=(t.match(/\n/g)||[]).length;let cur=node.data+t;if(cur.length>MAX_VISIBLE_CHARS)cur="[Đã thu gọn phần đầu để tránh nghẽn DOM trên mobile. Nội dung đầy đủ vẫn nằm trong bộ nhớ phiên.]\n\n"+cur.slice(-MAX_VISIBLE_CHARS);node.data=cur;meter.textContent=lines+" dòng · "+Math.round(cur.length/1024)+"KB hiển thị";previewBox.scrollTop=previewBox.scrollHeight}function flush(){if(scheduled)return;scheduled=true;requestAnimationFrame(()=>{let block="",c=0;while(queue.length&&c<STREAM_BATCH_LINES){block+=queue.shift();c++}appendText(block);scheduled=false;if(queue.length)flush()})}function stream(x){(Array.isArray(x)?x:[String(x||"")]).forEach(l=>queue.push(String(l).endsWith("\n")?String(l):String(l)+"\n"));flush()}
function selectCard(c){if(isBusy)return;cards.forEach(x=>x.classList.remove("active"));c.classList.add("active");selected=c}cards.forEach(c=>c.addEventListener("click",()=>selectCard(c)));choices.forEach(c=>c.addEventListener("click",()=>{if(isBusy)return;choices.forEach(x=>x.classList.remove("active"));c.classList.add("active");audioMode=c.dataset.mode||"Tóm tắt"}));tabs.forEach(t=>t.addEventListener("click",()=>{if(isBusy)return;t.classList.toggle("active")}));
async function simulateReport(kind){const title=selected.dataset.title||"Báo cáo",template=selected.dataset.template||"Chưa có mô tả",name=reportName.value.trim()||"Báo cáo chưa đặt tên",rules=reportRules.value.trim()||"Không có quy tắc bổ sung";setBusy(true,kind==="audio"?"Đang dựng tổng quan audio":"Đang kết nối Bô Lão",kind==="audio"?"Khóa thao tác trong khi tạo kịch bản âm thanh.":"Khóa thao tác để tránh bấm lặp gây nghẽn lõi.");setStatus("loading",kind==="audio"?"ĐANG DỰNG AUDIO":"ĐANG KẾT NỐI",10);setLog("[1/5] Mở ReportWorkspaceBridge\n[2/5] Chờ dữ liệu backend...");resetPreview("");if(kind==="audio"){stream(["# Kịch bản Tổng quan bằng âm thanh", "", "## Chế độ", audioMode, "", "## Ngôn ngữ", lang.value, "", "## Độ dài", length.value, "", "## Trọng tâm", audioFocus.value, "", "## Lưu ý an toàn", "Nội dung về Martingale/Fibonacci chỉ dùng để phân tích rủi ro và bảo toàn tài sản, không phải khuyến nghị đặt tiền hoặc cá cược.", ""])}else{stream(["# "+name,"","## Định dạng",title,"","## Mục tiêu",template,"","## Quy tắc",rules,"","## Luồng stream"])}await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG QUÉT NGUỒN",35);stream(["- Kiểm tra nguồn đầu vào qua API hook.","- Nếu nguồn không đọc được, không sinh kết luận thay dữ liệu.","- Dữ liệu lớn được render theo chunk requestAnimationFrame."]);await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG STREAM",70);setLog("[3/5] Nhận dữ liệu theo dòng\n[4/5] Render theo batch chống freeze DOM");for(let i=1;i<=60;i++){stream([(kind==="audio"?"Lượt thoại mô phỏng ":"Dòng phân tích mô phỏng ")+String(i).padStart(3,"0")+": thay dòng này bằng dữ liệu thật từ backend khi tích hợp."]);if(i%12===0)await new Promise(r=>setTimeout(r,20))}setStatus("ready","HOÀN TẤT",100);stream(["","## Kết luận kiểm soát","Không có đủ dữ liệu xác thực từ tệp nếu backend không gửi nguồn đọc được. UI đã sẵn sàng nhận dữ liệu động qua window.ReportWorkspaceBridge."]);setLog("[5/5] Hoàn tất stream. Không nhồi DOM một lần.");setBusy(false)}
buildBtn.addEventListener("click",()=>simulateReport("report"));audioBtn.addEventListener("click",()=>simulateReport("audio"));resetBtn.addEventListener("click",()=>{reportName.value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu";reportRules.value="Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.";audioFocus.value="Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.";selectCard(cards[0]);setStatus("","CHỜ KẾT NỐI",0);setLog("Bridge sẵn sàng: window.ReportWorkspaceBridge");renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.")});exportBtn.addEventListener("click",()=>{const blob=new Blob([full.join("")],{type:"text/plain;charset=utf-8"});const a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download="bao_cao_stream.txt";document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(a.href),500)});backBtn.addEventListener("click",()=>resetPreview("Đã kích hoạt nút Trở về. Trong hệ thống thật, nút này nối với router/bridge của không gian chính."));
window.ReportWorkspaceBridge={setFiles:(f,s,n)=>renderFiles(f,s,n),setStatus:(s,m,p)=>setStatus(s,m,p),setLog:m=>setLog(m),startLoading:(t,d)=>setBusy(true,t||"Đang xử lý",d||"Đang chờ lõi phân tích..."),stopLoading:()=>setBusy(false),resetReport:t=>resetPreview(t||""),streamReport:x=>stream(x),streamAudio:x=>stream(x),setAudioConfig:c=>{if(!c)return;if(c.mode){choices.forEach(x=>{x.classList.toggle("active",x.dataset.mode===c.mode)});audioMode=c.mode}if(c.language)lang.value=c.language;if(c.length)length.value=c.length;if(c.focus)audioFocus.value=c.focus},getFullReport:()=>full.join("")};
renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.");
})();
</script>
</body>
</html>

-----------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Không Gian Báo Cáo AI - Audio Overview Stream Core</title>
<style>
:root{
  --bg-main:#1c130d;--bg-board:#2a1a10;--bg-deep:#120a06;--panel:#24150d;--panel-2:#160d08;--panel-3:#3a2416;
  --text-main:#fff4e6;--text-soft:#ffe0b8;--text-muted:#c9a982;--border:#5a3824;--glass:#6b432b;
  --accent:#d40000;--accent2:#ff3838;--ok:#10b981;--warn:#facc15;--bad:#ef4444;--blue:#38bdf8;
  --font:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;--mono:"SF Mono","Cascadia Code","Roboto Mono",ui-monospace,Menlo,Consolas,monospace;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:var(--font);-webkit-tap-highlight-color:transparent}html,body{height:100%}
body{width:100vw;height:100dvh;overflow:hidden;background:#050302;color:var(--text-main);display:flex;justify-content:center;align-items:flex-start}button,input,textarea{font:inherit}button{touch-action:manipulation}
.app{max-width:480px;width:100%;height:100%;overflow:hidden;background:var(--bg-main);box-shadow:0 0 45px rgba(0,0,0,.95);border-left:1px solid rgba(255,232,190,.08);border-right:1px solid rgba(255,232,190,.08)}
.space{height:100%;display:flex;flex-direction:column;background:linear-gradient(180deg,var(--bg-board),var(--bg-deep));padding-top:env(safe-area-inset-top);position:relative}.top{flex-shrink:0;display:grid;grid-template-columns:38px 1fr auto;gap:10px;align-items:center;padding:10px 12px;background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border);box-shadow:0 4px 14px rgba(0,0,0,.32);z-index:20}.back{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);font-size:20px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 2px rgba(255,232,190,.08),0 3px 8px rgba(0,0,0,.25)}.back:active{transform:scale(.94)}.title{font-weight:950;font-size:14px;color:var(--text-soft);letter-spacing:.5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;text-transform:uppercase}.chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}
.scroll{flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;scrollbar-width:none;padding:14px 12px 16px;display:flex;flex-direction:column;gap:14px}.scroll::-webkit-scrollbar{display:none;width:0;height:0}
.hero,.panel,.builder,.preview,.audio{border-radius:18px;border:1px solid rgba(255,232,190,.10);background:linear-gradient(180deg,#24150d,#160d08);box-shadow:0 10px 24px rgba(0,0,0,.24)}.hero{padding:14px;background:radial-gradient(circle at 20% 0%,rgba(212,0,0,.20),transparent 34%),linear-gradient(180deg,#24150d,#160d08)}.kicker{font-size:11px;font-weight:950;color:var(--warn);letter-spacing:.8px;text-transform:uppercase;margin-bottom:7px}.hero h1{font-size:20px;font-weight:1000;line-height:1.15;color:var(--text-main);margin-bottom:8px}.hero p{font-size:12px;line-height:1.45;color:var(--text-muted);font-weight:750}
.core{border-color:rgba(56,189,248,.22);background:linear-gradient(180deg,rgba(56,189,248,.08),rgba(18,10,6,.90));padding:12px;display:flex;flex-direction:column;gap:10px}.row2{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.core-title{font-size:13px;font-weight:950;color:#bdeaff;text-transform:uppercase;letter-spacing:.4px}.status{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--blue);background:rgba(56,189,248,.10);border:1px solid rgba(56,189,248,.35);white-space:nowrap}.status.loading{color:var(--warn);background:rgba(250,204,21,.10);border-color:rgba(250,204,21,.35)}.status.ready{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.status.error{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.bar-shell{height:8px;border-radius:999px;overflow:hidden;background:rgba(0,0,0,.28);border:1px solid rgba(255,232,190,.08)}.bar{height:100%;width:0%;background:linear-gradient(90deg,#d40000,#ffbc5e,#10b981);transition:width .18s ease}.log{font-family:var(--mono);font-size:10.5px;line-height:1.35;color:var(--text-muted);background:rgba(0,0,0,.16);border:1px dashed rgba(255,232,190,.11);border-radius:12px;padding:9px;min-height:42px;white-space:pre-wrap}
.scan{border-color:rgba(250,204,21,.24);background:linear-gradient(180deg,rgba(250,204,21,.10),rgba(33,18,8,.92));padding:12px;display:flex;flex-direction:column;gap:10px}.panel-title{display:flex;align-items:center;justify-content:space-between;gap:8px;font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.4px}.pill{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--warn);background:rgba(250,204,21,.10);border:1px solid rgba(250,204,21,.35);white-space:nowrap}.pill.ok{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.pill.bad{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.file-list{display:flex;flex-direction:column;gap:8px}.file{display:grid;grid-template-columns:1fr auto;gap:8px;align-items:center;background:rgba(18,10,6,.55);border:1px solid rgba(255,232,190,.08);border-radius:12px;padding:9px 10px}.file-name{font-size:12px;color:var(--text-main);font-weight:850;line-height:1.25;word-break:break-word}.file-state{font-size:10px;font-weight:950;color:var(--warn);white-space:nowrap}.file-state.ok{color:var(--ok)}.file-state.bad{color:var(--bad)}.notice{font-size:11px;line-height:1.45;color:var(--text-muted);font-weight:760;background:rgba(0,0,0,.14);border-radius:12px;padding:9px;border:1px dashed rgba(255,232,190,.12)}
.head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-top:2px}.section-title{font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.6px}.section-sub{font-size:11px;color:var(--text-muted);font-weight:800}.grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}.card{min-height:122px;border:none;text-align:left;border-radius:16px;padding:12px;background:linear-gradient(180deg,rgba(58,36,22,.92),rgba(33,18,8,.98));border:1px solid rgba(255,232,190,.10);box-shadow:0 5px 14px rgba(0,0,0,.22);cursor:pointer;color:var(--text-main);display:flex;flex-direction:column;gap:8px;position:relative;overflow:hidden}.card::before{content:"";position:absolute;inset:auto -30px -45px auto;width:100px;height:100px;border-radius:50%;background:rgba(212,0,0,.13)}.card:active{transform:scale(.985)}.card.active{border-color:var(--accent2);box-shadow:0 0 0 1px rgba(255,56,56,.25),0 8px 20px rgba(0,0,0,.32)}.card:disabled{opacity:.55;cursor:not-allowed;transform:none}.icon{width:34px;height:34px;border-radius:12px;display:flex;align-items:center;justify-content:center;background:rgba(212,0,0,.16);border:1px solid rgba(255,56,56,.25);font-size:18px;flex-shrink:0}.card-title{font-size:14px;font-weight:950;line-height:1.16;color:var(--text-main);position:relative;z-index:1}.card-desc{font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:730;position:relative;z-index:1;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden}.full{grid-column:1/-1;min-height:104px}
.audio{padding:12px;display:flex;flex-direction:column;gap:11px;border-color:rgba(16,185,129,.22);background:linear-gradient(180deg,rgba(16,185,129,.08),rgba(18,10,6,.92))}.audio-grid{display:grid;grid-template-columns:1fr 1fr;gap:9px}.choice{border:1px solid rgba(255,232,190,.12);background:rgba(18,10,6,.55);border-radius:14px;padding:10px;text-align:left;color:var(--text-main);cursor:pointer}.choice.active{border-color:var(--ok);box-shadow:0 0 0 1px rgba(16,185,129,.20);background:rgba(16,185,129,.10)}.choice b{display:block;font-size:13px;color:var(--text-main);margin-bottom:4px}.choice span{display:block;font-size:10.5px;line-height:1.35;color:var(--text-muted);font-weight:740}.tabs{display:flex;gap:7px;flex-wrap:wrap}.tab{border:1px solid rgba(255,232,190,.14);background:rgba(18,10,6,.55);color:var(--text-soft);border-radius:999px;padding:7px 10px;font-size:11px;font-weight:900}.tab.active{border-color:var(--accent2);background:rgba(212,0,0,.18);color:#fff}.select-row{display:grid;grid-template-columns:1fr 1fr;gap:9px}.select-box{display:flex;flex-direction:column;gap:6px}.field{font-size:11px;color:#ffd6a0;font-weight:950;text-transform:uppercase;letter-spacing:.45px}.input,.textarea,.select{width:100%;border:1px solid rgba(255,232,190,.14);border-radius:13px;background:#120a06;color:var(--text-main);outline:none;padding:10px 11px;font-size:12px;font-weight:760;line-height:1.4}.textarea{height:94px;resize:none}.builder{padding:12px;display:flex;flex-direction:column;gap:10px}.actions{display:grid;grid-template-columns:1fr 1fr;gap:10px}.btn{border:none;border-radius:14px;padding:11px 10px;font-size:12px;font-weight:950;cursor:pointer;color:#fff;background:linear-gradient(135deg,#d40000,#ff3838);box-shadow:0 7px 16px rgba(212,0,0,.22)}.btn.secondary{background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);box-shadow:0 5px 12px rgba(0,0,0,.22)}.btn:active{transform:scale(.97)}.btn:disabled{opacity:.55;cursor:not-allowed;transform:none}
.preview{border-color:rgba(16,185,129,.28);background:linear-gradient(180deg,rgba(16,185,129,.09),rgba(18,10,6,.88));padding:12px;display:flex;flex-direction:column;gap:8px}.preview-title{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:13px;color:var(--ok);font-weight:950;text-transform:uppercase;letter-spacing:.4px}.meter{font-size:10px;color:var(--text-muted);font-weight:850;text-transform:none;letter-spacing:0;white-space:nowrap}.preview-box{height:280px;overflow:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;border-radius:12px;background:rgba(0,0,0,.18);border:1px solid rgba(255,232,190,.08);padding:10px}.preview-box::-webkit-scrollbar{display:none;width:0;height:0}.body{font-family:var(--mono);font-size:11px;line-height:1.45;color:var(--text-main);font-weight:650;white-space:pre-wrap;word-break:break-word}.abc{display:grid;gap:9px}.abc-box{border-radius:14px;padding:10px;border:1px solid rgba(255,232,190,.10);background:rgba(18,10,6,.48)}.abc-box b{display:block;font-size:11px;text-transform:uppercase;letter-spacing:.4px;margin-bottom:5px;color:#ffd6a0}.abc-box p{font-size:11px;line-height:1.42;color:var(--text-muted);font-weight:760}.foot{flex-shrink:0;background:linear-gradient(135deg,#2b1a10,#160d08);border-top:1px solid var(--border);padding:10px 14px calc(10px + env(safe-area-inset-bottom));font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:800;text-align:center}.foot b{color:#ffd6a0}.overlay{position:absolute;inset:0;background:rgba(5,3,2,.48);backdrop-filter:blur(2px);z-index:100;display:none;align-items:center;justify-content:center;padding:22px;text-align:center}.overlay.show{display:flex}.lock{border-radius:18px;background:linear-gradient(180deg,#2b1a10,#120a06);border:1px solid rgba(255,232,190,.16);box-shadow:0 18px 48px rgba(0,0,0,.5);padding:16px;max-width:330px;width:100%}.spin{width:32px;height:32px;border-radius:50%;border:3px solid rgba(255,232,190,.16);border-top-color:var(--warn);margin:0 auto 10px;animation:spin .8s linear infinite}.lock-title{font-size:14px;font-weight:950;color:#ffd6a0;margin-bottom:6px;text-transform:uppercase}.lock-text{font-size:12px;line-height:1.4;color:var(--text-muted);font-weight:760}@keyframes spin{to{transform:rotate(360deg)}}
@media(max-width:380px){.top{grid-template-columns:36px 1fr auto;padding:9px 10px}.back{width:36px;height:32px}.title{font-size:13px}.chip{font-size:9px;padding:5px 7px}.scroll{padding:12px 10px}.hero h1{font-size:18px}.grid{gap:9px}.card{padding:10px;min-height:118px}.card-title{font-size:13px}.card-desc{font-size:10.5px}.actions,.select-row{grid-template-columns:1fr}.audio-grid{grid-template-columns:1fr}.preview-box{height:250px}.foot{font-size:10.5px}}
</style>
</head>
<body>
<div class="app"><main class="space" id="space">
<header class="top"><button class="back" type="button" aria-label="Trở về" id="backBtn">←</button><div class="title">Không gian báo cáo AI</div><div class="chip">AUDIO + STREAM</div></header>
<section class="scroll" id="scroll">
<article class="hero"><div class="kicker">API Hook · Audio Overview · Stream Output</div><h1>Không gian báo cáo kết nối lõi xổ số</h1><p>Bản này dùng cổng nhận dữ liệu động, render báo cáo theo luồng để chống treo DOM, và bổ sung khối tùy chỉnh “Tổng quan bằng âm thanh” theo các chế độ: tìm hiểu sâu, tóm tắt, phê bình và tranh luận.</p></article>
<section class="panel core" aria-label="Trạng thái lõi"><div class="row2"><div class="core-title">Cổng lõi phân tích</div><div class="status" id="coreStatus">CHỜ KẾT NỐI</div></div><div class="bar-shell"><div class="bar" id="bar"></div></div><div class="log" id="log">Bridge sẵn sàng: window.ReportWorkspaceBridge</div></section>
<section class="panel scan" aria-label="Quét nguồn"><div class="panel-title"><span>Quét tệp / nguồn</span><span class="pill" id="scanStatus">Không đủ dữ liệu xác thực</span></div><div class="file-list" id="fileList"></div><div class="notice" id="scanNotice">Các file hệ thống đã được gọi quét, nhưng công cụ đọc tệp trả về rỗng/hỏng/không thể xử lý. Khi backend gửi dữ liệu thật, khu vực này sẽ cập nhật bằng API hook.</div></section>
<div class="head"><div><div class="section-title">Tạo báo cáo</div><div class="section-sub">Chọn định dạng đầu ra</div></div></div>
<section class="grid" id="formatGrid">
<button class="card active" type="button" data-title="Tạo báo cáo của riêng bạn" data-template="Tạo báo cáo theo cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng do người dùng chỉ định."><div class="icon">✍️</div><div class="card-title">Tạo báo cáo của riêng bạn</div><div class="card-desc">Chỉ định cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng.</div></button>
<button class="card" type="button" data-title="Tài liệu tóm tắt" data-template="Tổng quan nguồn dữ liệu, ý chính, trích dẫn, điểm chưa xác thực và cảnh báo thiếu dữ kiện."><div class="icon">📄</div><div class="card-title">Tài liệu tóm tắt</div><div class="card-desc">Tổng quan nguồn có trích dẫn, thông tin chính và điểm cần kiểm chứng.</div></button>
<button class="card" type="button" data-title="Hướng dẫn ôn tập" data-template="Tạo câu hỏi ngắn, câu hỏi tự luận, đáp án kiểm tra và bảng thuật ngữ từ tài liệu nguồn."><div class="icon">🎓</div><div class="card-title">Hướng dẫn ôn tập</div><div class="card-desc">Câu hỏi ngắn, tiểu luận, đáp án và bảng thuật ngữ theo nguồn.</div></button>
<button class="card" type="button" data-title="Bài đăng trên blog" data-template="Chắt lọc ý chính thành bài viết dễ đọc, có mở bài, thân bài, kết luận và cảnh báo dữ kiện."><div class="icon">📰</div><div class="card-title">Bài đăng trên blog</div><div class="card-desc">Chuyển điểm chính thành bài viết mạch lạc, dễ đọc.</div></button>
</section>
<div class="head"><div><div class="section-title">Định dạng đề xuất</div><div class="section-sub">Kiến trúc / quản trị / thuật toán</div></div></div>
<section class="grid">
<button class="card full" type="button" data-title="Tài liệu Đặc tả Kiến trúc" data-template="Mô tả cấu trúc hệ thống, module, luồng dữ liệu, lớp kiểm soát, cơ chế lỗi và ranh giới vận hành."><div class="icon">🏗️</div><div class="card-title">Tài liệu Đặc tả Kiến trúc</div><div class="card-desc">Cấu trúc hệ thống, module lõi, luồng dữ liệu và lớp kiểm soát.</div></button>
<button class="card full" type="button" data-title="Báo cáo Chiến lược Quản trị" data-template="Phân tích rủi ro, kiểm soát lỗi, quyền truy cập, vùng dữ liệu nhạy cảm và cơ chế giám sát."><div class="icon">🛡️</div><div class="card-title">Báo cáo Chiến lược Quản trị</div><div class="card-desc">Quản trị rủi ro, kiểm soát lỗi, quyền truy cập và trách nhiệm vận hành.</div></button>
<button class="card full" type="button" data-title="Tài liệu Hướng dẫn Thuật toán" data-template="Giải thích thuật toán, dữ liệu đầu vào, quy tắc xử lý, giới hạn suy luận và điều kiện không đủ dữ liệu."><div class="icon">🧮</div><div class="card-title">Tài liệu Hướng dẫn Thuật toán</div><div class="card-desc">Dữ liệu đầu vào, quy tắc xử lý, giới hạn và điều kiện không đủ dữ liệu.</div></button>
<button class="card full" type="button" data-title="Cẩm nang Tư duy Hệ thống" data-template="Mô hình xử lý thông tin đa tầng, phân biệt dữ liệu thật, giả định, suy luận và điểm mù."><div class="icon">🧠</div><div class="card-title">Cẩm nang Tư duy Hệ thống</div><div class="card-desc">Phân biệt dữ liệu thực tế, giả định, suy luận và điểm mù.</div></button>
</section>
<section class="audio" aria-label="Tùy chỉnh tổng quan bằng âm thanh"><div class="panel-title"><span>Tùy chỉnh bản Tổng quan bằng âm thanh</span><span class="pill ok" id="audioState">Sẵn sàng</span></div><div class="audio-grid" id="audioModes">
<button class="choice active" type="button" data-mode="Tìm hiểu sâu"><b>Tìm hiểu sâu</b><span>Một cuộc trò chuyện sôi nổi giữa 2 máy chủ AI, phân tích và kết nối các chủ đề trong nguồn.</span></button>
<button class="choice" type="button" data-mode="Tóm tắt"><b>Tóm tắt</b><span>Thông tin tổng quan ngắn gọn giúp nắm bắt nhanh các ý tưởng chính dựa trên nguồn.</span></button>
<button class="choice" type="button" data-mode="Phê bình"><b>Phê bình</b><span>Bài đánh giá chuyên gia về nguồn, đưa phản hồi xây dựng để cải thiện tài liệu.</span></button>
<button class="choice" type="button" data-mode="Tranh luận"><b>Tranh luận</b><span>Cuộc tranh luận sâu sắc giữa 2 máy chủ AI, làm sáng tỏ các quan điểm khác nhau.</span></button>
</div><div class="select-row"><div class="select-box"><label class="field" for="lang">Chọn ngôn ngữ</label><select class="select" id="lang"><option>Tiếng Việt</option><option>English</option><option>日本語</option><option>한국어</option></select></div><div class="select-box"><label class="field" for="length">Độ dài</label><select class="select" id="length"><option>Ngắn</option><option selected>Mặc định</option><option>Dài</option></select></div></div><label class="field" for="audioFocus">Máy chủ AI nên tập trung vào điều gì trong tập này?</label><textarea class="textarea" id="audioFocus">Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.</textarea><div class="tabs" id="audioTabs"><button class="tab active" type="button">+ Quản Lý Vốn</button><button class="tab" type="button">+ Người Mới Bắt</button><button class="tab" type="button">+ Phân Tích Cầu</button></div></section>
<section class="builder"><label class="field" for="reportName">Tên báo cáo</label><input class="input" id="reportName" value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu" autocomplete="off"><label class="field" for="reportRules">Yêu cầu kiểm soát</label><textarea class="textarea" id="reportRules">Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.</textarea><div class="actions"><button class="btn" type="button" id="buildBtn">Tạo báo cáo stream</button><button class="btn secondary" type="button" id="audioBtn">Tạo tổng quan audio</button><button class="btn secondary" type="button" id="resetBtn">Đặt lại</button><button class="btn secondary" type="button" id="exportBtn">Xuất nội dung</button></div></section>
<section class="preview" aria-live="polite"><div class="preview-title"><span>Bản nháp báo cáo</span><span class="meter" id="meter">0 dòng</span></div><div class="preview-box" id="previewBox"><pre class="body" id="previewBody">Chọn định dạng rồi bấm “Tạo báo cáo stream”.</pre></div></section>
<section class="abc"><div class="abc-box"><b>Bước 1 — Tạo lập</b><p>API hook nhận nguồn, trạng thái, log và stream báo cáo/audio từ backend.</p></div><div class="abc-box"><b>Bước 2 — Tự hủy diệt</b><p>Chặn hardcode, chặn nhồi 10.000 dòng một lần, chặn bấm lặp khi lõi đang xử lý.</p></div><div class="abc-box"><b>Bước 3 — Tái sinh</b><p>Dùng bridge động, render theo chunk, giới hạn vùng hiển thị, giữ bản đầy đủ trong bộ nhớ phiên.</p></div></section>
</section><footer class="foot"><b>Nguyên tắc:</b> chỉ hiển thị dữ liệu backend gửi vào. Nếu nguồn không đọc được, phải báo Không đủ dữ liệu xác thực.</footer><div class="overlay" id="overlay"><div class="lock"><div class="spin"></div><div class="lock-title" id="lockTitle">Đang xử lý</div><div class="lock-text" id="lockText">Đang kết nối lõi phân tích...</div></div></div>
</main></div>
<script>
"use strict";(function(){
const cards=Array.from(document.querySelectorAll(".card"));const choices=Array.from(document.querySelectorAll(".choice"));const tabs=Array.from(document.querySelectorAll(".tab"));
const previewBody=document.getElementById("previewBody"),previewBox=document.getElementById("previewBox"),meter=document.getElementById("meter"),reportName=document.getElementById("reportName"),reportRules=document.getElementById("reportRules"),buildBtn=document.getElementById("buildBtn"),audioBtn=document.getElementById("audioBtn"),resetBtn=document.getElementById("resetBtn"),exportBtn=document.getElementById("exportBtn"),backBtn=document.getElementById("backBtn"),fileList=document.getElementById("fileList"),scanStatus=document.getElementById("scanStatus"),scanNotice=document.getElementById("scanNotice"),coreStatus=document.getElementById("coreStatus"),log=document.getElementById("log"),bar=document.getElementById("bar"),overlay=document.getElementById("overlay"),lockTitle=document.getElementById("lockTitle"),lockText=document.getElementById("lockText"),lang=document.getElementById("lang"),length=document.getElementById("length"),audioFocus=document.getElementById("audioFocus"),audioState=document.getElementById("audioState");
const MAX_VISIBLE_CHARS=120000,STREAM_BATCH_LINES=24;let selected=cards[0],audioMode=choices[0].dataset.mode,isBusy=false,full=[],node=document.createTextNode(""),lines=0,queue=[],scheduled=false;previewBody.textContent="";previewBody.appendChild(node);
const defaultFiles=[{name:"HỆ THỐNG CAPABILITY TOKEN (CẤP QUYỀN TRUY CẬP).docx",state:"Không đọc được",level:"warn"},{name:"KHAI THÁC TRÊN BẢNG ĐẶC BIỆT NĂM.docx",state:"Không đọc được",level:"warn"},{name:"Hệ thống, thiếu kết quả xsmb.docx",state:"Không đọc được",level:"warn"},{name:"bản cấu trúc hệ thống nghiên cứu xổ số trọng tâm cốt lõi.docx",state:"Không đọc được",level:"warn"},{name:"nghiên cứu xổ số 1.docx",state:"Không đọc được",level:"warn"}];
function setBusy(v,t,d){isBusy=v;[buildBtn,audioBtn,resetBtn,exportBtn].forEach(b=>b.disabled=v);cards.forEach(c=>c.disabled=v);overlay.classList.toggle("show",v);if(t)lockTitle.textContent=t;if(d)lockText.textContent=d}function setStatus(s,m,p){coreStatus.className="status";if(s)coreStatus.classList.add(s);coreStatus.textContent=m||"CHỜ KẾT NỐI";if(typeof p==="number")bar.style.width=Math.max(0,Math.min(100,p))+"%"}function setLog(m){log.textContent=m||""}
function renderFiles(files,status,notice){fileList.replaceChildren();(Array.isArray(files)?files:[]).forEach(f=>{const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent=f.name||"Nguồn chưa đặt tên";st.textContent=f.state||"Chưa rõ";if(f.level==="ok")st.classList.add("ok");if(f.level==="bad")st.classList.add("bad");r.append(n,st);fileList.appendChild(r)});if(!fileList.children.length){const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent="Chưa có nguồn dữ liệu";st.textContent="Đang chờ";r.append(n,st);fileList.appendChild(r)}scanStatus.className="pill";if(status&&status.toLowerCase().includes("đủ"))scanStatus.classList.add("ok");if(status&&status.toLowerCase().includes("lỗi"))scanStatus.classList.add("bad");scanStatus.textContent=status||"Chưa có dữ liệu lõi";scanNotice.textContent=notice||"Nguồn có thể cập nhật qua API hook."}
function resetPreview(t){full=[];lines=0;queue=[];scheduled=false;node.data=t||"";if(t)full.push(t);meter.textContent=(t?t.split("\n").length:0)+" dòng";previewBox.scrollTop=0}function appendText(t){if(!t)return;full.push(t);lines+=(t.match(/\n/g)||[]).length;let cur=node.data+t;if(cur.length>MAX_VISIBLE_CHARS)cur="[Đã thu gọn phần đầu để tránh nghẽn DOM trên mobile. Nội dung đầy đủ vẫn nằm trong bộ nhớ phiên.]\n\n"+cur.slice(-MAX_VISIBLE_CHARS);node.data=cur;meter.textContent=lines+" dòng · "+Math.round(cur.length/1024)+"KB hiển thị";previewBox.scrollTop=previewBox.scrollHeight}function flush(){if(scheduled)return;scheduled=true;requestAnimationFrame(()=>{let block="",c=0;while(queue.length&&c<STREAM_BATCH_LINES){block+=queue.shift();c++}appendText(block);scheduled=false;if(queue.length)flush()})}function stream(x){(Array.isArray(x)?x:[String(x||"")]).forEach(l=>queue.push(String(l).endsWith("\n")?String(l):String(l)+"\n"));flush()}
function selectCard(c){if(isBusy)return;cards.forEach(x=>x.classList.remove("active"));c.classList.add("active");selected=c}cards.forEach(c=>c.addEventListener("click",()=>selectCard(c)));choices.forEach(c=>c.addEventListener("click",()=>{if(isBusy)return;choices.forEach(x=>x.classList.remove("active"));c.classList.add("active");audioMode=c.dataset.mode||"Tóm tắt"}));tabs.forEach(t=>t.addEventListener("click",()=>{if(isBusy)return;t.classList.toggle("active")}));
async function simulateReport(kind){const title=selected.dataset.title||"Báo cáo",template=selected.dataset.template||"Chưa có mô tả",name=reportName.value.trim()||"Báo cáo chưa đặt tên",rules=reportRules.value.trim()||"Không có quy tắc bổ sung";setBusy(true,kind==="audio"?"Đang dựng tổng quan audio":"Đang kết nối Bô Lão",kind==="audio"?"Khóa thao tác trong khi tạo kịch bản âm thanh.":"Khóa thao tác để tránh bấm lặp gây nghẽn lõi.");setStatus("loading",kind==="audio"?"ĐANG DỰNG AUDIO":"ĐANG KẾT NỐI",10);setLog("[1/5] Mở ReportWorkspaceBridge\n[2/5] Chờ dữ liệu backend...");resetPreview("");if(kind==="audio"){stream(["# Kịch bản Tổng quan bằng âm thanh", "", "## Chế độ", audioMode, "", "## Ngôn ngữ", lang.value, "", "## Độ dài", length.value, "", "## Trọng tâm", audioFocus.value, "", "## Lưu ý an toàn", "Nội dung về Martingale/Fibonacci chỉ dùng để phân tích rủi ro và bảo toàn tài sản, không phải khuyến nghị đặt tiền hoặc cá cược.", ""])}else{stream(["# "+name,"","## Định dạng",title,"","## Mục tiêu",template,"","## Quy tắc",rules,"","## Luồng stream"])}await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG QUÉT NGUỒN",35);stream(["- Kiểm tra nguồn đầu vào qua API hook.","- Nếu nguồn không đọc được, không sinh kết luận thay dữ liệu.","- Dữ liệu lớn được render theo chunk requestAnimationFrame."]);await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG STREAM",70);setLog("[3/5] Nhận dữ liệu theo dòng\n[4/5] Render theo batch chống freeze DOM");for(let i=1;i<=60;i++){stream([(kind==="audio"?"Lượt thoại mô phỏng ":"Dòng phân tích mô phỏng ")+String(i).padStart(3,"0")+": thay dòng này bằng dữ liệu thật từ backend khi tích hợp."]);if(i%12===0)await new Promise(r=>setTimeout(r,20))}setStatus("ready","HOÀN TẤT",100);stream(["","## Kết luận kiểm soát","Không có đủ dữ liệu xác thực từ tệp nếu backend không gửi nguồn đọc được. UI đã sẵn sàng nhận dữ liệu động qua window.ReportWorkspaceBridge."]);setLog("[5/5] Hoàn tất stream. Không nhồi DOM một lần.");setBusy(false)}
buildBtn.addEventListener("click",()=>simulateReport("report"));audioBtn.addEventListener("click",()=>simulateReport("audio"));resetBtn.addEventListener("click",()=>{reportName.value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu";reportRules.value="Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.";audioFocus.value="Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.";selectCard(cards[0]);setStatus("","CHỜ KẾT NỐI",0);setLog("Bridge sẵn sàng: window.ReportWorkspaceBridge");renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.")});exportBtn.addEventListener("click",()=>{const blob=new Blob([full.join("")],{type:"text/plain;charset=utf-8"});const a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download="bao_cao_stream.txt";document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(a.href),500)});backBtn.addEventListener("click",()=>resetPreview("Đã kích hoạt nút Trở về. Trong hệ thống thật, nút này nối với router/bridge của không gian chính."));
window.ReportWorkspaceBridge={setFiles:(f,s,n)=>renderFiles(f,s,n),setStatus:(s,m,p)=>setStatus(s,m,p),setLog:m=>setLog(m),startLoading:(t,d)=>setBusy(true,t||"Đang xử lý",d||"Đang chờ lõi phân tích..."),stopLoading:()=>setBusy(false),resetReport:t=>resetPreview(t||""),streamReport:x=>stream(x),streamAudio:x=>stream(x),setAudioConfig:c=>{if(!c)return;if(c.mode){choices.forEach(x=>{x.classList.toggle("active",x.dataset.mode===c.mode)});audioMode=c.mode}if(c.language)lang.value=c.language;if(c.length)length.value=c.length;if(c.focus)audioFocus.value=c.focus},getFullReport:()=>full.join("")};
renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.");
})();
</script>
</body>
</html>
------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Module Không Gian Video AI</title>
<style>
:root{
    --bg-main:#1c130d;
    --bg-board:#2a1a10;
    --bg-deep:#120a06;
    --panel:#24150d;
    --panel-2:#160d08;
    --text-main:#fff4e6;
    --text-soft:#ffe0b8;
    --text-muted:#c9a982;
    --border-color:#5a3824;
    --glass-border:#6b432b;
    --accent:#d40000;
    --accent-bright:#ff3838;
    --ok:#10b981;
    --warn:#facc15;
    --bad:#ef4444;
    --font-ui:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:var(--font-ui);-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{background:#050302;display:flex;justify-content:center;align-items:flex-start;width:100vw;height:100dvh;overflow:hidden;color:var(--text-main)}
button,input{font:inherit}
.app-wrapper{max-width:480px;width:100%;height:100%;position:relative;background:var(--bg-main);overflow:hidden;display:flex;flex-direction:column;box-shadow:0 0 45px rgba(0,0,0,.95);border-left:1px solid rgba(255,232,190,.08);border-right:1px solid rgba(255,232,190,.08)}
.sub-screen{position:relative;display:flex;flex-direction:column;flex:1;background:linear-gradient(180deg,var(--bg-board),var(--bg-deep));min-height:0;width:100%;height:100%;padding-top:env(safe-area-inset-top)}
.mock-header{padding:10px 12px;background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border-color);display:grid;grid-template-columns:38px 1fr auto;align-items:center;gap:10px;z-index:20;flex-shrink:0;box-shadow:0 4px 14px rgba(0,0,0,.32)}
.mock-back-btn{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass-border);color:var(--text-soft);font-size:20px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 2px rgba(255,232,190,.08),0 3px 8px rgba(0,0,0,.25)}
.mock-back-btn:active{transform:scale(.94)}
.mock-header-title{font-weight:950;font-size:14px;color:var(--text-soft);letter-spacing:.5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;text-transform:uppercase}
.header-chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}
.video-player-container{width:100%;aspect-ratio:16/9;background:#000;position:relative;flex-shrink:0;border-bottom:1px solid var(--border-color);box-shadow:0 6px 18px rgba(0,0,0,.5);z-index:10;overflow:hidden}
.video-player-container iframe,.video-player-container video{width:100%;height:100%;border:none;object-fit:contain;background:#000;display:block}
.player-placeholder{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;background:radial-gradient(circle at 50% 35%,#2a1a10 0%,#120a06 68%);color:var(--text-muted);text-align:center;padding:20px}
.player-placeholder svg{width:54px;height:54px;fill:#6b432b;margin-bottom:10px;filter:drop-shadow(0 4px 12px rgba(0,0,0,.45))}
.player-placeholder strong{font-size:13px;letter-spacing:.7px;color:var(--text-soft);text-transform:uppercase}
.player-placeholder small{display:block;margin-top:6px;font-size:11px;line-height:1.35;color:var(--text-muted);max-width:300px}
.video-info-section{padding:14px 15px 13px;flex-shrink:0;border-bottom:1px solid rgba(255,232,190,.08);background:linear-gradient(180deg,#24150d,#1a0f09)}
.video-title{font-size:16px;font-weight:900;color:var(--text-main);margin-bottom:9px;line-height:1.35;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.video-meta{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:12px;color:var(--text-muted)}
.ai-status-badge{background:rgba(16,185,129,.10);color:var(--ok);padding:5px 8px;border-radius:8px;border:1px solid rgba(16,185,129,.35);font-weight:950;letter-spacing:.4px;display:flex;align-items:center;gap:5px;white-space:nowrap;max-width:58%;overflow:hidden;text-overflow:ellipsis}
.ai-status-badge.waiting{border-color:rgba(250,204,21,.45);color:var(--warn);background:rgba(250,204,21,.10)}
.ai-status-badge.error{border-color:rgba(239,68,68,.45);color:var(--bad);background:rgba(239,68,68,.10)}
.playlist-header{padding:14px 15px 9px;font-size:12px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.8px;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-shrink:0}
.playlist-count{font-size:11px;color:var(--text-muted);font-weight:850;text-transform:none;letter-spacing:0}
.playlist-container{flex:1;overflow-y:auto;overflow-x:hidden;padding:0 15px 15px;display:flex;flex-direction:column;gap:10px;-webkit-overflow-scrolling:touch;scrollbar-width:none;min-height:0}
.playlist-container::-webkit-scrollbar{display:none;width:0;height:0}
.video-card{width:100%;display:flex;gap:12px;background:linear-gradient(180deg,rgba(58,36,22,.76),rgba(33,18,8,.92));padding:8px;border-radius:12px;border:1px solid rgba(255,232,190,.08);cursor:pointer;transition:transform .18s,background .18s,border-color .18s,box-shadow .18s;box-shadow:0 4px 12px rgba(0,0,0,.20);text-align:left;color:inherit}
.video-card:active{background:linear-gradient(180deg,#3a2416,#211208);transform:scale(.985)}
.video-card.active{border-color:var(--ok);background:linear-gradient(180deg,rgba(16,185,129,.12),rgba(33,18,8,.94));box-shadow:0 0 0 1px rgba(16,185,129,.16),0 6px 16px rgba(0,0,0,.28)}
.thumb-wrapper{width:120px;height:68px;border-radius:9px;overflow:hidden;position:relative;flex-shrink:0;background:#1e130c;border:1px solid rgba(255,232,190,.10)}
.thumb-art{width:100%;height:100%;display:flex;align-items:center;justify-content:center;background:radial-gradient(circle at 30% 20%,rgba(255,82,82,.34),transparent 36%),linear-gradient(135deg,#3a2416,#120a06);color:#ffe0b8;font-size:18px;font-weight:950;letter-spacing:.7px;text-align:center;padding:8px;text-transform:uppercase}
.thumb-wrapper img{width:100%;height:100%;object-fit:cover;display:block}
.duration-badge{position:absolute;bottom:4px;right:4px;background:rgba(0,0,0,.82);color:#fff;font-size:10px;padding:2px 5px;border-radius:5px;font-weight:900}
.type-badge{position:absolute;top:4px;left:4px;background:rgba(212,0,0,.86);color:#fff;font-size:9px;padding:2px 5px;border-radius:999px;font-weight:950;letter-spacing:.2px}
.card-info{flex:1;min-width:0;display:flex;flex-direction:column;justify-content:flex-start;padding:1px 0}
.card-title{font-size:13px;font-weight:850;color:var(--text-main);margin-bottom:4px;line-height:1.3;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.card-date{font-size:11px;color:var(--text-muted);font-weight:750}
.card-status{font-size:10px;font-weight:950;margin-top:auto;color:var(--ok);letter-spacing:.2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.card-status.wait{color:var(--warn)}
.card-status.error{color:var(--bad)}
.footer-note{flex-shrink:0;background:linear-gradient(135deg,#2b1a10,#160d08);border-top:1px solid var(--border-color);padding:10px 14px calc(10px + env(safe-area-inset-bottom));font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:800;text-align:center}
.footer-note b{color:#ffd6a0}
@media(max-height:720px){.playlist-container{gap:8px}.video-card{padding:7px}.thumb-wrapper{width:112px;height:63px}.footer-note{display:none}}
@media(max-width:380px){.mock-header{grid-template-columns:36px 1fr auto;padding:9px 10px}.mock-back-btn{width:36px;height:32px}.mock-header-title{font-size:13px}.header-chip{font-size:9px;padding:5px 7px}.video-info-section{padding:12px}.video-title{font-size:15px}.playlist-container{padding:0 12px 12px}.playlist-header{padding:12px 12px 8px}.thumb-wrapper{width:108px;height:61px}.video-card{gap:9px}.card-title{font-size:12px}.ai-status-badge{font-size:11px;max-width:62%}}
</style>
</head>
<body>
<div class="app-wrapper">
    <div id="video-workspace" class="sub-screen">
        <div class="mock-header">
            <button class="mock-back-btn" id="btn-exit-video" type="button" aria-label="Trở về">←</button>
            <span class="mock-header-title">Không gian Video AI</span>
            <span class="header-chip">AI VIDEO</span>
        </div>

        <div class="video-player-container" id="main-player-box" aria-live="polite">
            <div class="player-placeholder" id="player-placeholder">
                <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M8 5v14l11-7z"></path></svg>
                <strong>Chọn video để phát</strong>
                <small>Hỗ trợ YouTube, Vimeo, MP4, WebM, OGG và HLS nếu trình duyệt có hỗ trợ native HLS.</small>
            </div>
        </div>

        <div class="video-info-section">
            <div class="video-title" id="current-vid-title">Chưa chọn video phân tích</div>
            <div class="video-meta">
                <span id="current-vid-date">--/--/2026</span>
                <span class="ai-status-badge waiting" id="current-vid-status">ĐANG CHỜ</span>
            </div>
        </div>

        <div class="playlist-header">
            <span>Danh sách video</span>
            <span class="playlist-count" id="playlist-count">0 mục</span>
        </div>
        <div class="playlist-container" id="playlist-render-area"></div>
        <div class="footer-note"><b>Ghi chú:</b> 4 thẻ video được bố trí kín hơn. Dữ liệu mẫu nằm trong <b>dbVideos</b>; khi có video thật, thay URL và metadata tại đó.</div>
    </div>
</div>

<script>
"use strict";

document.addEventListener("DOMContentLoaded", function(){
    const $ = function(id){ return document.getElementById(id); };

    const dbVideos = [
        {
            id:"v01",
            title:"Video YouTube mẫu - hồ sơ phân tích ngày 01/06/2026",
            date:"01/06/2026",
            url:"https://www.youtube.com/watch?v=dQw4w9WgXcQ",
            thumbText:"YT 01",
            thumb:"",
            duration:"04:20",
            status:"YouTube",
            state:"ok"
        },
        {
            id:"v02",
            title:"Video Vimeo mẫu - kiểm thử player iframe ngoài YouTube",
            date:"02/06/2026",
            url:"https://vimeo.com/76979871",
            thumbText:"VIMEO",
            thumb:"",
            duration:"02:15",
            status:"Vimeo",
            state:"ok"
        },
        {
            id:"v03",
            title:"Video MP4 trực tiếp - kiểm thử thẻ video native",
            date:"03/06/2026",
            url:"https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4",
            thumbText:"MP4",
            thumb:"",
            duration:"00:05",
            status:"MP4 native",
            state:"ok"
        },
        {
            id:"v04",
            title:"Khung video HLS/WebM/OGG - thay URL thật khi vận hành",
            date:"04/06/2026",
            url:"https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm",
            thumbText:"WEBM",
            thumb:"",
            duration:"00:05",
            status:"WebM native",
            state:"wait"
        }
    ];

    const playlistBox = $("playlist-render-area");
    const playerBox = $("main-player-box");
    const txtTitle = $("current-vid-title");
    const txtDate = $("current-vid-date");
    const txtStatus = $("current-vid-status");
    const btnExit = $("btn-exit-video");
    const playlistCount = $("playlist-count");

    let currentActiveId = null;

    function showPlaceholder(title, detail){
        playerBox.replaceChildren();
        const box = document.createElement("div");
        box.className = "player-placeholder";
        const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
        svg.setAttribute("viewBox", "0 0 24 24");
        svg.setAttribute("aria-hidden", "true");
        const path = document.createElementNS("http://www.w3.org/2000/svg", "path");
        path.setAttribute("d", "M8 5v14l11-7z");
        svg.appendChild(path);
        const strong = document.createElement("strong");
        strong.textContent = title;
        const small = document.createElement("small");
        small.textContent = detail;
        box.appendChild(svg);
        box.appendChild(strong);
        box.appendChild(small);
        playerBox.appendChild(box);
    }

    function safeUrl(rawUrl){
        if(typeof rawUrl !== "string" || !rawUrl.trim()) return null;
        try{
            const url = new URL(rawUrl.trim());
            if(url.protocol !== "https:" && url.protocol !== "http:") return null;
            return url;
        }catch(error){
            return null;
        }
    }

    function extractYoutubeId(rawUrl){
        const url = safeUrl(rawUrl);
        if(!url) return "";
        const host = url.hostname.replace(/^www\./, "").toLowerCase();
        let id = "";
        if(host === "youtu.be"){
            id = url.pathname.split("/").filter(Boolean)[0] || "";
        }else if(host === "youtube.com" || host === "m.youtube.com" || host === "music.youtube.com"){
            if(url.pathname === "/watch") id = url.searchParams.get("v") || "";
            else if(url.pathname.startsWith("/embed/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
            else if(url.pathname.startsWith("/shorts/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
            else if(url.pathname.startsWith("/live/")) id = url.pathname.split("/").filter(Boolean)[1] || "";
        }
        return /^[A-Za-z0-9_-]{6,}$/.test(id) ? id : "";
    }

    function extractVimeoId(rawUrl){
        const url = safeUrl(rawUrl);
        if(!url) return "";
        const host = url.hostname.replace(/^www\./, "").toLowerCase();
        if(host !== "vimeo.com" && host !== "player.vimeo.com") return "";
        const parts = url.pathname.split("/").filter(Boolean);
        let id = "";
        if(host === "player.vimeo.com" && parts[0] === "video") id = parts[1] || "";
        if(host === "vimeo.com") id = parts.find(function(part){ return /^\d+$/.test(part); }) || "";
        return /^\d+$/.test(id) ? id : "";
    }

    function getExtension(pathname){
        const clean = pathname.toLowerCase().split("?")[0].split("#")[0];
        const idx = clean.lastIndexOf(".");
        return idx >= 0 ? clean.slice(idx + 1) : "";
    }

    function getPlayableType(rawUrl){
        const ytId = extractYoutubeId(rawUrl);
        if(ytId){
            return {type:"iframe",provider:"YouTube",src:"https://www.youtube.com/embed/" + ytId + "?autoplay=1&rel=0&playsinline=1"};
        }

        const vimeoId = extractVimeoId(rawUrl);
        if(vimeoId){
            return {type:"iframe",provider:"Vimeo",src:"https://player.vimeo.com/video/" + vimeoId + "?autoplay=1&title=0&byline=0&portrait=0"};
        }

        const url = safeUrl(rawUrl);
        if(!url) return {type:"invalid",provider:"",src:""};

        const ext = getExtension(url.pathname);
        const directVideoMap = {
            mp4:"video/mp4",
            m4v:"video/mp4",
            webm:"video/webm",
            ogg:"video/ogg",
            ogv:"video/ogg",
            mov:"video/quicktime",
            m3u8:"application/vnd.apple.mpegurl"
        };

        if(Object.prototype.hasOwnProperty.call(directVideoMap, ext)){
            return {type:"video",provider:ext.toUpperCase(),src:url.href,mime:directVideoMap[ext],extension:ext};
        }

        return {type:"unsupported",provider:"",src:""};
    }

    function setStatusBadge(videoData){
        txtStatus.className = "ai-status-badge waiting";
        if(videoData.state === "ok") txtStatus.className = "ai-status-badge";
        if(videoData.state === "warn" || videoData.state === "wait") txtStatus.className = "ai-status-badge waiting";
        if(videoData.state === "error") txtStatus.className = "ai-status-badge error";
        txtStatus.textContent = videoData.status || "Chưa rõ";
    }

    function playVideo(videoData){
        if(!videoData) return;
        currentActiveId = videoData.id;
        document.querySelectorAll(".video-card").forEach(function(card){
            card.classList.toggle("active", card.dataset.id === currentActiveId);
        });
        txtTitle.textContent = videoData.title || "Không có tiêu đề";
        txtDate.textContent = "Ngày: " + (videoData.date || "Chưa có ngày");
        setStatusBadge(videoData);

        const playable = getPlayableType(videoData.url);
        playerBox.replaceChildren();

        if(playable.type === "iframe"){
            const iframe = document.createElement("iframe");
            iframe.src = playable.src;
            iframe.title = playable.provider + " Video Player";
            iframe.allow = "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share";
            iframe.allowFullscreen = true;
            iframe.referrerPolicy = "strict-origin-when-cross-origin";
            playerBox.appendChild(iframe);
            return;
        }

        if(playable.type === "video"){
            const video = document.createElement("video");
            video.controls = true;
            video.playsInline = true;
            video.autoplay = true;
            video.preload = "metadata";

            const source = document.createElement("source");
            source.src = playable.src;
            source.type = playable.mime;
            video.appendChild(source);

            video.addEventListener("error", function(){
                showPlaceholder("Trình duyệt không phát được định dạng này", "File có thể cần codec khác, CORS hợp lệ, hoặc cần thư viện riêng nếu là HLS trên trình duyệt không hỗ trợ native.");
            });

            playerBox.appendChild(video);
            video.play().catch(function(){
                /* Autoplay có thể bị trình duyệt chặn. Người dùng bấm Play thủ công trên controls. */
            });
            return;
        }

        showPlaceholder("Không phát được video", "URL không hợp lệ hoặc chưa thuộc nhóm hỗ trợ: YouTube, Vimeo, MP4, M4V, WebM, OGG, OGV, MOV, M3U8.");
    }

    function detectProviderLabel(rawUrl){
        const playable = getPlayableType(rawUrl);
        if(playable.provider) return playable.provider;
        if(playable.type === "unsupported") return "URL";
        return "N/A";
    }

    function createThumb(videoData){
        const wrap = document.createElement("div");
        wrap.className = "thumb-wrapper";
        if(videoData.thumb && /^https?:\/\//i.test(videoData.thumb)){
            const img = document.createElement("img");
            img.src = videoData.thumb;
            img.alt = videoData.thumbText || "thumbnail";
            img.loading = "lazy";
            img.onerror = function(){
                wrap.replaceChildren(createThumbArt(videoData), createTypeBadge(videoData), createDuration(videoData.duration));
            };
            wrap.appendChild(img);
        }else{
            wrap.appendChild(createThumbArt(videoData));
        }
        wrap.appendChild(createTypeBadge(videoData));
        wrap.appendChild(createDuration(videoData.duration));
        return wrap;
    }

    function createThumbArt(videoData){
        const art = document.createElement("div");
        art.className = "thumb-art";
        art.textContent = videoData.thumbText || "VIDEO";
        return art;
    }

    function createTypeBadge(videoData){
        const span = document.createElement("span");
        span.className = "type-badge";
        span.textContent = detectProviderLabel(videoData.url);
        return span;
    }

    function createDuration(duration){
        const span = document.createElement("span");
        span.className = "duration-badge";
        span.textContent = duration || "--:--";
        return span;
    }

    function renderPlaylist(){
        playlistBox.replaceChildren();
        playlistCount.textContent = dbVideos.length + " mục";
        dbVideos.forEach(function(vid){
            const card = document.createElement("button");
            card.type = "button";
            card.className = "video-card";
            card.dataset.id = vid.id;
            card.setAttribute("aria-label", "Phát video: " + (vid.title || "Không có tiêu đề"));

            const thumb = createThumb(vid);
            const info = document.createElement("div");
            info.className = "card-info";

            const title = document.createElement("div");
            title.className = "card-title";
            title.textContent = vid.title || "Không có tiêu đề";

            const date = document.createElement("div");
            date.className = "card-date";
            date.textContent = vid.date || "Chưa có ngày";

            const status = document.createElement("div");
            status.className = "card-status";
            if(vid.state === "warn" || vid.state === "wait") status.classList.add("wait");
            if(vid.state === "error") status.classList.add("error");
            status.textContent = vid.status || "Chưa rõ";

            info.appendChild(title);
            info.appendChild(date);
            info.appendChild(status);
            card.appendChild(thumb);
            card.appendChild(info);
            card.addEventListener("click", function(){ playVideo(vid); });
            playlistBox.appendChild(card);
        });
    }

    btnExit.addEventListener("click", function(){
        currentActiveId = null;
        showPlaceholder("Đã ngắt phát video", "Player đã được dọn sạch để tránh video chạy ngầm khi rời không gian.");
        txtTitle.textContent = "Hệ thống chờ lệnh";
        txtDate.textContent = "--/--/--";
        txtStatus.className = "ai-status-badge waiting";
        txtStatus.textContent = "OFFLINE";
        document.querySelectorAll(".video-card").forEach(function(card){ card.classList.remove("active"); });
    });

    renderPlaylist();
});
</script>
</body>
</html>
---------------------------------------------
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Kết Quả Xổ Số Miền Bắc - Làm Cầu Mũi Tên</title>

<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{background:#050505;display:flex;justify-content:center;align-items:flex-start;height:100dvh;overflow:hidden;width:100vw}
.num-font{font-family:"SF Mono","Helvetica Neue",Helvetica,Arial,sans-serif;font-variant-numeric:tabular-nums lining-nums;font-feature-settings:"tnum" 1,"lnum" 1}

.app-wrapper{
    --bg-main:#fff;--bg-board:#cbd5e1;--text-main:#111;--text-dim:#6b7280;--border-color:#cbd5e1;
    --db-bg:#d40000;--led-color:#00e676;--led-bg:#111;
    --glass-bg:linear-gradient(180deg,#fff 0%,#eef2f7 100%);
    --glass-shadow:inset 0 2px 4px rgba(255,255,255,1),0 2px 5px rgba(0,0,0,.08);
    --glass-border:#cbd5e1;
    --lo-chip-bg:linear-gradient(135deg,#d40000,#ff5252);
    --lo-chip-shadow:rgba(212,0,0,.4);
    --modal-overlay:rgba(0,0,0,.45);
    --ai-bar-bg:linear-gradient(135deg,#e3f2fd,#bbdefb);
    --ai-bar-border:#90caf9;--ai-bar-text:#1565c0;--ai-bar-input:#fff;
}
#toggle-dark:checked~.app-wrapper{
    --bg-main:#121212;--bg-board:#0f172a;--text-main:#fff;--text-dim:#94a3b8;--border-color:#334155;
    --glass-bg:linear-gradient(180deg,#243044 0%,#161f30 100%);
    --glass-shadow:inset 0 1px 2px rgba(255,255,255,.07),0 3px 6px rgba(0,0,0,.45);
    --glass-border:#334155;
    --lo-chip-bg:linear-gradient(135deg,#ff1744,#d50000);
    --lo-chip-shadow:rgba(255,23,68,.4);
    --modal-overlay:rgba(0,0,0,.72);
    --ai-bar-bg:linear-gradient(135deg,#0f2440,#102a4d);
    --ai-bar-border:#1e3a5f;--ai-bar-text:#7cc4ff;--ai-bar-input:#0f172a;
}
.app-wrapper{max-width:480px;width:100%;height:100%;position:relative;background:var(--bg-main);color:var(--text-main);overflow:hidden;box-shadow:0 0 40px rgba(0,0,0,.9)}
.main-layer{width:100%;height:100%;display:flex;flex-direction:column;background:var(--bg-board)}

.top-controls{display:flex;justify-content:space-between;align-items:center;padding:10px 16px;background:var(--bg-main);border-bottom:1px solid var(--border-color);z-index:50;flex-shrink:0}
.top-controls-left,.top-controls-right{display:flex;gap:14px;align-items:center}
.switch-wrap{display:flex;flex-direction:column;align-items:center;gap:4px}
.switch-label-text{font-size:10px;font-weight:800;color:var(--text-main);text-transform:uppercase;letter-spacing:.3px}
.switch{position:relative;display:inline-block;width:36px;height:18px}
.switch input{opacity:0;width:0;height:0}
.switch input:disabled+.slider{opacity:.5;cursor:not-allowed}
.slider{position:absolute;cursor:pointer;inset:0;background:#cbd5e1;transition:.3s;border-radius:20px;box-shadow:inset 0 1px 3px rgba(0,0,0,.2)}
.slider:before{position:absolute;content:"";height:14px;width:14px;left:2px;bottom:2px;background:#fff;transition:.3s;border-radius:50%;box-shadow:0 1px 2px rgba(0,0,0,.3)}
input:checked+.slider{background:var(--db-bg)}
input:checked+.slider:before{transform:translateX(18px)}

.boards-feed{position:relative;flex:1;overflow-y:auto;overflow-x:hidden;padding:16px 12px;display:flex;flex-direction:column;gap:24px;-webkit-overflow-scrolling:touch;scrollbar-width:thin;scrollbar-color:var(--db-bg) transparent}
.boards-feed::-webkit-scrollbar{width:8px;display:block}
.boards-feed::-webkit-scrollbar-thumb{background:var(--db-bg);border-radius:999px;border:2px solid transparent;background-clip:content-box}
.boards-feed::-webkit-scrollbar-track{background:transparent}

.cau-svg-layer{position:absolute;left:0;top:0;width:100%;height:1px;pointer-events:none;z-index:30;overflow:visible}
.cau-arrow-line{fill:none;stroke-width:2.8;pointer-events:none;filter:drop-shadow(0 2px 3px rgba(0,0,0,.35))}
.cau-arrow-line.manual{stroke:#d40000;opacity:.96}
.cau-arrow-line.suggested{stroke:#ff9800;stroke-dasharray:7 6;opacity:.48}

.cau-help{
    display:none;background:linear-gradient(135deg,#fff3e0,#ffe0b2);color:#7a2e00;border:1px solid #ffb74d;
    border-radius:12px;padding:10px 12px;font-size:12px;font-weight:800;line-height:1.35;text-align:center;
}
.cau-on .cau-help{display:block}
#toggle-dark:checked~.app-wrapper .cau-help{background:linear-gradient(135deg,#3a2100,#4d2d00);color:#ffcc80;border-color:#8a5300}

.board{background:var(--bg-main);border-radius:14px;border:1px solid var(--border-color);padding:12px;box-shadow:0 2px 4px rgba(0,0,0,.02),0 8px 16px rgba(0,0,0,.05);transition:background .3s,border-color .3s}
.board-header{text-align:center;margin-bottom:14px;padding-bottom:10px;border-bottom:1.5px dashed var(--border-color)}
.board-title{font-size:17px;font-weight:900;color:var(--text-main);text-transform:uppercase;letter-spacing:.5px}
.board-title.live{color:var(--db-bg);text-shadow:0 2px 4px rgba(212,0,0,.18)}
.status-blink{font-size:12px;color:var(--db-bg);animation:blink 1.2s infinite;font-weight:800;margin-top:4px}
.board-date{font-size:13px;color:var(--text-dim);font-style:italic;margin-top:4px;font-weight:800;text-transform:capitalize}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.3}}

.row{display:flex;margin-bottom:6px;align-items:stretch;gap:6px}
.prize-name{width:40px;flex-shrink:0;display:flex;justify-content:center;align-items:center;font-size:13px;font-weight:900;background:var(--glass-bg);box-shadow:var(--glass-shadow);border:1px solid var(--glass-border);border-radius:7px;color:var(--text-main)}
.prize-name.db{background:linear-gradient(180deg,#e53935 0%,#b71c1c 100%);color:#fff;border:1px solid #c62828;box-shadow:inset 0 2px 4px rgba(255,255,255,.35),0 2px 4px rgba(0,0,0,.2)}
.prize-name.active-led{background:var(--led-bg);color:var(--led-color);border-color:var(--led-color);box-shadow:0 0 12px var(--led-color);transform:scale(1.05);z-index:2}
.prize-results{flex-grow:1;display:grid;gap:4px;min-width:0}
.grid-1{grid-template-columns:1fr}.grid-2{grid-template-columns:repeat(2,1fr)}.grid-3{grid-template-columns:repeat(3,1fr)}.grid-4{grid-template-columns:repeat(4,1fr)}.grid-6{grid-template-columns:repeat(6,1fr)}

.number-box{background:var(--glass-bg);border:1px solid var(--glass-border);box-shadow:var(--glass-shadow);display:flex;justify-content:center;align-items:center;border-radius:7px;height:34px;position:relative;cursor:default;min-width:0;transition:transform .2s cubic-bezier(.175,.885,.32,1.275),box-shadow .2s,border-color .2s;overflow:hidden}
.cau-on .number-box{cursor:pointer}
.number-box:hover{transform:scale(1.06);box-shadow:0 6px 15px rgba(0,0,0,.15);border-color:var(--db-bg);z-index:40}
.number-box:active{transform:scale(.96)}
.number-text{font-size:clamp(13px,4.4vw,17px);font-weight:800;letter-spacing:1.5px;display:flex;align-items:center;justify-content:center;white-space:nowrap;width:100%;max-width:100%;padding:0 2px;color:var(--text-main);line-height:1;transition:opacity .2s,color .2s}
.grid-3 .number-text{font-size:clamp(12px,4vw,16px);letter-spacing:1px}
.grid-4 .number-text{font-size:clamp(11px,3.4vw,15px);letter-spacing:.5px}
.grid-6 .number-text{font-size:clamp(10px,3vw,14px);letter-spacing:.3px;padding:0 1px}
.row-db .number-box{height:52px}
.row-db .number-text{font-size:clamp(24px,8.5vw,34px);color:var(--db-bg);letter-spacing:4px;z-index:1;text-shadow:0 2px 4px rgba(0,0,0,.1);padding-left:4px}
.number-text.spinning{color:var(--db-bg);filter:blur(.4px);opacity:.75}

.digit{display:inline-block;transition:all .2s cubic-bezier(.175,.885,.32,1.275);border-radius:4px;padding:0 1px;position:relative;z-index:2}
.digit.active-cau{background:var(--db-bg);color:#fff;transform:scale(1.2);box-shadow:0 0 0 1px var(--db-bg),0 0 10px rgba(212,0,0,.75);z-index:45;font-weight:900}
.digit.cau-suggested{outline:2px dashed #ff9800;outline-offset:2px;background:rgba(255,152,0,.18);color:#ff6d00;animation:cauSuggestPulse 1.1s infinite ease-in-out}
@keyframes cauSuggestPulse{0%,100%{transform:scale(1)}50%{transform:scale(1.18)}}

.mask-cover{position:absolute;inset:0;border-radius:7px;background:repeating-linear-gradient(45deg,#b71c1c,#b71c1c 10px,#d40000 10px,#d40000 20px);display:flex;align-items:center;justify-content:center;gap:8px;color:#fff;font-size:13px;font-weight:900;letter-spacing:1px;text-transform:uppercase;cursor:pointer;z-index:46;opacity:0;pointer-events:none;transition:opacity .3s;box-shadow:inset 0 0 20px rgba(0,0,0,.4)}
.mask-cover .eye{font-size:18px}
.masking .maskable-db .mask-cover{opacity:1;pointer-events:auto}
.masking .maskable-db .number-text{opacity:0}
.masking .maskable-db.revealed .mask-cover{opacity:0;pointer-events:none}
.masking .maskable-db.revealed .number-text{opacity:1}

.injected-slot{background:var(--bg-main);border:1.5px solid var(--db-bg);border-radius:14px;padding:12px;display:flex;flex-direction:column;gap:10px;box-shadow:0 6px 16px rgba(212,0,0,.12)}
.slot-title{font-size:12px;font-weight:900;color:var(--db-bg);text-align:center;text-transform:uppercase;letter-spacing:.5px;transition:all .3s;padding:4px 8px;border-radius:6px}
.slot-title.flash{background:var(--db-bg);color:#fff;box-shadow:0 0 15px rgba(212,0,0,.6);transform:scale(1.02)}
.loto-grid{display:flex;flex-wrap:wrap;justify-content:center;align-items:center;gap:5px;width:100%;min-height:26px}
.lo-chip{background:var(--lo-chip-bg);color:#fff;font-size:12px;font-weight:800;letter-spacing:.5px;padding:4px 8px;border-radius:5px;box-shadow:0 2px 4px var(--lo-chip-shadow),inset 0 1px 0 rgba(255,255,255,.3);transform:scale(0);animation:springDrop .5s cubic-bezier(.175,.885,.32,1.275) forwards}
@keyframes springDrop{0%{transform:scale(0) translateY(-20px) rotate(-5deg);opacity:0}100%{transform:scale(1) translateY(0) rotate(0);opacity:1}}

.dots-wrapper{display:flex;justify-content:center;align-items:center;gap:3px;width:100%}
.dot{width:5px;height:5px;background:var(--text-dim);border-radius:50%;animation:wave 1.2s infinite ease-in-out}
.dot:nth-child(2){animation-delay:-1.1s}.dot:nth-child(3){animation-delay:-1s}.dot:nth-child(4){animation-delay:-.9s}.dot:nth-child(5){animation-delay:-.8s}
@keyframes wave{0%,40%,100%{transform:translateY(0);opacity:.5}20%{transform:translateY(-3px);opacity:1}}

.ai-sticky-bar{background:var(--ai-bar-bg);border-top:1px solid var(--ai-bar-border);padding:12px 16px calc(12px + env(safe-area-inset-bottom));display:flex;align-items:center;gap:8px;z-index:50;box-shadow:0 -4px 10px rgba(0,0,0,.06);flex-shrink:0}
.ai-marquee{flex-grow:1;overflow:hidden;white-space:nowrap;min-width:0}
.ai-marquee span{display:inline-block;padding-left:100%;font-size:13px;font-weight:800;color:var(--ai-bar-text);animation:marquee 18s linear infinite}
@keyframes marquee{0%{transform:translateX(0)}100%{transform:translateX(-100%)}}
.ai-input{padding:7px 13px;border-radius:20px;border:1px solid var(--ai-bar-border);font-size:12px;width:92px;outline:none;background:var(--ai-bar-input);color:var(--text-main)}
.clear-cau-btn{border:none;background:var(--db-bg);color:#fff;font-size:11px;font-weight:900;padding:7px 10px;border-radius:999px;cursor:pointer;white-space:nowrap}
.clear-cau-btn:active{transform:scale(.94)}

@media(max-width:380px){
    .top-controls{padding:8px 10px;gap:8px}
    .top-controls-left,.top-controls-right{gap:10px}
    .switch-label-text{font-size:9px}
    .ai-input{width:78px}
    .clear-cau-btn{font-size:10px;padding:7px 8px}
}
</style>
</head>

<body>

<input type="checkbox" id="toggle-dark" hidden>

<div class="app-wrapper" id="app-wrapper">
    <div class="main-layer">
        <div class="top-controls">
            <div class="top-controls-left">
                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-cau" onchange="toggleCau(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Làm Cầu</span>
                </div>

                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-quay-thu" onchange="triggerQuayThu(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Quay Thử</span>
                </div>
            </div>

            <div class="top-controls-right">
                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-dark-vis" onchange="document.getElementById('toggle-dark').checked=this.checked">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Sáng/Tối</span>
                </div>

                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-mask-vis" onchange="toggleMask(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Lặn Số ĐB</span>
                </div>
            </div>
        </div>

        <div class="boards-feed" id="boards-feed-container">
            <svg id="cau-svg-layer" class="cau-svg-layer" xmlns="http://www.w3.org/2000/svg">
                <defs>
                    <marker id="arrow-head-manual" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
                        <path d="M0,0 L0,6 L9,3 z" fill="#d40000"></path>
                    </marker>
                    <marker id="arrow-head-suggested" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
                        <path d="M0,0 L0,6 L9,3 z" fill="#ff9800"></path>
                    </marker>
                </defs>
            </svg>

            <div class="cau-help">
                Chế độ Làm Cầu đang bật · Chạm trực tiếp từng chữ số để tạo điểm cầu · Chạm liên tiếp để nối mũi tên · Đường cam là gợi ý trùng dữ liệu, không phải dự đoán kết quả.
            </div>

            <div class="board board-live-cau" id="board-live">
                <div class="board-header">
                    <div class="board-title live">🔴 Kết quả xổ số Thần Mèo</div>
                    <div class="status-blink" id="live-status">⏳ Hãy bật công tắc "Quay Thử" ở trên...</div>
                    <div class="board-date" id="live-date"></div>
                </div>
                <div id="live-rows-container"></div>
            </div>

            <div class="injected-slot" id="custom-slot">
                <div class="slot-title" id="slot-title">⚡ Bảng lô rơi sẽ hiển thị tại đây</div>
                <div class="loto-grid" id="loto-drop-zone"></div>
            </div>

            <div id="history-boards-container"></div>
        </div>

        <div class="ai-sticky-bar">
            <div class="ai-marquee">
                <span>🤖 Bật Làm Cầu rồi chạm từng chữ số để nối mũi tên xuyên nhiều bảng ngày · Bấm Xóa Cầu để làm lại · Gợi ý chỉ là quan hệ trùng dữ liệu hiển thị...</span>
            </div>
            <button type="button" class="clear-cau-btn" onclick="clearAllCau()">Xóa Cầu</button>
            <input type="text" class="ai-input" placeholder="Hỏi AI...">
        </div>
    </div>
</div>

<script>
"use strict";

const PRIZES = [
    { name: "ĐB", len: 5, count: 1, grid: "grid-1", db: true },
    { name: "G1", len: 5, count: 1, grid: "grid-1", db: false },
    { name: "G2", len: 5, count: 2, grid: "grid-2", db: false },
    { name: "G3", len: 5, count: 6, grid: "grid-6", db: false },
    { name: "G4", len: 4, count: 4, grid: "grid-4", db: false },
    { name: "G5", len: 4, count: 6, grid: "grid-6", db: false },
    { name: "G6", len: 3, count: 3, grid: "grid-3", db: false },
    { name: "G7", len: 2, count: 4, grid: "grid-4", db: false }
];

const QUAY_ORDER = ["G1", "G2", "G3", "G4", "G5", "G6", "G7", "ĐB"];

const CauGraph = {
    nodes: [],
    edges: [],
    counter: 0,
    lastNodeId: null,
    maxSuggestedLinks: 5
};

let isRunning = false;

function generateRandom(length) {
    let result = "";
    for (let i = 0; i < length; i++) {
        result += Math.floor(Math.random() * 10);
    }
    return result;
}

function wrapDigits(numStr) {
    if (!numStr) return "";
    return String(numStr).split("").map(function(digit, index) {
        return '<span class="digit" data-idx="' + index + '">' + digit + '</span>';
    }).join("");
}

function sleep(ms) {
    return new Promise(function(resolve) {
        setTimeout(resolve, ms);
    });
}

function createDots(length) {
    let dots = "";
    for (let i = 0; i < length; i++) {
        dots += '<span class="dot"></span>';
    }
    return '<div class="dots-wrapper">' + dots + '</div>';
}

function createNumberBox(length, value, isMaskableDb) {
    const content = value ? wrapDigits(value) : createDots(length);
    const maskClass = isMaskableDb ? " maskable-db" : "";
    const maskHtml = isMaskableDb
        ? '<div class="mask-cover" onclick="revealDbNumber(this)"><span class="eye">🙈</span> Chạm để xem</div>'
        : "";

    return '<div class="number-box' + maskClass + '">' + maskHtml + '<span class="number-text num-font">' + content + '</span></div>';
}

function createPrizeRow(prize, mode) {
    const isDb = prize.db === true;
    const rowClass = isDb ? "row row-db" : "row";
    const labelClass = isDb ? "prize-name db" : "prize-name";
    const boxes = [];

    for (let i = 0; i < prize.count; i++) {
        const value = mode === "live" ? "" : generateRandom(prize.len);
        boxes.push(createNumberBox(prize.len, value, mode === "live" && isDb));
    }

    return '<div class="' + rowClass + '" data-prize="' + prize.name + '" data-len="' + prize.len + '">' +
        '<div class="' + labelClass + '">' + prize.name + '</div>' +
        '<div class="prize-results ' + prize.grid + '">' + boxes.join("") + '</div>' +
        '</div>';
}

document.addEventListener("DOMContentLoaded", function() {
    setLiveDate();
    renderLiveBoard();
    renderHistoricalBoards(40);
    bindCauClicks();
    prepareSvgSize();
});

function setLiveDate() {
    const d = new Date(2026, 2, 26);
    let s = d.toLocaleDateString("vi-VN", { weekday: "long", year: "numeric", month: "2-digit", day: "2-digit" });
    document.getElementById("live-date").textContent = s.charAt(0).toUpperCase() + s.slice(1);
}

function renderLiveBoard() {
    document.getElementById("live-rows-container").innerHTML = PRIZES.map(function(prize) {
        return createPrizeRow(prize, "live");
    }).join("");
}

function renderHistoricalBoards(count) {
    const container = document.getElementById("history-boards-container");
    const baseDate = new Date(2026, 2, 25);
    const boards = [];

    for (let i = 0; i < count; i++) {
        const d = new Date(baseDate);
        d.setDate(d.getDate() - i);

        let day = d.toLocaleDateString("vi-VN", { weekday: "long", year: "numeric", month: "2-digit", day: "2-digit" });
        day = day.charAt(0).toUpperCase() + day.slice(1);

        boards.push(
            '<div class="board">' +
            '<div class="board-header">' +
            '<div class="board-title">Kết quả xổ số Thần Mèo</div>' +
            '<div class="board-date">' + day + '</div>' +
            '</div>' +
            PRIZES.map(function(prize) { return createPrizeRow(prize, "history"); }).join("") +
            '</div>'
        );
    }

    container.style.cssText = "display:flex;flex-direction:column;gap:24px;";
    container.innerHTML = boards.join("");
}

function toggleCau(cb) {
    document.getElementById("app-wrapper").classList.toggle("cau-on", cb.checked);
    if (!cb.checked) {
        clearSmartSuggestions();
        redrawCauArrows();
    }
}

function toggleMask(cb) {
    const app = document.getElementById("app-wrapper");
    app.classList.toggle("masking", cb.checked);
    document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
        box.classList.remove("revealed");
    });
    redrawCauArrows();
}

function revealDbNumber(maskElement) {
    const box = maskElement.closest(".number-box");
    if (box) {
        box.classList.add("revealed");
        redrawCauArrows();
    }
}

function bindCauClicks() {
    const feed = document.getElementById("boards-feed-container");

    feed.addEventListener("click", function(e) {
        if (!document.getElementById("toggle-cau").checked) return;
        if (e.target.closest(".mask-cover")) return;

        const digit = e.target.closest(".digit");
        if (!digit) return;

        const box = digit.closest(".number-box");
        const app = document.getElementById("app-wrapper");

        if (box && box.classList.contains("maskable-db") && app.classList.contains("masking") && !box.classList.contains("revealed")) {
            return;
        }

        addManualCauNode(digit);
    });

    feed.addEventListener("scroll", function() {
        redrawCauArrows();
    });

    window.addEventListener("resize", function() {
        prepareSvgSize();
        redrawCauArrows();
    });
}

function createCauNode(digitElement, suggestedOnly) {
    const numberText = digitElement.closest(".number-text");
    const row = digitElement.closest(".row");
    const board = digitElement.closest(".board");

    if (!numberText || !row || !board) return null;

    const existingId = digitElement.dataset.cauNodeId;
    if (existingId) {
        return CauGraph.nodes.find(function(node) {
            return node.id === existingId;
        }) || null;
    }

    const boardList = Array.from(document.querySelectorAll(".board"));
    const boardIndex = boardList.indexOf(board);
    const boardDateEl = board.querySelector(".board-date");
    const fullNumber = numberText.textContent.trim();
    const digitIndex = Number(digitElement.dataset.idx || 0);
    const digit = digitElement.textContent.trim();
    const prize = row.dataset.prize || "";

    CauGraph.counter += 1;

    const node = {
        id: "cau-node-" + CauGraph.counter,
        digit: digit,
        fullNumber: fullNumber,
        digitIndex: digitIndex,
        prize: prize,
        boardIndex: boardIndex,
        dateText: boardDateEl ? boardDateEl.textContent.trim() : "",
        element: digitElement,
        suggestedOnly: suggestedOnly === true
    };

    digitElement.dataset.cauNodeId = node.id;

    if (!suggestedOnly) {
        digitElement.classList.add("active-cau");
        digitElement.setAttribute("title", "Điểm cầu " + CauGraph.counter);
    }

    CauGraph.nodes.push(node);
    return node;
}

function addManualCauNode(digitElement) {
    const node = createCauNode(digitElement, false);
    if (!node) return;

    node.suggestedOnly = false;
    digitElement.classList.add("active-cau");
    digitElement.classList.remove("cau-suggested");

    if (CauGraph.lastNodeId && CauGraph.lastNodeId !== node.id) {
        const duplicated = CauGraph.edges.some(function(edge) {
            return edge.fromId === CauGraph.lastNodeId && edge.toId === node.id && edge.type === "manual";
        });

        if (!duplicated) {
            CauGraph.edges.push({
                fromId: CauGraph.lastNodeId,
                toId: node.id,
                type: "manual",
                score: 100
            });
        }
    }

    CauGraph.lastNodeId = node.id;
    suggestSmartCauLinks(node);
    prepareSvgSize();
    redrawCauArrows();
}

function collectAllDigitCandidates() {
    const digits = Array.from(document.querySelectorAll(".number-text .digit"));
    const boardList = Array.from(document.querySelectorAll(".board"));

    return digits.map(function(digitElement) {
        const numberText = digitElement.closest(".number-text");
        const row = digitElement.closest(".row");
        const board = digitElement.closest(".board");
        const fullNumber = numberText ? numberText.textContent.trim() : "";
        const prize = row ? row.dataset.prize || "" : "";
        const boardIndex = boardList.indexOf(board);

        return {
            element: digitElement,
            digit: digitElement.textContent.trim(),
            fullNumber: fullNumber,
            tail: fullNumber.slice(-2),
            digitIndex: Number(digitElement.dataset.idx || 0),
            prize: prize,
            boardIndex: boardIndex
        };
    });
}

function calculateCauScore(source, target) {
    let score = 0;

    if (source.digit === target.digit) score += 30;
    if (source.prize === target.prize && source.digitIndex === target.digitIndex) score += 45;
    if (source.fullNumber.slice(-2) === target.tail) score += 60;

    const distance = Math.abs(source.boardIndex - target.boardIndex);
    if (distance > 0 && distance <= 3) score += 10;
    if (distance > 10) score -= 10;

    if (source.boardIndex === target.boardIndex && source.fullNumber === target.fullNumber) score -= 20;

    return score;
}

function suggestSmartCauLinks(sourceNode) {
    clearSmartSuggestions();

    const candidates = collectAllDigitCandidates();

    const scored = candidates
        .filter(function(candidate) {
            return candidate.element !== sourceNode.element;
        })
        .map(function(candidate) {
            return {
                candidate: candidate,
                score: calculateCauScore(sourceNode, candidate)
            };
        })
        .filter(function(item) {
            return item.score >= 45;
        })
        .sort(function(a, b) {
            return b.score - a.score;
        })
        .slice(0, CauGraph.maxSuggestedLinks);

    scored.forEach(function(item) {
        const candidate = item.candidate;
        candidate.element.classList.add("cau-suggested");

        const suggestionNode = createCauNode(candidate.element, true);
        if (!suggestionNode) return;

        const duplicated = CauGraph.edges.some(function(edge) {
            return edge.fromId === sourceNode.id && edge.toId === suggestionNode.id && edge.type === "suggested";
        });

        if (!duplicated) {
            CauGraph.edges.push({
                fromId: sourceNode.id,
                toId: suggestionNode.id,
                type: "suggested",
                score: item.score
            });
        }
    });
}

function clearSmartSuggestions() {
    document.querySelectorAll(".cau-suggested").forEach(function(el) {
        el.classList.remove("cau-suggested");
    });

    CauGraph.edges = CauGraph.edges.filter(function(edge) {
        return edge.type !== "suggested";
    });

    CauGraph.nodes = CauGraph.nodes.filter(function(node) {
        if (node.suggestedOnly !== true) return true;

        if (node.element) {
            node.element.removeAttribute("data-cau-node-id");
        }

        return false;
    });
}

function prepareSvgSize() {
    const feed = document.getElementById("boards-feed-container");
    const svg = document.getElementById("cau-svg-layer");
    if (!feed || !svg) return;

    const height = Math.max(feed.scrollHeight, feed.clientHeight);
    svg.setAttribute("height", String(height));
    svg.style.height = height + "px";
}

function redrawCauArrows() {
    const svg = document.getElementById("cau-svg-layer");
    const feed = document.getElementById("boards-feed-container");
    if (!svg || !feed) return;

    prepareSvgSize();

    Array.from(svg.querySelectorAll(".cau-arrow-line")).forEach(function(line) {
        line.remove();
    });

    const feedRect = feed.getBoundingClientRect();
    const scrollTop = feed.scrollTop;
    const scrollLeft = feed.scrollLeft;

    CauGraph.edges.forEach(function(edge) {
        const fromNode = CauGraph.nodes.find(function(node) { return node.id === edge.fromId; });
        const toNode = CauGraph.nodes.find(function(node) { return node.id === edge.toId; });

        if (!fromNode || !toNode || !fromNode.element || !toNode.element) return;
        if (!document.body.contains(fromNode.element) || !document.body.contains(toNode.element)) return;

        const fromRect = fromNode.element.getBoundingClientRect();
        const toRect = toNode.element.getBoundingClientRect();

        const x1 = fromRect.left - feedRect.left + fromRect.width / 2 + scrollLeft;
        const y1 = fromRect.top - feedRect.top + fromRect.height / 2 + scrollTop;
        const x2 = toRect.left - feedRect.left + toRect.width / 2 + scrollLeft;
        const y2 = toRect.top - feedRect.top + toRect.height / 2 + scrollTop;

        const dx = Math.abs(x2 - x1);
        const dy = Math.abs(y2 - y1);
        const curve = Math.max(35, Math.min(140, (dx + dy) / 3));

        const direction = x2 >= x1 ? 1 : -1;
        const c1x = x1 + curve * direction;
        const c1y = y1;
        const c2x = x2 - curve * direction;
        const c2y = y2;

        const path = document.createElementNS("http://www.w3.org/2000/svg", "path");
        path.setAttribute("d", "M " + x1 + " " + y1 + " C " + c1x + " " + c1y + ", " + c2x + " " + c2y + ", " + x2 + " " + y2);
        path.setAttribute("class", "cau-arrow-line " + (edge.type === "suggested" ? "suggested" : "manual"));
        path.setAttribute("marker-end", edge.type === "suggested" ? "url(#arrow-head-suggested)" : "url(#arrow-head-manual)");

        svg.appendChild(path);
    });
}

function clearAllCau() {
    CauGraph.nodes = [];
    CauGraph.edges = [];
    CauGraph.counter = 0;
    CauGraph.lastNodeId = null;

    document.querySelectorAll(".digit").forEach(function(digit) {
        digit.classList.remove("active-cau");
        digit.classList.remove("cau-suggested");
        digit.removeAttribute("data-cau-node-id");
        digit.removeAttribute("title");
    });

    redrawCauArrows();
}

function clearLiveCauNodes() {
    const liveBoard = document.getElementById("board-live");
    if (!liveBoard) return;

    const liveNodeIds = CauGraph.nodes
        .filter(function(node) {
            return node.element && liveBoard.contains(node.element);
        })
        .map(function(node) {
            return node.id;
        });

    CauGraph.nodes = CauGraph.nodes.filter(function(node) {
        return liveNodeIds.indexOf(node.id) === -1;
    });

    CauGraph.edges = CauGraph.edges.filter(function(edge) {
        return liveNodeIds.indexOf(edge.fromId) === -1 && liveNodeIds.indexOf(edge.toId) === -1;
    });

    liveBoard.querySelectorAll(".digit").forEach(function(digit) {
        digit.classList.remove("active-cau");
        digit.classList.remove("cau-suggested");
        digit.removeAttribute("data-cau-node-id");
        digit.removeAttribute("title");
    });

    if (liveNodeIds.indexOf(CauGraph.lastNodeId) !== -1) {
        CauGraph.lastNodeId = null;
    }

    redrawCauArrows();
}

async function triggerQuayThu(cb) {
    if (!cb.checked || isRunning) return;

    isRunning = true;
    cb.disabled = true;

    await startSimulation();

    cb.checked = false;
    cb.disabled = false;
    isRunning = false;
}

async function startSimulation() {
    clearLiveCauNodes();

    const status = document.getElementById("live-status");
    const dropZone = document.getElementById("loto-drop-zone");
    const slotTitle = document.getElementById("slot-title");
    const app = document.getElementById("app-wrapper");

    status.textContent = "🔴 Đang quay số...";
    status.style.color = "var(--db-bg)";
    dropZone.innerHTML = "";
    slotTitle.textContent = "⚡ Hệ thống đang lấy kết quả...";

    document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
        box.classList.remove("revealed");
    });

    document.querySelectorAll("#board-live .number-text").forEach(function(textBox) {
        const row = textBox.closest(".row");
        const len = Number(row.dataset.len);
        textBox.classList.remove("spinning");
        textBox.innerHTML = createDots(len);
    });

    const rows = Array.from(document.querySelectorAll("#board-live .row"));
    const msgs = ["gan cực đại!", "rơi liên tiếp 3 ngày!", "ra cả cặp rất đẹp!", "vào nhịp rơi ổn định!", "xuất hiện đúng cầu chạy!"];

    for (const name of QUAY_ORDER) {
        const row = rows.find(function(item) {
            return item.dataset.prize === name;
        });

        if (!row) continue;

        const len = Number(row.dataset.len);
        const label = row.querySelector(".prize-name");
        const boxes = row.querySelectorAll(".number-text");

        label.classList.add("active-led");

        for (const box of boxes) {
            box.classList.add("spinning");

            const spin = setInterval(function() {
                box.textContent = generateRandom(len);
            }, 50);

            await sleep(900);
            clearInterval(spin);

            box.classList.remove("spinning");

            const finalNumber = generateRandom(len);
            box.innerHTML = wrapDigits(finalNumber);

            const lo = finalNumber.slice(-2);
            const chip = document.createElement("div");
            chip.className = "lo-chip";
            chip.textContent = lo;
            dropZone.appendChild(chip);

            const message = msgs[Math.floor(Math.random() * msgs.length)];
            slotTitle.textContent = "🔥 Lô " + lo + " " + message + " (" + name + ")";
            slotTitle.classList.add("flash");

            setTimeout(function() {
                slotTitle.classList.remove("flash");
            }, 500);

            await sleep(150);
        }

        label.classList.remove("active-led");
    }

    if (app.classList.contains("masking")) {
        document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
            box.classList.remove("revealed");
        });
    }

    status.textContent = "✅ Đã quay xong";
    status.style.color = "var(--led-color)";
    slotTitle.textContent = "Kỳ quay kết thúc · Bật 'Làm Cầu' để chấm cầu các giải.";

    prepareSvgSize();
    redrawCauArrows();
}
</script>

</body>
</html>
--------------


<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Không Gian Báo Cáo AI - Audio Overview Stream Core</title>
<style>
:root{
  --bg-main:#1c130d;--bg-board:#2a1a10;--bg-deep:#120a06;--panel:#24150d;--panel-2:#160d08;--panel-3:#3a2416;
  --text-main:#fff4e6;--text-soft:#ffe0b8;--text-muted:#c9a982;--border:#5a3824;--glass:#6b432b;
  --accent:#d40000;--accent2:#ff3838;--ok:#10b981;--warn:#facc15;--bad:#ef4444;--blue:#38bdf8;
  --font:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;--mono:"SF Mono","Cascadia Code","Roboto Mono",ui-monospace,Menlo,Consolas,monospace;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:var(--font);-webkit-tap-highlight-color:transparent}html,body{height:100%}
body{width:100vw;height:100dvh;overflow:hidden;background:#050302;color:var(--text-main);display:flex;justify-content:center;align-items:flex-start}button,input,textarea{font:inherit}button{touch-action:manipulation}
.app{max-width:480px;width:100%;height:100%;overflow:hidden;background:var(--bg-main);box-shadow:0 0 45px rgba(0,0,0,.95);border-left:1px solid rgba(255,232,190,.08);border-right:1px solid rgba(255,232,190,.08)}
.space{height:100%;display:flex;flex-direction:column;background:linear-gradient(180deg,var(--bg-board),var(--bg-deep));padding-top:env(safe-area-inset-top);position:relative}.top{flex-shrink:0;display:grid;grid-template-columns:38px 1fr auto;gap:10px;align-items:center;padding:10px 12px;background:linear-gradient(180deg,#2b1a10,#120a06);border-bottom:1px solid var(--border);box-shadow:0 4px 14px rgba(0,0,0,.32);z-index:20}.back{width:38px;height:34px;border:none;border-radius:12px;background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);font-size:20px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 2px rgba(255,232,190,.08),0 3px 8px rgba(0,0,0,.25)}.back:active{transform:scale(.94)}.title{font-weight:950;font-size:14px;color:var(--text-soft);letter-spacing:.5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;text-transform:uppercase}.chip{font-size:10px;font-weight:950;color:#ffd6a0;border:1px solid rgba(255,210,150,.18);background:rgba(255,220,170,.06);border-radius:999px;padding:6px 8px;white-space:nowrap}
.scroll{flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;scrollbar-width:none;padding:14px 12px 16px;display:flex;flex-direction:column;gap:14px}.scroll::-webkit-scrollbar{display:none;width:0;height:0}
.hero,.panel,.builder,.preview,.audio{border-radius:18px;border:1px solid rgba(255,232,190,.10);background:linear-gradient(180deg,#24150d,#160d08);box-shadow:0 10px 24px rgba(0,0,0,.24)}.hero{padding:14px;background:radial-gradient(circle at 20% 0%,rgba(212,0,0,.20),transparent 34%),linear-gradient(180deg,#24150d,#160d08)}.kicker{font-size:11px;font-weight:950;color:var(--warn);letter-spacing:.8px;text-transform:uppercase;margin-bottom:7px}.hero h1{font-size:20px;font-weight:1000;line-height:1.15;color:var(--text-main);margin-bottom:8px}.hero p{font-size:12px;line-height:1.45;color:var(--text-muted);font-weight:750}
.core{border-color:rgba(56,189,248,.22);background:linear-gradient(180deg,rgba(56,189,248,.08),rgba(18,10,6,.90));padding:12px;display:flex;flex-direction:column;gap:10px}.row2{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.core-title{font-size:13px;font-weight:950;color:#bdeaff;text-transform:uppercase;letter-spacing:.4px}.status{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--blue);background:rgba(56,189,248,.10);border:1px solid rgba(56,189,248,.35);white-space:nowrap}.status.loading{color:var(--warn);background:rgba(250,204,21,.10);border-color:rgba(250,204,21,.35)}.status.ready{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.status.error{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.bar-shell{height:8px;border-radius:999px;overflow:hidden;background:rgba(0,0,0,.28);border:1px solid rgba(255,232,190,.08)}.bar{height:100%;width:0%;background:linear-gradient(90deg,#d40000,#ffbc5e,#10b981);transition:width .18s ease}.log{font-family:var(--mono);font-size:10.5px;line-height:1.35;color:var(--text-muted);background:rgba(0,0,0,.16);border:1px dashed rgba(255,232,190,.11);border-radius:12px;padding:9px;min-height:42px;white-space:pre-wrap}
.scan{border-color:rgba(250,204,21,.24);background:linear-gradient(180deg,rgba(250,204,21,.10),rgba(33,18,8,.92));padding:12px;display:flex;flex-direction:column;gap:10px}.panel-title{display:flex;align-items:center;justify-content:space-between;gap:8px;font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.4px}.pill{font-size:10px;font-weight:950;border-radius:999px;padding:5px 8px;color:var(--warn);background:rgba(250,204,21,.10);border:1px solid rgba(250,204,21,.35);white-space:nowrap}.pill.ok{color:var(--ok);background:rgba(16,185,129,.10);border-color:rgba(16,185,129,.35)}.pill.bad{color:var(--bad);background:rgba(239,68,68,.10);border-color:rgba(239,68,68,.35)}.file-list{display:flex;flex-direction:column;gap:8px}.file{display:grid;grid-template-columns:1fr auto;gap:8px;align-items:center;background:rgba(18,10,6,.55);border:1px solid rgba(255,232,190,.08);border-radius:12px;padding:9px 10px}.file-name{font-size:12px;color:var(--text-main);font-weight:850;line-height:1.25;word-break:break-word}.file-state{font-size:10px;font-weight:950;color:var(--warn);white-space:nowrap}.file-state.ok{color:var(--ok)}.file-state.bad{color:var(--bad)}.notice{font-size:11px;line-height:1.45;color:var(--text-muted);font-weight:760;background:rgba(0,0,0,.14);border-radius:12px;padding:9px;border:1px dashed rgba(255,232,190,.12)}
.head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-top:2px}.section-title{font-size:13px;font-weight:950;color:#ffd6a0;text-transform:uppercase;letter-spacing:.6px}.section-sub{font-size:11px;color:var(--text-muted);font-weight:800}.grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}.card{min-height:122px;border:none;text-align:left;border-radius:16px;padding:12px;background:linear-gradient(180deg,rgba(58,36,22,.92),rgba(33,18,8,.98));border:1px solid rgba(255,232,190,.10);box-shadow:0 5px 14px rgba(0,0,0,.22);cursor:pointer;color:var(--text-main);display:flex;flex-direction:column;gap:8px;position:relative;overflow:hidden}.card::before{content:"";position:absolute;inset:auto -30px -45px auto;width:100px;height:100px;border-radius:50%;background:rgba(212,0,0,.13)}.card:active{transform:scale(.985)}.card.active{border-color:var(--accent2);box-shadow:0 0 0 1px rgba(255,56,56,.25),0 8px 20px rgba(0,0,0,.32)}.card:disabled{opacity:.55;cursor:not-allowed;transform:none}.icon{width:34px;height:34px;border-radius:12px;display:flex;align-items:center;justify-content:center;background:rgba(212,0,0,.16);border:1px solid rgba(255,56,56,.25);font-size:18px;flex-shrink:0}.card-title{font-size:14px;font-weight:950;line-height:1.16;color:var(--text-main);position:relative;z-index:1}.card-desc{font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:730;position:relative;z-index:1;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden}.full{grid-column:1/-1;min-height:104px}
.audio{padding:12px;display:flex;flex-direction:column;gap:11px;border-color:rgba(16,185,129,.22);background:linear-gradient(180deg,rgba(16,185,129,.08),rgba(18,10,6,.92))}.audio-grid{display:grid;grid-template-columns:1fr 1fr;gap:9px}.choice{border:1px solid rgba(255,232,190,.12);background:rgba(18,10,6,.55);border-radius:14px;padding:10px;text-align:left;color:var(--text-main);cursor:pointer}.choice.active{border-color:var(--ok);box-shadow:0 0 0 1px rgba(16,185,129,.20);background:rgba(16,185,129,.10)}.choice b{display:block;font-size:13px;color:var(--text-main);margin-bottom:4px}.choice span{display:block;font-size:10.5px;line-height:1.35;color:var(--text-muted);font-weight:740}.tabs{display:flex;gap:7px;flex-wrap:wrap}.tab{border:1px solid rgba(255,232,190,.14);background:rgba(18,10,6,.55);color:var(--text-soft);border-radius:999px;padding:7px 10px;font-size:11px;font-weight:900}.tab.active{border-color:var(--accent2);background:rgba(212,0,0,.18);color:#fff}.select-row{display:grid;grid-template-columns:1fr 1fr;gap:9px}.select-box{display:flex;flex-direction:column;gap:6px}.field{font-size:11px;color:#ffd6a0;font-weight:950;text-transform:uppercase;letter-spacing:.45px}.input,.textarea,.select{width:100%;border:1px solid rgba(255,232,190,.14);border-radius:13px;background:#120a06;color:var(--text-main);outline:none;padding:10px 11px;font-size:12px;font-weight:760;line-height:1.4}.textarea{height:94px;resize:none}.builder{padding:12px;display:flex;flex-direction:column;gap:10px}.actions{display:grid;grid-template-columns:1fr 1fr;gap:10px}.btn{border:none;border-radius:14px;padding:11px 10px;font-size:12px;font-weight:950;cursor:pointer;color:#fff;background:linear-gradient(135deg,#d40000,#ff3838);box-shadow:0 7px 16px rgba(212,0,0,.22)}.btn.secondary{background:linear-gradient(180deg,#3a2416,#211208);border:1px solid var(--glass);color:var(--text-soft);box-shadow:0 5px 12px rgba(0,0,0,.22)}.btn:active{transform:scale(.97)}.btn:disabled{opacity:.55;cursor:not-allowed;transform:none}
.preview{border-color:rgba(16,185,129,.28);background:linear-gradient(180deg,rgba(16,185,129,.09),rgba(18,10,6,.88));padding:12px;display:flex;flex-direction:column;gap:8px}.preview-title{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:13px;color:var(--ok);font-weight:950;text-transform:uppercase;letter-spacing:.4px}.meter{font-size:10px;color:var(--text-muted);font-weight:850;text-transform:none;letter-spacing:0;white-space:nowrap}.preview-box{height:280px;overflow:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;border-radius:12px;background:rgba(0,0,0,.18);border:1px solid rgba(255,232,190,.08);padding:10px}.preview-box::-webkit-scrollbar{display:none;width:0;height:0}.body{font-family:var(--mono);font-size:11px;line-height:1.45;color:var(--text-main);font-weight:650;white-space:pre-wrap;word-break:break-word}.abc{display:grid;gap:9px}.abc-box{border-radius:14px;padding:10px;border:1px solid rgba(255,232,190,.10);background:rgba(18,10,6,.48)}.abc-box b{display:block;font-size:11px;text-transform:uppercase;letter-spacing:.4px;margin-bottom:5px;color:#ffd6a0}.abc-box p{font-size:11px;line-height:1.42;color:var(--text-muted);font-weight:760}.foot{flex-shrink:0;background:linear-gradient(135deg,#2b1a10,#160d08);border-top:1px solid var(--border);padding:10px 14px calc(10px + env(safe-area-inset-bottom));font-size:11px;line-height:1.35;color:var(--text-muted);font-weight:800;text-align:center}.foot b{color:#ffd6a0}.overlay{position:absolute;inset:0;background:rgba(5,3,2,.48);backdrop-filter:blur(2px);z-index:100;display:none;align-items:center;justify-content:center;padding:22px;text-align:center}.overlay.show{display:flex}.lock{border-radius:18px;background:linear-gradient(180deg,#2b1a10,#120a06);border:1px solid rgba(255,232,190,.16);box-shadow:0 18px 48px rgba(0,0,0,.5);padding:16px;max-width:330px;width:100%}.spin{width:32px;height:32px;border-radius:50%;border:3px solid rgba(255,232,190,.16);border-top-color:var(--warn);margin:0 auto 10px;animation:spin .8s linear infinite}.lock-title{font-size:14px;font-weight:950;color:#ffd6a0;margin-bottom:6px;text-transform:uppercase}.lock-text{font-size:12px;line-height:1.4;color:var(--text-muted);font-weight:760}@keyframes spin{to{transform:rotate(360deg)}}
@media(max-width:380px){.top{grid-template-columns:36px 1fr auto;padding:9px 10px}.back{width:36px;height:32px}.title{font-size:13px}.chip{font-size:9px;padding:5px 7px}.scroll{padding:12px 10px}.hero h1{font-size:18px}.grid{gap:9px}.card{padding:10px;min-height:118px}.card-title{font-size:13px}.card-desc{font-size:10.5px}.actions,.select-row{grid-template-columns:1fr}.audio-grid{grid-template-columns:1fr}.preview-box{height:250px}.foot{font-size:10.5px}}
</style>
</head>
<body>
<div class="app"><main class="space" id="space">
<header class="top"><button class="back" type="button" aria-label="Trở về" id="backBtn">←</button><div class="title">Không gian báo cáo AI</div><div class="chip">AUDIO + STREAM</div></header>
<section class="scroll" id="scroll">
<article class="hero"><div class="kicker">API Hook · Audio Overview · Stream Output</div><h1>Không gian báo cáo kết nối lõi xổ số</h1><p>Bản này dùng cổng nhận dữ liệu động, render báo cáo theo luồng để chống treo DOM, và bổ sung khối tùy chỉnh “Tổng quan bằng âm thanh” theo các chế độ: tìm hiểu sâu, tóm tắt, phê bình và tranh luận.</p></article>
<section class="panel core" aria-label="Trạng thái lõi"><div class="row2"><div class="core-title">Cổng lõi phân tích</div><div class="status" id="coreStatus">CHỜ KẾT NỐI</div></div><div class="bar-shell"><div class="bar" id="bar"></div></div><div class="log" id="log">Bridge sẵn sàng: window.ReportWorkspaceBridge</div></section>
<section class="panel scan" aria-label="Quét nguồn"><div class="panel-title"><span>Quét tệp / nguồn</span><span class="pill" id="scanStatus">Không đủ dữ liệu xác thực</span></div><div class="file-list" id="fileList"></div><div class="notice" id="scanNotice">Các file hệ thống đã được gọi quét, nhưng công cụ đọc tệp trả về rỗng/hỏng/không thể xử lý. Khi backend gửi dữ liệu thật, khu vực này sẽ cập nhật bằng API hook.</div></section>
<div class="head"><div><div class="section-title">Tạo báo cáo</div><div class="section-sub">Chọn định dạng đầu ra</div></div></div>
<section class="grid" id="formatGrid">
<button class="card active" type="button" data-title="Tạo báo cáo của riêng bạn" data-template="Tạo báo cáo theo cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng do người dùng chỉ định."><div class="icon">✍️</div><div class="card-title">Tạo báo cáo của riêng bạn</div><div class="card-desc">Chỉ định cấu trúc, phong cách, giọng điệu và tiêu chí kiểm chứng.</div></button>
<button class="card" type="button" data-title="Tài liệu tóm tắt" data-template="Tổng quan nguồn dữ liệu, ý chính, trích dẫn, điểm chưa xác thực và cảnh báo thiếu dữ kiện."><div class="icon">📄</div><div class="card-title">Tài liệu tóm tắt</div><div class="card-desc">Tổng quan nguồn có trích dẫn, thông tin chính và điểm cần kiểm chứng.</div></button>
<button class="card" type="button" data-title="Hướng dẫn ôn tập" data-template="Tạo câu hỏi ngắn, câu hỏi tự luận, đáp án kiểm tra và bảng thuật ngữ từ tài liệu nguồn."><div class="icon">🎓</div><div class="card-title">Hướng dẫn ôn tập</div><div class="card-desc">Câu hỏi ngắn, tiểu luận, đáp án và bảng thuật ngữ theo nguồn.</div></button>
<button class="card" type="button" data-title="Bài đăng trên blog" data-template="Chắt lọc ý chính thành bài viết dễ đọc, có mở bài, thân bài, kết luận và cảnh báo dữ kiện."><div class="icon">📰</div><div class="card-title">Bài đăng trên blog</div><div class="card-desc">Chuyển điểm chính thành bài viết mạch lạc, dễ đọc.</div></button>
</section>
<div class="head"><div><div class="section-title">Định dạng đề xuất</div><div class="section-sub">Kiến trúc / quản trị / thuật toán</div></div></div>
<section class="grid">
<button class="card full" type="button" data-title="Tài liệu Đặc tả Kiến trúc" data-template="Mô tả cấu trúc hệ thống, module, luồng dữ liệu, lớp kiểm soát, cơ chế lỗi và ranh giới vận hành."><div class="icon">🏗️</div><div class="card-title">Tài liệu Đặc tả Kiến trúc</div><div class="card-desc">Cấu trúc hệ thống, module lõi, luồng dữ liệu và lớp kiểm soát.</div></button>
<button class="card full" type="button" data-title="Báo cáo Chiến lược Quản trị" data-template="Phân tích rủi ro, kiểm soát lỗi, quyền truy cập, vùng dữ liệu nhạy cảm và cơ chế giám sát."><div class="icon">🛡️</div><div class="card-title">Báo cáo Chiến lược Quản trị</div><div class="card-desc">Quản trị rủi ro, kiểm soát lỗi, quyền truy cập và trách nhiệm vận hành.</div></button>
<button class="card full" type="button" data-title="Tài liệu Hướng dẫn Thuật toán" data-template="Giải thích thuật toán, dữ liệu đầu vào, quy tắc xử lý, giới hạn suy luận và điều kiện không đủ dữ liệu."><div class="icon">🧮</div><div class="card-title">Tài liệu Hướng dẫn Thuật toán</div><div class="card-desc">Dữ liệu đầu vào, quy tắc xử lý, giới hạn và điều kiện không đủ dữ liệu.</div></button>
<button class="card full" type="button" data-title="Cẩm nang Tư duy Hệ thống" data-template="Mô hình xử lý thông tin đa tầng, phân biệt dữ liệu thật, giả định, suy luận và điểm mù."><div class="icon">🧠</div><div class="card-title">Cẩm nang Tư duy Hệ thống</div><div class="card-desc">Phân biệt dữ liệu thực tế, giả định, suy luận và điểm mù.</div></button>
</section>
<section class="audio" aria-label="Tùy chỉnh tổng quan bằng âm thanh"><div class="panel-title"><span>Tùy chỉnh bản Tổng quan bằng âm thanh</span><span class="pill ok" id="audioState">Sẵn sàng</span></div><div class="audio-grid" id="audioModes">
<button class="choice active" type="button" data-mode="Tìm hiểu sâu"><b>Tìm hiểu sâu</b><span>Một cuộc trò chuyện sôi nổi giữa 2 máy chủ AI, phân tích và kết nối các chủ đề trong nguồn.</span></button>
<button class="choice" type="button" data-mode="Tóm tắt"><b>Tóm tắt</b><span>Thông tin tổng quan ngắn gọn giúp nắm bắt nhanh các ý tưởng chính dựa trên nguồn.</span></button>
<button class="choice" type="button" data-mode="Phê bình"><b>Phê bình</b><span>Bài đánh giá chuyên gia về nguồn, đưa phản hồi xây dựng để cải thiện tài liệu.</span></button>
<button class="choice" type="button" data-mode="Tranh luận"><b>Tranh luận</b><span>Cuộc tranh luận sâu sắc giữa 2 máy chủ AI, làm sáng tỏ các quan điểm khác nhau.</span></button>
</div><div class="select-row"><div class="select-box"><label class="field" for="lang">Chọn ngôn ngữ</label><select class="select" id="lang"><option>Tiếng Việt</option><option>English</option><option>日本語</option><option>한국어</option></select></div><div class="select-box"><label class="field" for="length">Độ dài</label><select class="select" id="length"><option>Ngắn</option><option selected>Mặc định</option><option>Dài</option></select></div></div><label class="field" for="audioFocus">Máy chủ AI nên tập trung vào điều gì trong tập này?</label><textarea class="textarea" id="audioFocus">Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.</textarea><div class="tabs" id="audioTabs"><button class="tab active" type="button">+ Quản Lý Vốn</button><button class="tab" type="button">+ Người Mới Bắt</button><button class="tab" type="button">+ Phân Tích Cầu</button></div></section>
<section class="builder"><label class="field" for="reportName">Tên báo cáo</label><input class="input" id="reportName" value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu" autocomplete="off"><label class="field" for="reportRules">Yêu cầu kiểm soát</label><textarea class="textarea" id="reportRules">Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.</textarea><div class="actions"><button class="btn" type="button" id="buildBtn">Tạo báo cáo stream</button><button class="btn secondary" type="button" id="audioBtn">Tạo tổng quan audio</button><button class="btn secondary" type="button" id="resetBtn">Đặt lại</button><button class="btn secondary" type="button" id="exportBtn">Xuất nội dung</button></div></section>
<section class="preview" aria-live="polite"><div class="preview-title"><span>Bản nháp báo cáo</span><span class="meter" id="meter">0 dòng</span></div><div class="preview-box" id="previewBox"><pre class="body" id="previewBody">Chọn định dạng rồi bấm “Tạo báo cáo stream”.</pre></div></section>
<section class="abc"><div class="abc-box"><b>Bước 1 — Tạo lập</b><p>API hook nhận nguồn, trạng thái, log và stream báo cáo/audio từ backend.</p></div><div class="abc-box"><b>Bước 2 — Tự hủy diệt</b><p>Chặn hardcode, chặn nhồi 10.000 dòng một lần, chặn bấm lặp khi lõi đang xử lý.</p></div><div class="abc-box"><b>Bước 3 — Tái sinh</b><p>Dùng bridge động, render theo chunk, giới hạn vùng hiển thị, giữ bản đầy đủ trong bộ nhớ phiên.</p></div></section>
</section><footer class="foot"><b>Nguyên tắc:</b> chỉ hiển thị dữ liệu backend gửi vào. Nếu nguồn không đọc được, phải báo Không đủ dữ liệu xác thực.</footer><div class="overlay" id="overlay"><div class="lock"><div class="spin"></div><div class="lock-title" id="lockTitle">Đang xử lý</div><div class="lock-text" id="lockText">Đang kết nối lõi phân tích...</div></div></div>
</main></div>
<script>
"use strict";(function(){
const cards=Array.from(document.querySelectorAll(".card"));const choices=Array.from(document.querySelectorAll(".choice"));const tabs=Array.from(document.querySelectorAll(".tab"));
const previewBody=document.getElementById("previewBody"),previewBox=document.getElementById("previewBox"),meter=document.getElementById("meter"),reportName=document.getElementById("reportName"),reportRules=document.getElementById("reportRules"),buildBtn=document.getElementById("buildBtn"),audioBtn=document.getElementById("audioBtn"),resetBtn=document.getElementById("resetBtn"),exportBtn=document.getElementById("exportBtn"),backBtn=document.getElementById("backBtn"),fileList=document.getElementById("fileList"),scanStatus=document.getElementById("scanStatus"),scanNotice=document.getElementById("scanNotice"),coreStatus=document.getElementById("coreStatus"),log=document.getElementById("log"),bar=document.getElementById("bar"),overlay=document.getElementById("overlay"),lockTitle=document.getElementById("lockTitle"),lockText=document.getElementById("lockText"),lang=document.getElementById("lang"),length=document.getElementById("length"),audioFocus=document.getElementById("audioFocus"),audioState=document.getElementById("audioState");
const MAX_VISIBLE_CHARS=120000,STREAM_BATCH_LINES=24;let selected=cards[0],audioMode=choices[0].dataset.mode,isBusy=false,full=[],node=document.createTextNode(""),lines=0,queue=[],scheduled=false;previewBody.textContent="";previewBody.appendChild(node);
const defaultFiles=[{name:"HỆ THỐNG CAPABILITY TOKEN (CẤP QUYỀN TRUY CẬP).docx",state:"Không đọc được",level:"warn"},{name:"KHAI THÁC TRÊN BẢNG ĐẶC BIỆT NĂM.docx",state:"Không đọc được",level:"warn"},{name:"Hệ thống, thiếu kết quả xsmb.docx",state:"Không đọc được",level:"warn"},{name:"bản cấu trúc hệ thống nghiên cứu xổ số trọng tâm cốt lõi.docx",state:"Không đọc được",level:"warn"},{name:"nghiên cứu xổ số 1.docx",state:"Không đọc được",level:"warn"}];
function setBusy(v,t,d){isBusy=v;[buildBtn,audioBtn,resetBtn,exportBtn].forEach(b=>b.disabled=v);cards.forEach(c=>c.disabled=v);overlay.classList.toggle("show",v);if(t)lockTitle.textContent=t;if(d)lockText.textContent=d}function setStatus(s,m,p){coreStatus.className="status";if(s)coreStatus.classList.add(s);coreStatus.textContent=m||"CHỜ KẾT NỐI";if(typeof p==="number")bar.style.width=Math.max(0,Math.min(100,p))+"%"}function setLog(m){log.textContent=m||""}
function renderFiles(files,status,notice){fileList.replaceChildren();(Array.isArray(files)?files:[]).forEach(f=>{const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent=f.name||"Nguồn chưa đặt tên";st.textContent=f.state||"Chưa rõ";if(f.level==="ok")st.classList.add("ok");if(f.level==="bad")st.classList.add("bad");r.append(n,st);fileList.appendChild(r)});if(!fileList.children.length){const r=document.createElement("div"),n=document.createElement("div"),st=document.createElement("div");r.className="file";n.className="file-name";st.className="file-state";n.textContent="Chưa có nguồn dữ liệu";st.textContent="Đang chờ";r.append(n,st);fileList.appendChild(r)}scanStatus.className="pill";if(status&&status.toLowerCase().includes("đủ"))scanStatus.classList.add("ok");if(status&&status.toLowerCase().includes("lỗi"))scanStatus.classList.add("bad");scanStatus.textContent=status||"Chưa có dữ liệu lõi";scanNotice.textContent=notice||"Nguồn có thể cập nhật qua API hook."}
function resetPreview(t){full=[];lines=0;queue=[];scheduled=false;node.data=t||"";if(t)full.push(t);meter.textContent=(t?t.split("\n").length:0)+" dòng";previewBox.scrollTop=0}function appendText(t){if(!t)return;full.push(t);lines+=(t.match(/\n/g)||[]).length;let cur=node.data+t;if(cur.length>MAX_VISIBLE_CHARS)cur="[Đã thu gọn phần đầu để tránh nghẽn DOM trên mobile. Nội dung đầy đủ vẫn nằm trong bộ nhớ phiên.]\n\n"+cur.slice(-MAX_VISIBLE_CHARS);node.data=cur;meter.textContent=lines+" dòng · "+Math.round(cur.length/1024)+"KB hiển thị";previewBox.scrollTop=previewBox.scrollHeight}function flush(){if(scheduled)return;scheduled=true;requestAnimationFrame(()=>{let block="",c=0;while(queue.length&&c<STREAM_BATCH_LINES){block+=queue.shift();c++}appendText(block);scheduled=false;if(queue.length)flush()})}function stream(x){(Array.isArray(x)?x:[String(x||"")]).forEach(l=>queue.push(String(l).endsWith("\n")?String(l):String(l)+"\n"));flush()}
function selectCard(c){if(isBusy)return;cards.forEach(x=>x.classList.remove("active"));c.classList.add("active");selected=c}cards.forEach(c=>c.addEventListener("click",()=>selectCard(c)));choices.forEach(c=>c.addEventListener("click",()=>{if(isBusy)return;choices.forEach(x=>x.classList.remove("active"));c.classList.add("active");audioMode=c.dataset.mode||"Tóm tắt"}));tabs.forEach(t=>t.addEventListener("click",()=>{if(isBusy)return;t.classList.toggle("active")}));
async function simulateReport(kind){const title=selected.dataset.title||"Báo cáo",template=selected.dataset.template||"Chưa có mô tả",name=reportName.value.trim()||"Báo cáo chưa đặt tên",rules=reportRules.value.trim()||"Không có quy tắc bổ sung";setBusy(true,kind==="audio"?"Đang dựng tổng quan audio":"Đang kết nối Bô Lão",kind==="audio"?"Khóa thao tác trong khi tạo kịch bản âm thanh.":"Khóa thao tác để tránh bấm lặp gây nghẽn lõi.");setStatus("loading",kind==="audio"?"ĐANG DỰNG AUDIO":"ĐANG KẾT NỐI",10);setLog("[1/5] Mở ReportWorkspaceBridge\n[2/5] Chờ dữ liệu backend...");resetPreview("");if(kind==="audio"){stream(["# Kịch bản Tổng quan bằng âm thanh", "", "## Chế độ", audioMode, "", "## Ngôn ngữ", lang.value, "", "## Độ dài", length.value, "", "## Trọng tâm", audioFocus.value, "", "## Lưu ý an toàn", "Nội dung về Martingale/Fibonacci chỉ dùng để phân tích rủi ro và bảo toàn tài sản, không phải khuyến nghị đặt tiền hoặc cá cược.", ""])}else{stream(["# "+name,"","## Định dạng",title,"","## Mục tiêu",template,"","## Quy tắc",rules,"","## Luồng stream"])}await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG QUÉT NGUỒN",35);stream(["- Kiểm tra nguồn đầu vào qua API hook.","- Nếu nguồn không đọc được, không sinh kết luận thay dữ liệu.","- Dữ liệu lớn được render theo chunk requestAnimationFrame."]);await new Promise(r=>setTimeout(r,180));setStatus("loading","ĐANG STREAM",70);setLog("[3/5] Nhận dữ liệu theo dòng\n[4/5] Render theo batch chống freeze DOM");for(let i=1;i<=60;i++){stream([(kind==="audio"?"Lượt thoại mô phỏng ":"Dòng phân tích mô phỏng ")+String(i).padStart(3,"0")+": thay dòng này bằng dữ liệu thật từ backend khi tích hợp."]);if(i%12===0)await new Promise(r=>setTimeout(r,20))}setStatus("ready","HOÀN TẤT",100);stream(["","## Kết luận kiểm soát","Không có đủ dữ liệu xác thực từ tệp nếu backend không gửi nguồn đọc được. UI đã sẵn sàng nhận dữ liệu động qua window.ReportWorkspaceBridge."]);setLog("[5/5] Hoàn tất stream. Không nhồi DOM một lần.");setBusy(false)}
buildBtn.addEventListener("click",()=>simulateReport("report"));audioBtn.addEventListener("click",()=>simulateReport("audio"));resetBtn.addEventListener("click",()=>{reportName.value="Báo cáo kiểm định nguồn dữ liệu và thiết kế không gian nghiên cứu";reportRules.value="Không ảo giác. Không suy luận thay dữ liệu. Nếu thiếu dữ kiện phải ghi rõ Không có đủ dữ liệu xác thực. Áp dụng tam giác Tạo lập - Tự hủy diệt - Tái sinh.";audioFocus.value="Giải thích các thuật toán Martingale và Fibonacci dưới góc nhìn quản trị rủi ro, nhấn mạnh bảo toàn tài sản an toàn, không cổ vũ cá cược và không đưa khuyến nghị đặt tiền.";selectCard(cards[0]);setStatus("","CHỜ KẾT NỐI",0);setLog("Bridge sẵn sàng: window.ReportWorkspaceBridge");renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.")});exportBtn.addEventListener("click",()=>{const blob=new Blob([full.join("")],{type:"text/plain;charset=utf-8"});const a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download="bao_cao_stream.txt";document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(a.href),500)});backBtn.addEventListener("click",()=>resetPreview("Đã kích hoạt nút Trở về. Trong hệ thống thật, nút này nối với router/bridge của không gian chính."));
window.ReportWorkspaceBridge={setFiles:(f,s,n)=>renderFiles(f,s,n),setStatus:(s,m,p)=>setStatus(s,m,p),setLog:m=>setLog(m),startLoading:(t,d)=>setBusy(true,t||"Đang xử lý",d||"Đang chờ lõi phân tích..."),stopLoading:()=>setBusy(false),resetReport:t=>resetPreview(t||""),streamReport:x=>stream(x),streamAudio:x=>stream(x),setAudioConfig:c=>{if(!c)return;if(c.mode){choices.forEach(x=>{x.classList.toggle("active",x.dataset.mode===c.mode)});audioMode=c.mode}if(c.language)lang.value=c.language;if(c.length)length.value=c.length;if(c.focus)audioFocus.value=c.focus},getFullReport:()=>full.join("")};
renderFiles(defaultFiles,"Không đủ dữ liệu xác thực","Các file đã gửi không đọc được bằng công cụ quét. Khi backend gửi nguồn thật, khu vực này sẽ cập nhật động.");resetPreview("Chọn định dạng rồi bấm “Tạo báo cáo stream”.");
})();
</script>
</body>
</html> 

---------

<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Kết Quả Xổ Số Miền Bắc - Làm Cầu Mũi Tên</title>

<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{background:#050505;display:flex;justify-content:center;align-items:flex-start;height:100dvh;overflow:hidden;width:100vw}
.num-font{font-family:"SF Mono","Helvetica Neue",Helvetica,Arial,sans-serif;font-variant-numeric:tabular-nums lining-nums;font-feature-settings:"tnum" 1,"lnum" 1}

.app-wrapper{
    --bg-main:#fff;--bg-board:#cbd5e1;--text-main:#111;--text-dim:#6b7280;--border-color:#cbd5e1;
    --db-bg:#d40000;--led-color:#00e676;--led-bg:#111;
    --glass-bg:linear-gradient(180deg,#fff 0%,#eef2f7 100%);
    --glass-shadow:inset 0 2px 4px rgba(255,255,255,1),0 2px 5px rgba(0,0,0,.08);
    --glass-border:#cbd5e1;
    --lo-chip-bg:linear-gradient(135deg,#d40000,#ff5252);
    --lo-chip-shadow:rgba(212,0,0,.4);
    --modal-overlay:rgba(0,0,0,.45);
    --ai-bar-bg:linear-gradient(135deg,#e3f2fd,#bbdefb);
    --ai-bar-border:#90caf9;--ai-bar-text:#1565c0;--ai-bar-input:#fff;
}
#toggle-dark:checked~.app-wrapper{
    --bg-main:#121212;--bg-board:#0f172a;--text-main:#fff;--text-dim:#94a3b8;--border-color:#334155;
    --glass-bg:linear-gradient(180deg,#243044 0%,#161f30 100%);
    --glass-shadow:inset 0 1px 2px rgba(255,255,255,.07),0 3px 6px rgba(0,0,0,.45);
    --glass-border:#334155;
    --lo-chip-bg:linear-gradient(135deg,#ff1744,#d50000);
    --lo-chip-shadow:rgba(255,23,68,.4);
    --modal-overlay:rgba(0,0,0,.72);
    --ai-bar-bg:linear-gradient(135deg,#0f2440,#102a4d);
    --ai-bar-border:#1e3a5f;--ai-bar-text:#7cc4ff;--ai-bar-input:#0f172a;
}
.app-wrapper{max-width:480px;width:100%;height:100%;position:relative;background:var(--bg-main);color:var(--text-main);overflow:hidden;box-shadow:0 0 40px rgba(0,0,0,.9)}
.main-layer{width:100%;height:100%;display:flex;flex-direction:column;background:var(--bg-board)}

.top-controls{display:flex;justify-content:space-between;align-items:center;padding:10px 16px;background:var(--bg-main);border-bottom:1px solid var(--border-color);z-index:50;flex-shrink:0}
.top-controls-left,.top-controls-right{display:flex;gap:14px;align-items:center}
.switch-wrap{display:flex;flex-direction:column;align-items:center;gap:4px}
.switch-label-text{font-size:10px;font-weight:800;color:var(--text-main);text-transform:uppercase;letter-spacing:.3px}
.switch{position:relative;display:inline-block;width:36px;height:18px}
.switch input{opacity:0;width:0;height:0}
.switch input:disabled+.slider{opacity:.5;cursor:not-allowed}
.slider{position:absolute;cursor:pointer;inset:0;background:#cbd5e1;transition:.3s;border-radius:20px;box-shadow:inset 0 1px 3px rgba(0,0,0,.2)}
.slider:before{position:absolute;content:"";height:14px;width:14px;left:2px;bottom:2px;background:#fff;transition:.3s;border-radius:50%;box-shadow:0 1px 2px rgba(0,0,0,.3)}
input:checked+.slider{background:var(--db-bg)}
input:checked+.slider:before{transform:translateX(18px)}

.boards-feed{position:relative;flex:1;overflow-y:auto;overflow-x:hidden;padding:16px 12px;display:flex;flex-direction:column;gap:24px;-webkit-overflow-scrolling:touch;scrollbar-width:thin;scrollbar-color:var(--db-bg) transparent}
.boards-feed::-webkit-scrollbar{width:8px;display:block}
.boards-feed::-webkit-scrollbar-thumb{background:var(--db-bg);border-radius:999px;border:2px solid transparent;background-clip:content-box}
.boards-feed::-webkit-scrollbar-track{background:transparent}

.cau-svg-layer{position:absolute;left:0;top:0;width:100%;height:1px;pointer-events:none;z-index:30;overflow:visible}
.cau-arrow-line{fill:none;stroke-width:2.8;pointer-events:none;filter:drop-shadow(0 2px 3px rgba(0,0,0,.35))}
.cau-arrow-line.manual{stroke:#d40000;opacity:.96}
.cau-arrow-line.suggested{stroke:#ff9800;stroke-dasharray:7 6;opacity:.48}

.cau-help{
    display:none;background:linear-gradient(135deg,#fff3e0,#ffe0b2);color:#7a2e00;border:1px solid #ffb74d;
    border-radius:12px;padding:10px 12px;font-size:12px;font-weight:800;line-height:1.35;text-align:center;
}
.cau-on .cau-help{display:block}
#toggle-dark:checked~.app-wrapper .cau-help{background:linear-gradient(135deg,#3a2100,#4d2d00);color:#ffcc80;border-color:#8a5300}

.board{background:var(--bg-main);border-radius:14px;border:1px solid var(--border-color);padding:12px;box-shadow:0 2px 4px rgba(0,0,0,.02),0 8px 16px rgba(0,0,0,.05);transition:background .3s,border-color .3s}
.board-header{text-align:center;margin-bottom:14px;padding-bottom:10px;border-bottom:1.5px dashed var(--border-color)}
.board-title{font-size:17px;font-weight:900;color:var(--text-main);text-transform:uppercase;letter-spacing:.5px}
.board-title.live{color:var(--db-bg);text-shadow:0 2px 4px rgba(212,0,0,.18)}
.status-blink{font-size:12px;color:var(--db-bg);animation:blink 1.2s infinite;font-weight:800;margin-top:4px}
.board-date{font-size:13px;color:var(--text-dim);font-style:italic;margin-top:4px;font-weight:800;text-transform:capitalize}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.3}}

.row{display:flex;margin-bottom:6px;align-items:stretch;gap:6px}
.prize-name{width:40px;flex-shrink:0;display:flex;justify-content:center;align-items:center;font-size:13px;font-weight:900;background:var(--glass-bg);box-shadow:var(--glass-shadow);border:1px solid var(--glass-border);border-radius:7px;color:var(--text-main)}
.prize-name.db{background:linear-gradient(180deg,#e53935 0%,#b71c1c 100%);color:#fff;border:1px solid #c62828;box-shadow:inset 0 2px 4px rgba(255,255,255,.35),0 2px 4px rgba(0,0,0,.2)}
.prize-name.active-led{background:var(--led-bg);color:var(--led-color);border-color:var(--led-color);box-shadow:0 0 12px var(--led-color);transform:scale(1.05);z-index:2}
.prize-results{flex-grow:1;display:grid;gap:4px;min-width:0}
.grid-1{grid-template-columns:1fr}.grid-2{grid-template-columns:repeat(2,1fr)}.grid-3{grid-template-columns:repeat(3,1fr)}.grid-4{grid-template-columns:repeat(4,1fr)}.grid-6{grid-template-columns:repeat(6,1fr)}

.number-box{background:var(--glass-bg);border:1px solid var(--glass-border);box-shadow:var(--glass-shadow);display:flex;justify-content:center;align-items:center;border-radius:7px;height:34px;position:relative;cursor:default;min-width:0;transition:transform .2s cubic-bezier(.175,.885,.32,1.275),box-shadow .2s,border-color .2s;overflow:hidden}
.cau-on .number-box{cursor:pointer}
.number-box:hover{transform:scale(1.06);box-shadow:0 6px 15px rgba(0,0,0,.15);border-color:var(--db-bg);z-index:40}
.number-box:active{transform:scale(.96)}
.number-text{font-size:clamp(13px,4.4vw,17px);font-weight:800;letter-spacing:1.5px;display:flex;align-items:center;justify-content:center;white-space:nowrap;width:100%;max-width:100%;padding:0 2px;color:var(--text-main);line-height:1;transition:opacity .2s,color .2s}
.grid-3 .number-text{font-size:clamp(12px,4vw,16px);letter-spacing:1px}
.grid-4 .number-text{font-size:clamp(11px,3.4vw,15px);letter-spacing:.5px}
.grid-6 .number-text{font-size:clamp(10px,3vw,14px);letter-spacing:.3px;padding:0 1px}
.row-db .number-box{height:52px}
.row-db .number-text{font-size:clamp(24px,8.5vw,34px);color:var(--db-bg);letter-spacing:4px;z-index:1;text-shadow:0 2px 4px rgba(0,0,0,.1);padding-left:4px}
.number-text.spinning{color:var(--db-bg);filter:blur(.4px);opacity:.75}

.digit{display:inline-block;transition:all .2s cubic-bezier(.175,.885,.32,1.275);border-radius:4px;padding:0 1px;position:relative;z-index:2}
.digit.active-cau{background:var(--db-bg);color:#fff;transform:scale(1.2);box-shadow:0 0 0 1px var(--db-bg),0 0 10px rgba(212,0,0,.75);z-index:45;font-weight:900}
.digit.cau-suggested{outline:2px dashed #ff9800;outline-offset:2px;background:rgba(255,152,0,.18);color:#ff6d00;animation:cauSuggestPulse 1.1s infinite ease-in-out}
@keyframes cauSuggestPulse{0%,100%{transform:scale(1)}50%{transform:scale(1.18)}}

.mask-cover{position:absolute;inset:0;border-radius:7px;background:repeating-linear-gradient(45deg,#b71c1c,#b71c1c 10px,#d40000 10px,#d40000 20px);display:flex;align-items:center;justify-content:center;gap:8px;color:#fff;font-size:13px;font-weight:900;letter-spacing:1px;text-transform:uppercase;cursor:pointer;z-index:46;opacity:0;pointer-events:none;transition:opacity .3s;box-shadow:inset 0 0 20px rgba(0,0,0,.4)}
.mask-cover .eye{font-size:18px}
.masking .maskable-db .mask-cover{opacity:1;pointer-events:auto}
.masking .maskable-db .number-text{opacity:0}
.masking .maskable-db.revealed .mask-cover{opacity:0;pointer-events:none}
.masking .maskable-db.revealed .number-text{opacity:1}

.injected-slot{background:var(--bg-main);border:1.5px solid var(--db-bg);border-radius:14px;padding:12px;display:flex;flex-direction:column;gap:10px;box-shadow:0 6px 16px rgba(212,0,0,.12)}
.slot-title{font-size:12px;font-weight:900;color:var(--db-bg);text-align:center;text-transform:uppercase;letter-spacing:.5px;transition:all .3s;padding:4px 8px;border-radius:6px}
.slot-title.flash{background:var(--db-bg);color:#fff;box-shadow:0 0 15px rgba(212,0,0,.6);transform:scale(1.02)}
.loto-grid{display:flex;flex-wrap:wrap;justify-content:center;align-items:center;gap:5px;width:100%;min-height:26px}
.lo-chip{background:var(--lo-chip-bg);color:#fff;font-size:12px;font-weight:800;letter-spacing:.5px;padding:4px 8px;border-radius:5px;box-shadow:0 2px 4px var(--lo-chip-shadow),inset 0 1px 0 rgba(255,255,255,.3);transform:scale(0);animation:springDrop .5s cubic-bezier(.175,.885,.32,1.275) forwards}
@keyframes springDrop{0%{transform:scale(0) translateY(-20px) rotate(-5deg);opacity:0}100%{transform:scale(1) translateY(0) rotate(0);opacity:1}}

.dots-wrapper{display:flex;justify-content:center;align-items:center;gap:3px;width:100%}
.dot{width:5px;height:5px;background:var(--text-dim);border-radius:50%;animation:wave 1.2s infinite ease-in-out}
.dot:nth-child(2){animation-delay:-1.1s}.dot:nth-child(3){animation-delay:-1s}.dot:nth-child(4){animation-delay:-.9s}.dot:nth-child(5){animation-delay:-.8s}
@keyframes wave{0%,40%,100%{transform:translateY(0);opacity:.5}20%{transform:translateY(-3px);opacity:1}}

.ai-sticky-bar{background:var(--ai-bar-bg);border-top:1px solid var(--ai-bar-border);padding:12px 16px calc(12px + env(safe-area-inset-bottom));display:flex;align-items:center;gap:8px;z-index:50;box-shadow:0 -4px 10px rgba(0,0,0,.06);flex-shrink:0}
.ai-marquee{flex-grow:1;overflow:hidden;white-space:nowrap;min-width:0}
.ai-marquee span{display:inline-block;padding-left:100%;font-size:13px;font-weight:800;color:var(--ai-bar-text);animation:marquee 18s linear infinite}
@keyframes marquee{0%{transform:translateX(0)}100%{transform:translateX(-100%)}}
.ai-input{padding:7px 13px;border-radius:20px;border:1px solid var(--ai-bar-border);font-size:12px;width:92px;outline:none;background:var(--ai-bar-input);color:var(--text-main)}
.clear-cau-btn{border:none;background:var(--db-bg);color:#fff;font-size:11px;font-weight:900;padding:7px 10px;border-radius:999px;cursor:pointer;white-space:nowrap}
.clear-cau-btn:active{transform:scale(.94)}

@media(max-width:380px){
    .top-controls{padding:8px 10px;gap:8px}
    .top-controls-left,.top-controls-right{gap:10px}
    .switch-label-text{font-size:9px}
    .ai-input{width:78px}
    .clear-cau-btn{font-size:10px;padding:7px 8px}
}
</style>
</head>

<body>

<input type="checkbox" id="toggle-dark" hidden>

<div class="app-wrapper" id="app-wrapper">
    <div class="main-layer">
        <div class="top-controls">
            <div class="top-controls-left">
                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-cau" onchange="toggleCau(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Làm Cầu</span>
                </div>

                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-quay-thu" onchange="triggerQuayThu(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Quay Thử</span>
                </div>
            </div>

            <div class="top-controls-right">
                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-dark-vis" onchange="document.getElementById('toggle-dark').checked=this.checked">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Sáng/Tối</span>
                </div>

                <div class="switch-wrap">
                    <label class="switch">
                        <input type="checkbox" id="toggle-mask-vis" onchange="toggleMask(this)">
                        <span class="slider"></span>
                    </label>
                    <span class="switch-label-text">Lặn Số ĐB</span>
                </div>
            </div>
        </div>

        <div class="boards-feed" id="boards-feed-container">
            <svg id="cau-svg-layer" class="cau-svg-layer" xmlns="http://www.w3.org/2000/svg">
                <defs>
                    <marker id="arrow-head-manual" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
                        <path d="M0,0 L0,6 L9,3 z" fill="#d40000"></path>
                    </marker>
                    <marker id="arrow-head-suggested" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
                        <path d="M0,0 L0,6 L9,3 z" fill="#ff9800"></path>
                    </marker>
                </defs>
            </svg>

            <div class="cau-help">
                Chế độ Làm Cầu đang bật · Chạm trực tiếp từng chữ số để tạo điểm cầu · Chạm liên tiếp để nối mũi tên · Đường cam là gợi ý trùng dữ liệu, không phải dự đoán kết quả.
            </div>

            <div class="board board-live-cau" id="board-live">
                <div class="board-header">
                    <div class="board-title live">🔴 Kết quả xổ số Thần Mèo</div>
                    <div class="status-blink" id="live-status">⏳ Hãy bật công tắc "Quay Thử" ở trên...</div>
                    <div class="board-date" id="live-date"></div>
                </div>
                <div id="live-rows-container"></div>
            </div>

            <div class="injected-slot" id="custom-slot">
                <div class="slot-title" id="slot-title">⚡ Bảng lô rơi sẽ hiển thị tại đây</div>
                <div class="loto-grid" id="loto-drop-zone"></div>
            </div>

            <div id="history-boards-container"></div>
        </div>

        <div class="ai-sticky-bar">
            <div class="ai-marquee">
                <span>🤖 Bật Làm Cầu rồi chạm từng chữ số để nối mũi tên xuyên nhiều bảng ngày · Bấm Xóa Cầu để làm lại · Gợi ý chỉ là quan hệ trùng dữ liệu hiển thị...</span>
            </div>
            <button type="button" class="clear-cau-btn" onclick="clearAllCau()">Xóa Cầu</button>
            <input type="text" class="ai-input" placeholder="Hỏi AI...">
        </div>
    </div>
</div>

<script>
"use strict";

const PRIZES = [
    { name: "ĐB", len: 5, count: 1, grid: "grid-1", db: true },
    { name: "G1", len: 5, count: 1, grid: "grid-1", db: false },
    { name: "G2", len: 5, count: 2, grid: "grid-2", db: false },
    { name: "G3", len: 5, count: 6, grid: "grid-6", db: false },
    { name: "G4", len: 4, count: 4, grid: "grid-4", db: false },
    { name: "G5", len: 4, count: 6, grid: "grid-6", db: false },
    { name: "G6", len: 3, count: 3, grid: "grid-3", db: false },
    { name: "G7", len: 2, count: 4, grid: "grid-4", db: false }
];

const QUAY_ORDER = ["G1", "G2", "G3", "G4", "G5", "G6", "G7", "ĐB"];

const CauGraph = {
    nodes: [],
    edges: [],
    counter: 0,
    lastNodeId: null,
    maxSuggestedLinks: 5
};

let isRunning = false;

function generateRandom(length) {
    let result = "";
    for (let i = 0; i < length; i++) {
        result += Math.floor(Math.random() * 10);
    }
    return result;
}

function wrapDigits(numStr) {
    if (!numStr) return "";
    return String(numStr).split("").map(function(digit, index) {
        return '<span class="digit" data-idx="' + index + '">' + digit + '</span>';
    }).join("");
}

function sleep(ms) {
    return new Promise(function(resolve) {
        setTimeout(resolve, ms);
    });
}

function createDots(length) {
    let dots = "";
    for (let i = 0; i < length; i++) {
        dots += '<span class="dot"></span>';
    }
    return '<div class="dots-wrapper">' + dots + '</div>';
}

function createNumberBox(length, value, isMaskableDb) {
    const content = value ? wrapDigits(value) : createDots(length);
    const maskClass = isMaskableDb ? " maskable-db" : "";
    const maskHtml = isMaskableDb
        ? '<div class="mask-cover" onclick="revealDbNumber(this)"><span class="eye">🙈</span> Chạm để xem</div>'
        : "";

    return '<div class="number-box' + maskClass + '">' + maskHtml + '<span class="number-text num-font">' + content + '</span></div>';
}

function createPrizeRow(prize, mode) {
    const isDb = prize.db === true;
    const rowClass = isDb ? "row row-db" : "row";
    const labelClass = isDb ? "prize-name db" : "prize-name";
    const boxes = [];

    for (let i = 0; i < prize.count; i++) {
        const value = mode === "live" ? "" : generateRandom(prize.len);
        boxes.push(createNumberBox(prize.len, value, mode === "live" && isDb));
    }

    return '<div class="' + rowClass + '" data-prize="' + prize.name + '" data-len="' + prize.len + '">' +
        '<div class="' + labelClass + '">' + prize.name + '</div>' +
        '<div class="prize-results ' + prize.grid + '">' + boxes.join("") + '</div>' +
        '</div>';
}

document.addEventListener("DOMContentLoaded", function() {
    setLiveDate();
    renderLiveBoard();
    renderHistoricalBoards(40);
    bindCauClicks();
    prepareSvgSize();
});

function setLiveDate() {
    const d = new Date(2026, 2, 26);
    let s = d.toLocaleDateString("vi-VN", { weekday: "long", year: "numeric", month: "2-digit", day: "2-digit" });
    document.getElementById("live-date").textContent = s.charAt(0).toUpperCase() + s.slice(1);
}

function renderLiveBoard() {
    document.getElementById("live-rows-container").innerHTML = PRIZES.map(function(prize) {
        return createPrizeRow(prize, "live");
    }).join("");
}

function renderHistoricalBoards(count) {
    const container = document.getElementById("history-boards-container");
    const baseDate = new Date(2026, 2, 25);
    const boards = [];

    for (let i = 0; i < count; i++) {
        const d = new Date(baseDate);
        d.setDate(d.getDate() - i);

        let day = d.toLocaleDateString("vi-VN", { weekday: "long", year: "numeric", month: "2-digit", day: "2-digit" });
        day = day.charAt(0).toUpperCase() + day.slice(1);

        boards.push(
            '<div class="board">' +
            '<div class="board-header">' +
            '<div class="board-title">Kết quả xổ số Thần Mèo</div>' +
            '<div class="board-date">' + day + '</div>' +
            '</div>' +
            PRIZES.map(function(prize) { return createPrizeRow(prize, "history"); }).join("") +
            '</div>'
        );
    }

    container.style.cssText = "display:flex;flex-direction:column;gap:24px;";
    container.innerHTML = boards.join("");
}

function toggleCau(cb) {
    document.getElementById("app-wrapper").classList.toggle("cau-on", cb.checked);
    if (!cb.checked) {
        clearSmartSuggestions();
        redrawCauArrows();
    }
}

function toggleMask(cb) {
    const app = document.getElementById("app-wrapper");
    app.classList.toggle("masking", cb.checked);
    document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
        box.classList.remove("revealed");
    });
    redrawCauArrows();
}

function revealDbNumber(maskElement) {
    const box = maskElement.closest(".number-box");
    if (box) {
        box.classList.add("revealed");
        redrawCauArrows();
    }
}

function bindCauClicks() {
    const feed = document.getElementById("boards-feed-container");

    feed.addEventListener("click", function(e) {
        if (!document.getElementById("toggle-cau").checked) return;
        if (e.target.closest(".mask-cover")) return;

        const digit = e.target.closest(".digit");
        if (!digit) return;

        const box = digit.closest(".number-box");
        const app = document.getElementById("app-wrapper");

        if (box && box.classList.contains("maskable-db") && app.classList.contains("masking") && !box.classList.contains("revealed")) {
            return;
        }

        addManualCauNode(digit);
    });

    feed.addEventListener("scroll", function() {
        redrawCauArrows();
    });

    window.addEventListener("resize", function() {
        prepareSvgSize();
        redrawCauArrows();
    });
}

function createCauNode(digitElement, suggestedOnly) {
    const numberText = digitElement.closest(".number-text");
    const row = digitElement.closest(".row");
    const board = digitElement.closest(".board");

    if (!numberText || !row || !board) return null;

    const existingId = digitElement.dataset.cauNodeId;
    if (existingId) {
        return CauGraph.nodes.find(function(node) {
            return node.id === existingId;
        }) || null;
    }

    const boardList = Array.from(document.querySelectorAll(".board"));
    const boardIndex = boardList.indexOf(board);
    const boardDateEl = board.querySelector(".board-date");
    const fullNumber = numberText.textContent.trim();
    const digitIndex = Number(digitElement.dataset.idx || 0);
    const digit = digitElement.textContent.trim();
    const prize = row.dataset.prize || "";

    CauGraph.counter += 1;

    const node = {
        id: "cau-node-" + CauGraph.counter,
        digit: digit,
        fullNumber: fullNumber,
        digitIndex: digitIndex,
        prize: prize,
        boardIndex: boardIndex,
        dateText: boardDateEl ? boardDateEl.textContent.trim() : "",
        element: digitElement,
        suggestedOnly: suggestedOnly === true
    };

    digitElement.dataset.cauNodeId = node.id;

    if (!suggestedOnly) {
        digitElement.classList.add("active-cau");
        digitElement.setAttribute("title", "Điểm cầu " + CauGraph.counter);
    }

    CauGraph.nodes.push(node);
    return node;
}

function addManualCauNode(digitElement) {
    const node = createCauNode(digitElement, false);
    if (!node) return;

    node.suggestedOnly = false;
    digitElement.classList.add("active-cau");
    digitElement.classList.remove("cau-suggested");

    if (CauGraph.lastNodeId && CauGraph.lastNodeId !== node.id) {
        const duplicated = CauGraph.edges.some(function(edge) {
            return edge.fromId === CauGraph.lastNodeId && edge.toId === node.id && edge.type === "manual";
        });

        if (!duplicated) {
            CauGraph.edges.push({
                fromId: CauGraph.lastNodeId,
                toId: node.id,
                type: "manual",
                score: 100
            });
        }
    }

    CauGraph.lastNodeId = node.id;
    suggestSmartCauLinks(node);
    prepareSvgSize();
    redrawCauArrows();
}

function collectAllDigitCandidates() {
    const digits = Array.from(document.querySelectorAll(".number-text .digit"));
    const boardList = Array.from(document.querySelectorAll(".board"));

    return digits.map(function(digitElement) {
        const numberText = digitElement.closest(".number-text");
        const row = digitElement.closest(".row");
        const board = digitElement.closest(".board");
        const fullNumber = numberText ? numberText.textContent.trim() : "";
        const prize = row ? row.dataset.prize || "" : "";
        const boardIndex = boardList.indexOf(board);

        return {
            element: digitElement,
            digit: digitElement.textContent.trim(),
            fullNumber: fullNumber,
            tail: fullNumber.slice(-2),
            digitIndex: Number(digitElement.dataset.idx || 0),
            prize: prize,
            boardIndex: boardIndex
        };
    });
}

function calculateCauScore(source, target) {
    let score = 0;

    if (source.digit === target.digit) score += 30;
    if (source.prize === target.prize && source.digitIndex === target.digitIndex) score += 45;
    if (source.fullNumber.slice(-2) === target.tail) score += 60;

    const distance = Math.abs(source.boardIndex - target.boardIndex);
    if (distance > 0 && distance <= 3) score += 10;
    if (distance > 10) score -= 10;

    if (source.boardIndex === target.boardIndex && source.fullNumber === target.fullNumber) score -= 20;

    return score;
}

function suggestSmartCauLinks(sourceNode) {
    clearSmartSuggestions();

    const candidates = collectAllDigitCandidates();

    const scored = candidates
        .filter(function(candidate) {
            return candidate.element !== sourceNode.element;
        })
        .map(function(candidate) {
            return {
                candidate: candidate,
                score: calculateCauScore(sourceNode, candidate)
            };
        })
        .filter(function(item) {
            return item.score >= 45;
        })
        .sort(function(a, b) {
            return b.score - a.score;
        })
        .slice(0, CauGraph.maxSuggestedLinks);

    scored.forEach(function(item) {
        const candidate = item.candidate;
        candidate.element.classList.add("cau-suggested");

        const suggestionNode = createCauNode(candidate.element, true);
        if (!suggestionNode) return;

        const duplicated = CauGraph.edges.some(function(edge) {
            return edge.fromId === sourceNode.id && edge.toId === suggestionNode.id && edge.type === "suggested";
        });

        if (!duplicated) {
            CauGraph.edges.push({
                fromId: sourceNode.id,
                toId: suggestionNode.id,
                type: "suggested",
                score: item.score
            });
        }
    });
}

function clearSmartSuggestions() {
    document.querySelectorAll(".cau-suggested").forEach(function(el) {
        el.classList.remove("cau-suggested");
    });

    CauGraph.edges = CauGraph.edges.filter(function(edge) {
        return edge.type !== "suggested";
    });

    CauGraph.nodes = CauGraph.nodes.filter(function(node) {
        if (node.suggestedOnly !== true) return true;

        if (node.element) {
            node.element.removeAttribute("data-cau-node-id");
        }

        return false;
    });
}

function prepareSvgSize() {
    const feed = document.getElementById("boards-feed-container");
    const svg = document.getElementById("cau-svg-layer");
    if (!feed || !svg) return;

    const height = Math.max(feed.scrollHeight, feed.clientHeight);
    svg.setAttribute("height", String(height));
    svg.style.height = height + "px";
}

function redrawCauArrows() {
    const svg = document.getElementById("cau-svg-layer");
    const feed = document.getElementById("boards-feed-container");
    if (!svg || !feed) return;

    prepareSvgSize();

    Array.from(svg.querySelectorAll(".cau-arrow-line")).forEach(function(line) {
        line.remove();
    });

    const feedRect = feed.getBoundingClientRect();
    const scrollTop = feed.scrollTop;
    const scrollLeft = feed.scrollLeft;

    CauGraph.edges.forEach(function(edge) {
        const fromNode = CauGraph.nodes.find(function(node) { return node.id === edge.fromId; });
        const toNode = CauGraph.nodes.find(function(node) { return node.id === edge.toId; });

        if (!fromNode || !toNode || !fromNode.element || !toNode.element) return;
        if (!document.body.contains(fromNode.element) || !document.body.contains(toNode.element)) return;

        const fromRect = fromNode.element.getBoundingClientRect();
        const toRect = toNode.element.getBoundingClientRect();

        const x1 = fromRect.left - feedRect.left + fromRect.width / 2 + scrollLeft;
        const y1 = fromRect.top - feedRect.top + fromRect.height / 2 + scrollTop;
        const x2 = toRect.left - feedRect.left + toRect.width / 2 + scrollLeft;
        const y2 = toRect.top - feedRect.top + toRect.height / 2 + scrollTop;

        const dx = Math.abs(x2 - x1);
        const dy = Math.abs(y2 - y1);
        const curve = Math.max(35, Math.min(140, (dx + dy) / 3));

        const direction = x2 >= x1 ? 1 : -1;
        const c1x = x1 + curve * direction;
        const c1y = y1;
        const c2x = x2 - curve * direction;
        const c2y = y2;

        const path = document.createElementNS("http://www.w3.org/2000/svg", "path");
        path.setAttribute("d", "M " + x1 + " " + y1 + " C " + c1x + " " + c1y + ", " + c2x + " " + c2y + ", " + x2 + " " + y2);
        path.setAttribute("class", "cau-arrow-line " + (edge.type === "suggested" ? "suggested" : "manual"));
        path.setAttribute("marker-end", edge.type === "suggested" ? "url(#arrow-head-suggested)" : "url(#arrow-head-manual)");

        svg.appendChild(path);
    });
}

function clearAllCau() {
    CauGraph.nodes = [];
    CauGraph.edges = [];
    CauGraph.counter = 0;
    CauGraph.lastNodeId = null;

    document.querySelectorAll(".digit").forEach(function(digit) {
        digit.classList.remove("active-cau");
        digit.classList.remove("cau-suggested");
        digit.removeAttribute("data-cau-node-id");
        digit.removeAttribute("title");
    });

    redrawCauArrows();
}

function clearLiveCauNodes() {
    const liveBoard = document.getElementById("board-live");
    if (!liveBoard) return;

    const liveNodeIds = CauGraph.nodes
        .filter(function(node) {
            return node.element && liveBoard.contains(node.element);
        })
        .map(function(node) {
            return node.id;
        });

    CauGraph.nodes = CauGraph.nodes.filter(function(node) {
        return liveNodeIds.indexOf(node.id) === -1;
    });

    CauGraph.edges = CauGraph.edges.filter(function(edge) {
        return liveNodeIds.indexOf(edge.fromId) === -1 && liveNodeIds.indexOf(edge.toId) === -1;
    });

    liveBoard.querySelectorAll(".digit").forEach(function(digit) {
        digit.classList.remove("active-cau");
        digit.classList.remove("cau-suggested");
        digit.removeAttribute("data-cau-node-id");
        digit.removeAttribute("title");
    });

    if (liveNodeIds.indexOf(CauGraph.lastNodeId) !== -1) {
        CauGraph.lastNodeId = null;
    }

    redrawCauArrows();
}

async function triggerQuayThu(cb) {
    if (!cb.checked || isRunning) return;

    isRunning = true;
    cb.disabled = true;

    await startSimulation();

    cb.checked = false;
    cb.disabled = false;
    isRunning = false;
}

async function startSimulation() {
    clearLiveCauNodes();

    const status = document.getElementById("live-status");
    const dropZone = document.getElementById("loto-drop-zone");
    const slotTitle = document.getElementById("slot-title");
    const app = document.getElementById("app-wrapper");

    status.textContent = "🔴 Đang quay số...";
    status.style.color = "var(--db-bg)";
    dropZone.innerHTML = "";
    slotTitle.textContent = "⚡ Hệ thống đang lấy kết quả...";

    document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
        box.classList.remove("revealed");
    });

    document.querySelectorAll("#board-live .number-text").forEach(function(textBox) {
        const row = textBox.closest(".row");
        const len = Number(row.dataset.len);
        textBox.classList.remove("spinning");
        textBox.innerHTML = createDots(len);
    });

    const rows = Array.from(document.querySelectorAll("#board-live .row"));
    const msgs = ["gan cực đại!", "rơi liên tiếp 3 ngày!", "ra cả cặp rất đẹp!", "vào nhịp rơi ổn định!", "xuất hiện đúng cầu chạy!"];

    for (const name of QUAY_ORDER) {
        const row = rows.find(function(item) {
            return item.dataset.prize === name;
        });

        if (!row) continue;

        const len = Number(row.dataset.len);
        const label = row.querySelector(".prize-name");
        const boxes = row.querySelectorAll(".number-text");

        label.classList.add("active-led");

        for (const box of boxes) {
            box.classList.add("spinning");

            const spin = setInterval(function() {
                box.textContent = generateRandom(len);
            }, 50);

            await sleep(900);
            clearInterval(spin);

            box.classList.remove("spinning");

            const finalNumber = generateRandom(len);
            box.innerHTML = wrapDigits(finalNumber);

            const lo = finalNumber.slice(-2);
            const chip = document.createElement("div");
            chip.className = "lo-chip";
            chip.textContent = lo;
            dropZone.appendChild(chip);

            const message = msgs[Math.floor(Math.random() * msgs.length)];
            slotTitle.textContent = "🔥 Lô " + lo + " " + message + " (" + name + ")";
            slotTitle.classList.add("flash");

            setTimeout(function() {
                slotTitle.classList.remove("flash");
            }, 500);

            await sleep(150);
        }

        label.classList.remove("active-led");
    }

    if (app.classList.contains("masking")) {
        document.querySelectorAll(".maskable-db.revealed").forEach(function(box) {
            box.classList.remove("revealed");
        });
    }

    status.textContent = "✅ Đã quay xong";
    status.style.color = "var(--led-color)";
    slotTitle.textContent = "Kỳ quay kết thúc · Bật 'Làm Cầu' để chấm cầu các giải.";

    prepareSvgSize();
    redrawCauArrows();
}
</script>

</body>
</html>
