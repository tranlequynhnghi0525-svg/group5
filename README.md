<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kho Tài Liệu Nhóm</title>
<style>
 :root{
 --g900:#14532d; --g700:#15803d; --g500:#22c55e;
 --g200:#bbf7d0; --g100:#dcfce7; --g50:#f0fdf4;
 --text:#1f2937; --shadow:0 4px 14px rgba(21,128,61,.15);
 }
 *{box-sizing:border-box;margin:0;padding:0}
 html{scroll-behavior:smooth}
 body{font-family:"Segoe UI",Roboto,Arial,sans-serif;background:var(--g50);color:var(--text);line-height:1.5}

 /* HEADER */
 .hero{background:linear-gradient(135deg,var(--g900),var(--g700) 60%,var(--g500));color:#fff;text-align:center;padding:56px 20px}
 .hero h1{font-size:2.2rem;margin-bottom:8px}
 .hero p{opacity:.9}

 main{max-width:1100px;margin:0 auto;padding:32px 20px 60px}
 .section-title{color:var(--g900);font-size:1.5rem;margin:32px 0 18px;padding-left:12px;border-left:5px solid var(--g500)}

 /* THÀNH VIÊN */
 .member-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
 .member-card{background:#fff;border-radius:16px;padding:22px 14px;text-align:center;cursor:pointer;
 box-shadow:var(--shadow);border-top:5px solid var(--g500);transition:.2s}
 .member-card:hover{transform:translateY(-5px);background:var(--g100)}
 .member-card h3{color:var(--g900);font-size:1.05rem;margin:10px 0 4px}
 .role{display:inline-block;background:var(--g100);color:var(--g700);font-size:.8rem;padding:2px 10px;border-radius:99px}
 .more{display:block;margin-top:10px;font-size:.85rem;color:var(--g700);font-weight:600}

 .avatar{position:relative;width:84px;height:84px;border-radius:50%;margin:0 auto;overflow:hidden;
 background:linear-gradient(135deg,var(--g500),var(--g700));color:#fff;font-size:2rem;font-weight:700;
 display:flex;align-items:center;justify-content:center;border:3px solid var(--g200)}
 .avatar img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
 .avatar.large{width:120px;height:120px;font-size:3rem}

 /* DANH SÁCH BÀI */
 .lesson-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(170px,1fr));gap:14px}
 .lesson-card{background:#fff;border:2px solid var(--g200);border-radius:14px;padding:16px;cursor:pointer;
 text-align:left;font:inherit;color:inherit;transition:.2s;box-shadow:var(--shadow)}
 .lesson-card:hover{border-color:var(--g500);transform:translateY(-3px)}
 .lesson-card.active{background:var(--g700);border-color:var(--g700);color:#fff}
 .lesson-card .no{font-size:1.3rem;font-weight:800;color:var(--g700)}
 .lesson-card .t{font-size:.92rem;margin-top:2px}
 .lesson-card small{display:block;margin-top:6px;opacity:.75}
 .lesson-card.active .no{color:#fff}

 /* KHUNG XEM TÀI LIỆU */
 .viewer{margin-top:24px;background:#fff;border-radius:16px;box-shadow:var(--shadow);overflow:hidden;border:2px solid var(--g200)}
 .viewer-head{display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap;padding:20px;background:var(--g100)}
 .badge{background:var(--g700);color:#fff;padding:2px 12px;border-radius:99px;font-size:.8rem;font-weight:700}
 .viewer-head h3{color:var(--g900);margin:8px 0 4px;font-size:1.3rem}
 .viewer-head small{color:#4b5563}
 .viewer-actions{display:flex;gap:10px;align-items:flex-start}
 .btn{background:var(--g700);color:#fff;text-decoration:none;padding:8px 16px;border-radius:10px;font-weight:600;font-size:.9rem}
 .btn:hover{background:var(--g900)}
 .btn-outline{background:#fff;color:var(--g700);border:2px solid var(--g700)}
 .btn-outline:hover{background:var(--g100);color:var(--g900)}
 .viewer-content iframe{width:100%;height:75vh;border:0;display:block}
 .viewer-content img{max-width:100%;display:block;margin:auto}
 .empty{padding:50px 20px;text-align:center;color:#6b7280}

 /* MODAL */
 .modal{position:fixed;inset:0;background:rgba(20,83,45,.6);display:flex;align-items:center;justify-content:center;padding:16px;z-index:50}
 .modal-content{background:#fff;border-radius:18px;max-width:460px;width:100%;max-height:90vh;overflow:auto;padding:28px;position:relative}
 .close{position:absolute;top:10px;right:14px;border:0;background:none;font-size:1.8rem;cursor:pointer;color:var(--g700)}
 .profile{text-align:center}
 .profile h2{color:var(--g900);margin:10px 0 6px}
 .profile .bio{margin:14px 0;text-align:left}
 .profile h4{text-align:left;color:var(--g700);margin-top:14px}
 .profile ul{text-align:left;margin:6px 0 0 20px}
 .profile a{color:var(--g700)}
 .tags{display:flex;gap:6px;flex-wrap:wrap;justify-content:center;margin-bottom:10px}
 .tag{background:var(--g100);color:var(--g700);padding:3px 12px;border-radius:99px;font-size:.82rem}
 .hidden{display:none!important}

 footer{text-align:center;padding:22px;background:var(--g900);color:var(--g200);font-size:.9rem}

 @media(max-width:800px){.member-grid{grid-template-columns:repeat(2,1fr)}}
 @media(max-width:480px){.member-grid{grid-template-columns:1fr}.hero h1{font-size:1.7rem}}
</style>
</head>
<body>

<header class="hero">
 <h1>🌿 Kho Tài Liệu Nhóm</h1>
 <p>Nơi lưu trữ và chia sẻ tài liệu của các thành viên</p>
</header>

<main>
 <h2 class="section-title">Thành viên</h2>
 <div id="member-list" class="member-grid"></div>

 <h2 class="section-title">Tài liệu theo bài</h2>
 <div id="lesson-list" class="lesson-grid"></div>

 <div id="viewer" class="viewer hidden">
 <div class="viewer-head">
 <div>
 <span id="v-badge" class="badge"></span>
 <h3 id="v-title"></h3>
 <p id="v-desc"></p>
 <small id="v-meta"></small>
 </div>
 <div class="viewer-actions">
 <a id="v-open" class="btn" target="_blank">Mở tab mới</a>
 <a id="v-down" class="btn btn-outline" download>Tải về</a>
 </div>
 </div>
 <div id="v-content" class="viewer-content"></div>
 </div>
</main>

<div id="modal" class="modal hidden">
 <div class="modal-content">
 <button id="modal-close" class="close">&times;</button>
 <div id="modal-body"></div>
 </div>
</div>

<footer>© 2025 – Nhóm sinh viên · Hosted on GitHub Pages</footer>

<script>
/* =====================================================
 ✏️ CHỈNH SỬA DỮ LIỆU Ở ĐÂY
 ===================================================== */
const members = [
 { id:"nghi", name:"Trần Lê Quỳnh Nghi", role:"Thành viên", avatar:"images/nghi.jpg",
 bio:"Xin chào! Mình là Nghi. Viết vài dòng giới thiệu bản thân ở đây.", skills:["Làm slide"], email:"", link:"" },
 { id:"ngoc", name:"Lê Dương Bảo Ngọc", role:"Thành viên", avatar:"images/ngoc.jpg",
 bio:"Giới thiệu về Ngọc...", skills:[], email:"", link:"" },
 { id:"thao", name:"Võ Thị Mai Thảo", role:"Thành viên", avatar:"images/thao.jpg",
 bio:"Giới thiệu về Thảo...", skills:[], email:"", link:"" },
 { id:"phuc", name:"Phạm Minh Phúc", role:"Thành viên", avatar:"images/phuc.jpg",
 bio:"Giới thiệu về Phúc...", skills:[], email:"", link:"" },
 { id:"phat", name:"Trần Huỳnh Phát", role:"Thành viên", avatar:"images/phat.jpg",
 bio:"Giới thiệu về Phát...", skills:[], email:"", link:"" },
 { id:"minh", name:"Tống Hoàng Minh", role:"Thành viên", avatar:"images/minh.jpg",
 bio:"Giới thiệu về Minh...", skills:[], email:"", link:"" }
];

// Mỗi dòng = 1 bài. Thêm bài mới: copy 1 dòng rồi dán xuống dưới.
// file: đường dẫn tới tài liệu trong repo (VD: docs/bai1.pdf). Để "" nếu chưa có.
const lessons = [
 { title:"Tên bài 1", description:"Mô tả ngắn về bài 1.", author:"nghi", date:"2
