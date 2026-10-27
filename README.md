<!DOCTYPE html>
<html lang="vi">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Kho Tài Liệu Nhóm</title>
 <link rel="stylesheet" href="style.css">
</head>
<body>

 <header class="hero">
 <h1>📚 Kho Tài Liệu Nhóm</h1>
 <p>Nơi lưu trữ và chia sẻ tài liệu của các thành viên</p>
 </header>

 <main>
 <!-- THÀNH VIÊN -->
 <section id="members">
 <h2>👥 Thành viên</h2>
 <div id="member-list" class="member-grid"></div>
 </section>

 <!-- TÀI LIỆU -->
 <section id="documents">
 <h2>📁 Tài liệu</h2>
 <div class="toolbar">
 <input type="text" id="search" placeholder="🔍 Tìm tài liệu...">
 <select id="filter-category"></select>
 <select id="filter-author"></select>
 </div>
 <div id="doc-list" class="doc-grid"></div>
 </section>
 </main>

 <!-- MODAL GIỚI THIỆU CÁ NHÂN -->
 <div id="modal" class="modal hidden">
 <div class="modal-content">
 <button id="modal-close" class="close">&times;</button>
 <div id="modal-body"></div>
 </div>
 </div>

 <footer>© 2025 – Nhóm sinh viên. Hosted on GitHub Pages.</footer>

 <script src="data.js"></script>
 <script src="script.js"></script>
</body>
</html>
