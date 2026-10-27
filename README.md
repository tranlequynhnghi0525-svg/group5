<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kho Tài Liệu Nhóm</title>
<style>
:root{--g9:#14532d;--g7:#15803d;--g5:#22c55e;--g2:#bbf7d0;--g1:#dcfce7;--g0:#f0fdf4;--sh:0 4px 14px rgba(21,128,61,.15)}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:"Segoe UI",Arial,sans-serif;background:var(--g0);color:#1f2937;line-height:1.5}
.hero{background:linear-gradient(135deg,var(--g9),var(--g7) 60%,var(--g5));color:#fff;text-align:center;padding:56px 20px}
.hero h1{font-size:2.2rem;margin-bottom:8px}
main{max-width:1100px;margin:0 auto;padding:20px 20px 60px}
.st{color:var(--g9);font-size:1.5rem;margin:32px 0 18px;padding-left:12px;border-left:5px solid var(--g5)}
.mg{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.mc{background:#fff;border-radius:16px;padding:22px 14px;text-align:center;cursor:pointer;box-shadow:var(--sh);border-top:5px solid var(--g5);transition:.2s}
.mc:hover{transform:translateY(-5px);background:var(--g1)}
.mc h3{color:var(--g9);font-size:1.05rem;margin:10px 0 4px}
.role{display:inline-block;background:var(--g1);color:var(--g7);font-size:.8rem;padding:2px 10px;border-radius:99px}
.more{display:block;margin-top:10px;font-size:.85rem;color:var(--g7);font-weight:600}
.av{position:relative;width:84px;height:84px;border-radius:50%;margin:0 auto;overflow:hidden;background:linear-gradient(135deg,var(--g5),var(--g7));color:#fff;font-size:2rem;font-weight:700;display:flex;align-items:center;justify-content:center;border:3px solid var(--g2)}
.av img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
.av.big{width:120px;height:120px;font-size:3rem}
.lg{display:grid;grid-template-columns:repeat(auto-fill,minmax(170px,1fr));gap:14px}
.lc{background:#fff;border:2px solid var(--g2);border-radius:14px;padding:16px;cursor:pointer;text-align:left;font:inherit;color:inherit;transition:.2s;box-shadow:var(--sh)}
.lc:hover{border-color:var(--g5);transform:translateY(-3px)}
.lc.on{background:var(--g7);border-color:var(--g7);color:#fff}
.lc .no{font-size:1.3rem;font-weight:800;color:var(--g7)}
.lc.on .no{color:#fff}
.lc small{display:block;margin-top:6px;opacity:.75}
.viewer{margin-top:24px;background:#fff;border-radius:16px;box-shadow:var(--sh);overflow:hidden;border:2px solid var(--g2)}
.vh{display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap;padding:20px;background:var(--g1)}
.badge{background:var(--g7);color:#fff;padding:2px 12px;border-radius:99px;font-size:.8rem;font-weight:700}
.vh h3{color:var(--g9);margin:8px 0 4px;font-size:1.3rem}
.va{display:flex;gap:10px;align-items:flex-start}
.btn{background:var(--g7);color:#fff;text-decoration:none;padding:8px 16px;border-radius:10px;font-weight:600;font-size:.9rem;border:2px solid var(--g7)}
.btn:hover{background:var(--g9)}
.btn.o{background:#fff;color:var(--g7)}
.vc iframe{width:100%;height:75vh;border:0;display:block}
.vc img{max-width:100%;display:block;margin:auto}
.empty{padding:50px 20px;text-align:center;color:#6b7280}
.modal{position:fixed;inset:0;background:rgba(20,83,45,.6);display:flex;align-items:center;justify-content:center;padding:16px;z-index:50}
.mbox{background:#fff;border-radius:18px;max-width:460px;width:100%;max-height:90vh;overflow:auto;padding:28px;position:relative}
.close{position:absolute;top:10px;right:14px;border:0;background:none;font-size:1.8rem;cursor:pointer;color:var(--g7)}
.profile{text-align:center}
.profile h2{color:var(--g9);margin:10px 0 6px}
.bio{margin:14px 0;text-align:left}
.profile h4{text-align:left;color:var(--g7);margin-top:14px}
.profile ul{text-align:left;margin:6px 0 0 20px}
.profile a{color:var(--g7)}
.tags{display:flex;gap:6px;flex-wrap:wrap;justify-content:center;margin-bottom:10px}
.tag{background:var(--g1);color:var(--g7);padding:3px 12px;border-radius:99px;font-size:.82rem}
.hidden{display:none!important}
footer{text-align:center;padding:22px;background:var(--g9);color:var(--g2);font-size:.9rem}
@media(max-width:800px){.mg{grid-template-columns:repeat(2,1fr)}}
@media(max-width:480px){.mg{grid-template-columns:1fr}.hero h1{font-size:1.7rem}}
</style>
</head>
<body>

<header class="hero">
 <h1>🌿 Kho Tài Liệu Nhóm</h1>
 <p>Nơi lưu trữ và chia sẻ tài liệu của các thành viên</p>
</header>

<main>
 <h2 class="st">Thành viên</h2>
 <div id="members" class="mg"></div>

 <h2 class="st">Tài liệu theo bài</h2>
 <div id="lessons" class="lg"></div>

 <div id="viewer" class="viewer hidden">
 <div class="vh">
 <div>
 <span id="vb" class="badge"></span>
 <h3 id="vt"></h3>
 <p id="vd"></p>
 <small id="vm"></small>
 </div>
 <div class="va">
 <a id="vo" class="btn" target="_blank">Mở tab mới</a>
 <a id="vl" class="btn o" download>Tải về</a>
 </div>
 </div>
 <div id="vc" class="vc"></div>
 </div>
</main>

<div id="modal" class="modal hidden">
 <div class="mbox">
 <button id="mclose" class="close">&times;</button>
 <div id="mbody"></div>
 </div>
</div>

<footer>© 2025 – Nhóm sinh viên · Hosted on GitHub Pages</footer>

<script>
/* ===== ✏️ SỬA DỮ LIỆU Ở ĐÂY ===== */
const members = [
 {id:"nghi",name:"Trần Lê Quỳnh Nghi",avatar:"images/nghi.jpg",bio:"Xin chào! Mình là Nghi. Viết giới thiệu bản thân ở đây.",skills:["Làm slide"],email:"",link:""},
 {id:"ngoc",name:"Lê Dương Bảo Ngọc",avatar:"images/ngoc.jpg",bio:"Giới thiệu về Ngọc...",skills:[],email:"",link:""},
 {id:"thao",name:"Võ Thị Mai Thảo",avatar:"images/thao.jpg",bio:"Giới thiệu về Thảo...",skills:[],email:"",link:""},
 {id:"phuc",name:"Phạm Minh Phúc",avatar:"images/phuc.jpg",bio:"Giới thiệu về Phúc...",skills:[],email:"",link:""},
 {id:"phat",name:"Trần Huỳnh Phát",avatar:"images/phat.jpg",bio:"Giới thiệu về Phát...",skills:[],email:"",link:""},
 {id:"minh",name:"Tống Hoàng Minh",avatar:"images/minh.jpg",bio:"Giới thiệu về Minh...",skills:[],email:"",link:""}
];

// Mỗi dòng = 1 bài. Muốn thêm bài: copy 1 dòng, dán xuống dưới.
const lessons = [
 {title:"Tên bài 1",desc:"Mô tả bài 1.",author:"nghi",date:"2025-01-10",file:"docs/bai1.pdf"},
 {title:"Tên bài 2",desc:"Mô tả bài 2.",author:"ngoc",date:"2025-01-17",file:"docs/bai2.pdf"},
 {title:"Tên bài 3",desc:"Mô tả bài 3.",author:"thao",date:"2025-01-24",file:"docs/bai3.pptx"},
 {title:"Tên bài 4",desc:"Mô tả bài 4.",author:"phuc",date:"2025-02-01",file:"docs/bai4.docx"},
 {title:"Tên bài 5",desc:"Mô tả bài 5.",author:"phat",date:"2025-02-08",file:"docs/bai5.pdf"},
 {title:"Tên bài 6",desc:"Mô tả bài 6.",author:"minh",date:"2025-02-15",file:"docs/bai6.pdf"}
];

/* ===== CODE XỬ LÝ (không cần sửa) ===== */
const $ = s => document.querySelector(s);
const getM = id => members.find(m => m.id === id);
const initial = n => n.trim().split(" ").pop()[0].toUpperCase();

function avatar(m, big){
 return `<div class="av ${big?"big":""}"><span>${initial(m.name)}</span>` +
 (m.avatar ? `<img src="${m.avatar}" alt="" onerror="this.remove()">` : "") + `</div>`;
}
function renderMembers(){
 $("#members").innerHTML = members.map(m => `
 <div class="mc" data-id="${m.id}">
 ${avatar(m)}
 <h3>${m.name}</h3>
 <span class="role">Thành viên</span>
 <span class="more">Xem giới thiệu →</span>
 </div>`).join("");
 document.querySelectorAll(".mc").forEach(c => c.onclick = () => openProfile(c.dataset.id));
}

function openProfile(id){
 const m = getM(id);
 const mine = lessons.map((l,i) => ({...l, i})).filter(l => l.author === id);
 const skills = m.skills.length ? `<div class="tags">${m.skills.map(s => `<span class="tag">${s}</span>`).join("")}</div>` : "";
 const mail = m.email ? `📧 <a href="mailto:${m.email}">${m.email}</a><br>` : "";
 const link = m.link ? `🔗 <a href="${m.link}" target="_blank">${m.link}</a>` : "";
 const list = mine.length
 ? mine.map(l => `<li><a href="#" data-i="${l.i}">Bài ${l.i+1}: ${l.title}</a></li>`).join("")
 : "<li>Chưa có bài nào.</li>";

 $("#mbody").innerHTML = `
 <div class="profile">
 ${avatar(m, true)}
 <h2>${m.name}</h2>
 <span class="role">Thành viên</span>
 <p class="bio">${m.bio}</p>
 ${skills}
 <p>${mail}${link}</p>
 <h4>Phụ trách (${mine.length} bài)</h4>
 <ul>${list}</ul>
 </div>`;

 $("#mbody").querySelectorAll("[data-i]").forEach(a => a.onclick = e => {
 e.preventDefault();
 closeModal();
 openLesson(+a.dataset.i);
 });
 $("#modal").classList.remove("hidden");
}

function closeModal(){ $("#modal").classList.add("hidden"); }
$("#mclose").onclick = closeModal;
$("#modal").onclick = e => { if (e.target.id === "modal") closeModal(); };
document.addEventListener("keydown", e => { if (e.key === "Escape") closeModal(); });

function renderLessons(){
 $("#lessons").innerHTML = lessons.map((l,i) => `
 <button class="lc" data-i="${i}">
 <div class="no">Bài ${i+1}</div>
 <div>${l.title}</div>
 <small>👤 ${getM(l.author) ? getM(l.author).name : ""}</small>
 </button>`).join("");
 document.querySelectorAll(".lc").forEach(b => b.onclick = () => openLesson(+b.dataset.i));
}

function openLesson(i){
 const l = lessons[i], m = getM(l.author);
 document.querySelectorAll(".lc").forEach((b,k) => b.classList.toggle("on", k === i));

 $("#vb").textContent = "Bài " + (i+1);
 $("#vt").textContent = l.title;
 $("#vd").textContent = l.desc;
 $("#vm").textContent = "👤 " + (m ? m.name : "—") + " · 📅 " + l.date;
 $("#vo").href = l.file || "#";
 $("#vl").href = l.file || "#";

 const ext = (l.file.split(".").pop() || "").toLowerCase();
 let html;
 if (!l.file) {
 html = `<div class="empty">Bài này chưa có tài liệu.</div>`;
 } else if (ext === "pdf") {
 html = `<iframe src="${l.file}"></iframe>`;
 } else if (["png","jpg","jpeg","gif","webp"].includes(ext)) {
 html = `<img src="${l.file}" alt="">`;
 } else if (["doc","docx","ppt","pptx","xls","xlsx"].includes(ext)) {
 if (location.protocol === "file:") {
 html = `<div class="empty">File Word/PowerPoint/Excel chỉ xem trực tiếp được khi web đã đưa lên GitHub Pages. Bạn có thể bấm "Tải về".</div>`;
 } else {
 const url = new URL(l.file, location.href).href;
 html = `<iframe src="https://view.officeapps.live.com/op/embed.aspx?src=${encodeURIComponent(url)}"></iframe>`;
 }
 } else {
 html = `<div class="empty">Không xem trực tiếp được loại file này. Hãy bấm "Tải về".</div>`;
 }

 $("#vc").innerHTML = html;
 $("#viewer").classList.remove("hidden");
 $("#viewer").scrollIntoView({behavior:"smooth", block:"start"});
}

renderMembers();
renderLessons();
</script>
</body>
</html>
