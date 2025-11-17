<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>نظام المواد والملازم – النسخة متعددة اللغات</title>

<style>
    body {
        font-family: "Cairo", sans-serif;
        background: linear-gradient(135deg, #4C6EF5, #9775FA);
        margin: 0;
        padding: 40px 20px;
        direction: rtl;
        color: #fff;
        transition: 0.3s;
    }

    h1 {
        text-align: center;
        margin-bottom: 35px;
        font-size: 32px;
        font-weight: 700;
    }

    .lang-btn {
        display: block;
        margin: 0 auto 25px;
        padding: 10px 20px;
        border-radius: 12px;
        border: none;
        cursor: pointer;
        background: rgba(255,255,255,0.25);
        color: #fff;
        font-weight: 600;
        transition: 0.3s;
    }

    .lang-btn:hover {
        background: rgba(255,255,255,0.35);
    }

    .subject-card {
        background: rgba(255, 255, 255, 0.15);
        padding: 20px;
        margin-bottom: 15px;
        border-radius: 16px;
        box-shadow: 0 6px 20px rgba(0,0,0,0.15);
        backdrop-filter: blur(10px);
        transition: 0.3s;
        cursor: pointer;
    }

    .subject-card:hover {
        transform: scale(1.03);
        background: rgba(255,255,255,0.25);
    }

    .subject-header {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .subject-header h3 {
        margin: 0;
        font-size: 22px;
        font-weight: 600;
    }

    .teacher {
        margin-top: 8px;
        font-size: 15px;
        opacity: 0.9;
    }

    .materials-box {
        background: rgba(255,255,255,0.20);
        padding: 15px;
        margin-top: 12px;
        border-radius: 12px;
        display: none;
        animation: slide 0.35s ease;
    }

    @keyframes slide {
        from { transform: translateY(-10px); opacity: 0; }
        to { transform: translateY(0); opacity: 1; }
    }

    .material-item {
        color: #fff;
        text-decoration: none;
        display: block;
        background: rgba(0,0,0,0.25);
        padding: 10px;
        border-radius: 10px;
        margin-bottom: 8px;
        transition: 0.25s;
    }

    .material-item:hover {
        background: rgba(0,0,0,0.35);
        transform: translateX(-5px);
    }

    .arrow {
        font-size: 20px;
        transition: 0.3s;
    }

    .rotate {
        transform: rotate(90deg);
    }
</style>
</head>

<body>

<h1 id="title">📚 المواد الدراسية</h1>
<button class="lang-btn" onclick="switchLang()">Switch Language / تغيير اللغة</button>

<!-- مادة 1 -->
<div class="subject-card" onclick="toggleMaterials('m1','a1')">
    <div class="subject-header">
        <h3 class="sub-ar">برمجة 1</h3>
        <h3 class="sub-en hidden">Programming 1</h3>
        <span id="a1" class="arrow">▶</span>
    </div>ٍ
    <div class="teacher">
        <span class="ar"> 👩‍🏫 م. هرمان خالدٍٍ</span>
        <span class="en hidden"></span>
    </div>
</div>

<div id="m1" class="materials-box">
    <a href="#" class="material-item">
        <span class="ar">📄 محاضرة 1 – مقدمة</span>
        <span class="en hidden">📄 Lecture 1 – Introduction</span>
    </a>
    <a href="#" class="material-item">
        <span class="ar">📄 خوارزميات أساسية</span>
        <span class="en hidden">📄 Basic Algorithms</span>
    </a>
    <a href="#" class="material-item">
        <span class="ar">📄 الواجب الأول</span>
        <span class="en hidden">📄 First Assignment</span>
    </a>
</div>

<!-- مادة 2 -->
<div class="subject-card" onclick="toggleMaterials('m2','a2')">
    <div class="subject-header">
        <h3 class="sub-ar">هياكل بيانات</h3>
        <h3 class="sub-en hidden">Data Structures</h3>
        <span id="a2" class="arrow">▶</span>
    </div>
    <div class="teacher">
        <span class="ar">👨‍🏫 م. علي</span>
        <span class="en hidden">👨‍🏫 Eng. Ali</span>
    </div>
</div>

<div id="m2" class="materials-box">
    <a href="#" class="material-item">
        <span class="ar">📄 محاضرة 1 PDF</span>
        <span class="en hidden">📄 Lecture 1 PDF</span>
    </a>
    <a href="#" class="material-item">
        <span class="ar">📄 تمارين الأسبوع الثاني</span>
        <span class="en hidden">📄 Week 2 Exercises</span>
    </a>
</div>

<!-- مادة 3 -->
<div class="subject-card" onclick="toggleMaterials('m3','a3')">
    <div class="subject-header">
        <h3 class="sub-ar">شبكات الحاسوب</h3>
        <h3 class="sub-en hidden">Computer Networks</h3>
        <span id="a3" class="arrow">▶</span>
    </div>
    <div class="teacher">
        <span class="ar">👩‍🏫 د. مي</span>
        <span class="en hidden">👩‍🏫 Dr. Mai</span>
    </div>
</div>

<div id="m3" class="materials-box">
    <a href="#" class="material-item">
        <span class="ar">📄 أساسيات الشبكات</span>
        <span class="en hidden">📄 Network Basics</span>
    </a>
</div>

<script>
function toggleMaterials(boxId, arrowId) {
    let box = document.getElementById(boxId);
    let arrow = document.getElementById(arrowId);
    box.style.display = (box.style.display === "block") ? "none" : "block";
    arrow.classList.toggle("rotate");
}

// تغيير اللغة
let lang = "ar";
function switchLang() {
    const arElements = document.querySelectorAll(".ar");
    const enElements = document.querySelectorAll(".en");
    const subAr = document.querySelectorAll(".sub-ar");
    const subEn = document.querySelectorAll(".sub-en");
    const title = document.getElementById("title");

    if(lang === "ar") {
        arElements.forEach(el => el.classList.add("hidden"));
        enElements.forEach(el => el.classList.remove("hidden"));
        subAr.forEach(el => el.classList.add("hidden"));
        subEn.forEach(el => el.classList.remove("hidden"));
        title.textContent = "📚 Subjects";
        lang = "en";
    } else {
        arElements.forEach(el => el.classList.remove("hidden"));
        enElements.forEach(el => el.classList.add("hidden"));
        subAr.forEach(el => el.classList.remove("hidden"));
        subEn.forEach(el => el.classList.add("hidden"));
        title.textContent = "📚 المواد الدراسية";
        lang = "ar";
    }
}
</script>

</body>
</html>

