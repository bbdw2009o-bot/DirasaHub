<!DOCTYPE html>  <html lang="ar" dir="rtl">    <head>    
    <meta charset="UTF-8">    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">    
    <title>Dirasa Hub | عبد الحق بولبداوي</title>    
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">    
    <style>    
        :root { --p: #2563eb; --d: #0f172a; --a: #fbbf24; --bg: #f8fafc; --c: #ffffff; }    
        .dark { --bg: #0f172a; --c: #1e293b; --p: #60a5fa; --text: #f8fafc; }    
        body { font-family: 'Cairo', sans-serif; background: var(--bg); color: var(--text); margin: 0; transition: 0.3s; }    
        nav { background: var(--d); color: white; padding: 15px 5%; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 100; }    
        .logo { font-size: 1.6rem; font-weight: 900; }    
        .logo span { color: var(--a); }    
        .theme-toggle { cursor: pointer; background: var(--a); border: none; padding: 5px 15px; border-radius: 20px; font-weight: bold; }    
        header { background: linear-gradient(135deg, var(--d), var(--p)); color: white; padding: 70px 20px; text-align: center; clip-path: polygon(0 0, 100% 0, 100% 85%, 0% 100%); }    
        .owner { background: rgba(255,255,255,0.1); padding: 5px 20px; border-radius: 20px; border: 1px solid var(--a); display: inline-block; margin-bottom: 15px; }    
        .container { max-width: 1200px; margin: -50px auto 50px; padding: 20px; display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 25px; }    
        .card { background: var(--c); border-radius: 20px; padding: 25px; box-shadow: 0 10px 25px rgba(0,0,0,0.05); border-top: 6px solid var(--p); }    
        .item { display: flex; justify-content: space-between; align-items: center; padding: 12px; border-bottom: 1px solid #eee; font-size: 0.95rem; }    
        .dl { background: var(--p); color: white; text-decoration: none; padding: 5px 15px; border-radius: 8px; font-size: 0.8rem; }    
        footer { background: var(--d); color: white; padding: 40px; text-align: center; }    
    </style>    
</head>    
<body>    
    <nav>    
        <div class="logo">Dirasa<span>Hub</span></div>    
        <button class="theme-toggle" onclick="document.body.classList.toggle('dark')">🌓 مظهر</button>    
    </nav>    
    <header>    
        <div class="owner">المطور: عبد الحق بولبداوي</div>    
        <h1>Dirasa Hub - جيل جديد من التعليم</h1>    
        <p>موسوعة الفروض والاختبارات للسنة الأولى متوسط</p>    
    </header>    
    <div class="container" id="hub"></div>    
    <footer>    
        <p>جميع الحقوق محفوظة لمنصة <b>Dirasa Hub</b> &copy; 2026</p>    
        <p>بإشراف: عبد الحق بولبداوي</p>    
    </footer>    
    <script>    
        const subs = [    
            {n:'الرياضيات', i:'📐', c:'#2563eb'}, {n:'العلوم الطبيعية', i:'🧪', c:'#10b981'},    
            {n:'الفيزياء', i:'⚡', c:'#f59e0b'}, {n:'اللغة العربية', i:'📖', c:'#ef4444'},    
            {n:'اللغة الإنجليزية', i:'🇬🇧', c:'#06b6d4'}, {n:'التربية الإسلامية', i:'🕌', c:'#8b5cf6'}    
        ];    
        const hub = document.getElementById('hub');    
        subs.forEach(s => {    
            let files = '';    
            for(let i=1; i<=10; i++) {    
                files += `<div class="item"><span>${i>6?'اختبار':'فرض'} نموذج ${i}</span><a href="https://www.dzexams.com/ar/1am" class="dl">PDF</a></div>`;    
            }    
            hub.innerHTML += `<div class="card" style="border-top-color:${s.c}"><h3>${s.i} ${s.n}</h3>${files}</div>`;    
        });    
    </script>    
</body>    
</html>    
