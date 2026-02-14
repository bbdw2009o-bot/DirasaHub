<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dirasa Hub | منصة عبد الحق بولبداوي التفاعلية</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #4834d4;
            --accent: #f9ca24;
            --bg: #f1f2f6;
            --card-bg: #ffffff;
            --text: #2f3640;
            --success: #27ae60;
        }

        .dark-theme {
            --bg: #18191a;
            --card-bg: #242526;
            --text: #e4e6eb;
            --primary: #706fd3;
        }

        body {
            font-family: 'Cairo', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            transition: 0.3s;
        }

        /* Navbar */
        .navbar {
            background: var(--primary);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .logo { color: white; margin: 0; font-weight: 900; font-size: 1.5rem; }
        .logo span { color: var(--accent); }

        .theme-btn {
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
        }

        /* Header */
        header {
            background: var(--primary);
            color: white;
            text-align: center;
            padding: 50px 20px;
            clip-path: polygon(0 0, 100% 0, 100% 85%, 0% 100%);
        }

        .container { max-width: 1100px; margin: auto; padding: 20px; }

        /* Subject Cards */
        .subjects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: -50px;
        }

        .card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        .file-item {
            background: var(--bg);
            margin: 10px 0;
            padding: 10px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .download-btn {
            background: var(--success);
            color: white;
            text-decoration: none;
            padding: 5px 12px;
            border-radius: 5px;
            font-size: 0.8em;
        }

        /* قسم التعليقات التفاعلي */
        .comments-section {
            background: var(--card-bg);
            margin-top: 40px;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .comment-input {
            width: 100%;
            padding: 15px;
            border: 2px solid var(--bg);
            border-radius: 10px;
            background: var(--bg);
            color: var(--text);
            font-family: 'Cairo';
            margin-bottom: 10px;
            resize: none;
        }

        .btn-send {
            background: var(--primary);
            color: white;
            border: none;
            padding: 10px 25px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        #commentsList { margin-top: 20px; }
        .comment-item {
            background: var(--bg);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 10px;
            border-right: 4px solid var(--primary);
        }

        footer {
            text-align: center;
            padding: 40px;
            background: var(--primary);
            color: white;
            margin-top: 50px;
        }

    </style>
</head>
<body>

<nav class="navbar">
    <div class="logo">Dirasa<span>Hub</span></div>
    <button class="theme-btn" onclick="toggleTheme()">🌓 وضع التصفح</button>
</nav>

<header>
    <div style="background: var(--accent); color: black; display: inline-block; padding: 5px 20px; border-radius: 20px; font-weight: bold; margin-bottom: 10px;">بإشراف: عبد الحق بولبداوي</div>
    <h1>مرحباً بك في مجتمع Dirasa Hub</h1>
    <p>حمل ملفاتك، ناقش زملاءك، وتفوق في دراستك</p>
</header>

<div class="container">
    <div class="subjects-grid">
        <div class="card">
            <h3>📐 الرياضيات</h3>
            <div class="file-item">
                <span>اختبار الفصل الثاني 2026</span>
                <a href="#" class="download-btn" onclick="alert('جاري تجهيز الرابط المباشر...')">تحميل</a>
            </div>
            <div class="file-item">
                <span>ملخص شامل للدوال</span>
                <a href="#" class="download-btn">تحميل</a>
            </div>
        </div>
        
        <div class="card">
            <h3>🧪 العلوم الطبيعية</h3>
            <div class="file-item">
                <span>فرض دوري رقم 1</span>
                <a href="#" class="download-btn">تحميل</a>
            </div>
            <div class="file-item">
                <span>تجارب التركيب الضوئي</span>
                <a href="#" class="download-btn">تحميل</a>
            </div>
        </div>
    </div>

    <div class="comments-section">
        <h3>💬 مركز نقاش Dirasa Hub</h3>
        <p style="font-size: 0.9em; opacity: 0.7;">اطرح سؤالك أو اترك نصيحة لزملائك:</p>
        <textarea id="commentText" class="comment-input" rows="3" placeholder="اكتب تعليقك هنا يا بطل..."></textarea>
        <button class="btn-send" onclick="addComment()">نشر التعليق</button>

        <div id="commentsList">
            <div class="comment-item">
                <strong>أمين (تلميذ):</strong> شكراً جزيلاً أستاذ عبد الحق، هذه الملفات ساعدتني كثيراً في الفرض!
            </div>
        </div>
    </div>
</div>

<footer>
    <p>تم التطوير بواسطة <b>عبد الحق بولبداوي</b> &copy; 2026</p>
    <p style="font-size: 0.8em;">Dirasa Hub - وجهتك الأولى للنجاح</p>
</footer>

<script>
    // وظيفة تبديل الوضع الليلي
    function toggleTheme() {
        document.body.classList.toggle('dark-theme');
    }

    // وظيفة إضافة تعليق برمجياً (تجريبية)
    function addComment() {
        const text = document.getElementById('commentText').value;
        if(text.trim() === "") {
            alert("من فضلك اكتب شيئاً أولاً!");
            return;
        }

        const list = document.getElementById('commentsList');
        const newComment = document.createElement('div');
        newComment.className = 'comment-item';
        newComment.innerHTML = `<strong>زائر جديد:</strong> ${text}`;
        
        list.prepend(newComment); // إضافة التعليق في الأعلى
        document.getElementById('commentText').value = ""; // تفريغ الخانة
    }
</script>

</body>
</html># DirasaHub
فروض واختبارات ودروس السنة الرابعة متوسط2026
