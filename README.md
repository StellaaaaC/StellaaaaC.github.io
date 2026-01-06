<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stella Cai - Portfolio</title>
    <style>
        /* --- 1. 基础设置 (Reset) --- */
        :root {
            /* 这里定义颜色和字体，方便你修改 */
            --bg-color: #ffffff;
            --text-color: #1a1a1a;
            --gray-text: #666666;
            --accent-color: #000000;
            --card-bg: #f5f5f5;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box; /* 关键：防止padding撑大盒子导致溢出 */
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.5;
            -webkit-font-smoothing: antialiased;
        }

        /* --- 2. 布局容器 (核心修复点) --- */
        /* 
           这里修复了你之前的宽度问题。
           我们不设固定宽度，而是限制最大宽度。
        */
        .container {
            max-width: 1100px; /*在大屏幕上最大显示多宽 */
            width: 90%;        /* 在小屏幕上留出左右5%的空隙，防止贴边 */
            margin: 0 auto;    /* 居中显示 */
        }

        /* --- 3. 导航栏 --- */
        header {
            padding: 40px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-weight: 700;
            font-size: 1.2rem;
            letter-spacing: -0.5px;
        }

        nav a {
            text-decoration: none;
            color: var(--gray-text);
            margin-left: 24px;
            font-size: 0.95rem;
            transition: color 0.2s;
        }

        nav a:hover {
            color: var(--text-color);
        }

        /* --- 4. 个人简介 (Hero Section) --- */
        .hero {
            padding: 80px 0 100px;
        }

        .hero h1 {
            font-size: 3rem; /* 大标题 */
            font-weight: 600;
            line-height: 1.2;
            margin-bottom: 20px;
            letter-spacing: -1px;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--gray-text);
            max-width: 600px;
        }

        /* 手机端适配：字体改小一点 */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2rem; }
            .hero { padding: 50px 0; }
        }

        /* --- 5. 作品集网格 (Grid) --- */
        .projects-grid {
            display: grid;
            /* 
               魔法代码：
               repeat(auto-fit, minmax(320px, 1fr))
               意思是：每列最窄320px，如果屏幕够宽就自动多放几列，
               如果屏幕窄（手机），就自动变成一列。
            */
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px; /* 卡片之间的间距 */
            padding-bottom: 100px;
        }

        .project-card {
            display: block;
            text-decoration: none;
            color: inherit;
            group; /* 用于hover效果 */
        }

        .image-box {
            width: 100%;
            /* 这种写法保持图片比例，比如 4:3 */
            aspect-ratio: 4 / 3; 
            background-color: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 16px;
            position: relative;
        }

        .image-box img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* 保证图片填满盒子不变形 */
            transition: transform 0.4s ease;
        }

        /* 鼠标悬停时的微动效 */
        .project-card:hover .image-box img {
            transform: scale(1.05);
        }

        .project-info h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 4px;
        }

        .project-info p {
            font-size: 0.9rem;
            color: var(--gray-text);
        }

        /* --- 6. 页脚 --- */
        footer {
            border-top: 1px solid #eee;
            padding: 40px 0;
            color: var(--gray-text);
            font-size: 0.9rem;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .social-links a {
            color: var(--text-color);
            text-decoration: none;
            margin-left: 20px;
        }

    </style>
</head>
<body>

    <div class="container">
        
        <!-- 头部导航 -->
        <header>
            <div class="logo">Stella Cai</div>
            <nav>
                <a href="#work">Work</a>
                <a href="#about">About</a>
                <a href="mailto:your-email@example.com">Contact</a>
            </nav>
        </header>

        <!-- 简介区域 -->
        <section class="hero" id="about">
            <!-- 请在这里修改你的个人介绍 -->
            <h1>Creating digital experiences<br>with clarity and purpose.</h1>
            <p>I'm a Product Designer based in [Location], focusing on UI/UX and interaction design.</p>
        </section>

        <!-- 作品集列表 -->
        <section class="projects-grid" id="work">
            
            <!-- 作品 1 -->
            <a href="#" class="project-card">
                <div class="image-box">
                    <!-- 把 src 换成你作品图片的链接 -->
                    <img src="https://images.unsplash.com/photo-1600607686527-6fb886090705?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Project 1">
                </div>
                <div class="project-info">
                    <h3>Project Name 01</h3>
                    <p>UI Design / Case Study</p>
                </div>
            </a>

            <!-- 作品 2 -->
            <a href="#" class="project-card">
                <div class="image-box">
                    <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Project 2">
                </div>
                <div class="project-info">
                    <h3>Mobile App Redesign</h3>
                    <p>Product Design</p>
                </div>
            </a>

            <!-- 作品 3 -->
            <a href="#" class="project-card">
                <div class="image-box">
                    <img src="https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Project 3">
                </div>
                <div class="project-info">
                    <h3>Dashboard System</h3>
                    <p>Web Development</p>
                </div>
            </a>

            <!-- 作品 4 -->
            <a href="#" class="project-card">
                <div class="image-box">
                    <img src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Project 4">
                </div>
                <div class="project-info">
                    <h3>Brand Identity</h3>
                    <p>Graphic Design</p>
                </div>
            </a>

        </section>

        <!-- 页脚 -->
        <footer>
            <div>&copy; 2024 Stella Cai.</div>
            <div class="social-links">
                <a href="#">LinkedIn</a>
                <a href="#">Twitter</a>
                <a href="#">Instagram</a>
            </div>
        </footer>

    </div>

</body>
</html>
