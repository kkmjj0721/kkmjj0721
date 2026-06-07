<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AlexandraChen (Lexi) - GitHub Cream Style</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #fcf6e8;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
            color: #24292f;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* 模拟浏览器窗口及其长宽比 */
        .browser-window {
            width: 100%;
            max-width: 1300px;
            aspect-ratio: 16 / 9;
            background-color: #fdfbf7;
            border-radius: 12px;
            box-shadow: 0 20px 50px rgba(180, 160, 120, 0.15);
            border: 1px solid #ebdcb9;
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }

        /* 浏览器顶部控制栏 */
        .browser-header {
            height: 42px;
            background-color: #f7f2e4;
            border-bottom: 1px solid #ebdcb9;
            display: flex;
            align-items: center;
            padding: 0 16px;
            position: relative;
        }

        .browser-dots {
            display: flex;
            gap: 8px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }
        .dot-red { background-color: #ff5f56; }
        .dot-yellow { background-color: #ffbd2e; }
        .dot-green { background-color: #27c93f; }

        .browser-tab {
            position: absolute;
            left: 100px;
            bottom: -1px;
            background-color: #fdfbf7;
            padding: 8px 20px;
            border-radius: 8px 8px 0 0;
            border: 1px solid #ebdcb9;
            border-bottom: none;
            font-size: 13px;
            display: flex;
            align-items: center;
            gap: 8px;
            color: #57606a;
        }

        /* GitHub 内部导航栏 */
        .github-nav {
            height: 56px;
            background-color: #fdfbf7;
            border-bottom: 1px solid #ebdcb9;
            display: flex;
            align-items: center;
            padding: 0 32px;
            gap: 16px;
        }

        .github-logo {
            font-size: 24px;
            color: #24292f;
        }

        .search-bar {
            background-color: #f4eeda;
            border: 1px solid #ebdcb9;
            border-radius: 6px;
            padding: 4px 12px;
            font-size: 14px;
            width: 240px;
            color: #57606a;
        }

        .nav-links {
            display: flex;
            gap: 16px;
            font-size: 14px;
            font-weight: 500;
            color: #24292f;
        }

        /* 主体内容滚动区域 */
        .window-content {
            flex: 1;
            overflow-y: auto;
            padding: 24px 32px;
        }

        /* 顶部标签页 */
        .profile-tabs {
            display: flex;
            gap: 24px;
            border-bottom: 1px solid #ebdcb9;
            margin-bottom: 24px;
            padding-left: 280px;
        }

        .tab-item {
            padding: 8px 12px;
            font-size: 14px;
            color: #24292f;
            cursor: pointer;
            position: relative;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .tab-item.active {
            font-weight: 600;
        }

        .tab-item.active::after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            right: 0;
            height: 2px;
            background-color: #f4be41;
        }

        .tab-badge {
            background-color: #f4eeda;
            padding: 2px 6px;
            border-radius: 10px;
            font-size: 12px;
        }

        /* 三栏总布局 */
        .main-layout {
            display: grid;
            grid-template-columns: 260px 1fr 240px;
            gap: 32px;
        }

        /* 左侧栏：个人核心信息 */
        .left-sidebar {
            display: flex;
            flex-direction: column;
        }

        .avatar-container {
            width: 260px;
            height: 260px;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid #f5ebd2;
            background: linear-gradient(135deg, #ecdca5, #bfa668);
            position: relative;
            margin-bottom: 16px;
            box-shadow: 0 8px 24px rgba(180, 160, 120, 0.1);
        }

        /* 用纯CSS/SVG绘制一个相似的可爱女孩头像 */
        .avatar-svg {
            width: 100%;
            height: 100%;
        }

        .profile-name {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 4px;
        }

        .profile-username {
            font-size: 16px;
            color: #6e7781;
            margin-bottom: 16px;
        }

        .profile-bio {
            font-size: 14px;
            margin-bottom: 16px;
            line-height: 1.5;
        }

        .profile-meta {
            font-size: 14px;
            color: #57606a;
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin-bottom: 16px;
        }

        .btn-gray-follow {
            width: 100%;
            padding: 6px;
            background-color: #fdfbf7;
            border: 1px solid #ebdcb9;
            border-radius: 6px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            text-align: center;
            transition: background 0.2s;
        }
        .btn-gray-follow:hover {
            background-color: #f5ebd2;
        }

        /* 中间栏：README 和 主要组件 */
        .center-content {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        /* README 卡片 */
        .readme-block {
            background-color: #ffffff;
            border: 1px solid #ebdcb9;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(180, 160, 120, 0.05);
        }

        .readme-header {
            padding: 12px 16px;
            background-color: #fffdf9;
            border-bottom: 1px solid #ebdcb9;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
            color: #57606a;
        }

        .readme-body {
            padding: 24px;
        }

        /* 仿图中的插画Banner组件 */
        .custom-banner {
            width: 100%;
            height: 160px;
            background: linear-gradient(to right, #fbf7ec, #f5ebd2);
            border-radius: 6px;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
            display: flex;
            justify-content: space-between;
            padding: 20px 40px;
            align-items: center;
            border: 1px solid #ebdcb9;
        }

        /* 招呼和技术栈网格 */
        .readme-title {
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 6px;
        }

        .readme-subtitle {
            font-size: 14px;
            color: #57606a;
            margin-bottom: 20px;
            font-weight: 500;
        }

        .readme-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 16px;
        }

        .grid-col h4 {
            font-size: 14px;
            margin-bottom: 12px;
            color: #24292f;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .grid-col ul {
            list-style: none;
            font-size: 13px;
            color: #57606a;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        /* 技术栈小徽章组件 */
        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .badge {
            background-color: #fbf7ec;
            border: 1px solid #ebdcb9;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        /* 黄色系贡献热力图小组件 */
        .contributions-block {
            background-color: #ffffff;
            border: 1px solid #ebdcb9;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 12px rgba(180, 160, 120, 0.05);
        }

        .contributions-title {
            font-size: 14px;
            margin-bottom: 12px;
        }

        .heatmap-container {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }

        .months-labels {
            display: flex;
            justify-content: space-between;
            font-size: 11px;
            color: #57606a;
            padding-left: 20px;
            margin-bottom: 2px;
        }

        .heatmap-grid-wrapper {
            display: flex;
            gap: 6px;
        }

        .days-labels {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            font-size: 11px;
            color: #57606a;
            padding-top: 2px;
            height: 80px;
        }

        .heatmap-grid {
            display: grid;
            grid-template-flow: column;
            grid-template-columns: repeat(45, 12px);
            grid-template-rows: repeat(7, 12px);
            gap: 2px;
            flex: 1;
        }

        .heatmap-cell {
            width: 12px;
            height: 12px;
            border-radius: 2px;
        }

        /* 黄色奶油风色阶 */
        .lvl-0 { background-color: #f7f4eb; }
        .lvl-1 { background-color: #fdf0cd; }
        .lvl-2 { background-color: #fbe39b; }
        .lvl-3 { background-color: #f9d365; }
        .lvl-4 { background-color: #f4be41; }

        /* 精选仓库列表（2x2网格组件） */
        .repos-section-title {
            font-size: 15px;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .repos-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        .repo-card {
            background-color: #ffffff;
            border: 1px solid #ebdcb9;
            border-radius: 8px;
            padding: 16px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-shadow: 0 4px 12px rgba(180, 160, 120, 0.03);
        }

        .repo-top h5 {
            color: #bfa668;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 8px;
            cursor: pointer;
        }

        .repo-desc {
            font-size: 12px;
            color: #57606a;
            line-height: 1.5;
            margin-bottom: 16px;
        }

        .repo-meta {
            display: flex;
            gap: 16px;
            font-size: 12px;
            color: #57606a;
            align-items: center;
        }

        .lang-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            display: inline-block;
        }

        /* 右侧栏：自定义高亮小组件区 */
        .right-sidebar {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .btn-yellow-follow {
            width: 100%;
            padding: 10px;
            background-color: #f4be41;
            border: none;
            border-radius: 6px;
            font-size: 14px;
            font-weight: 600;
            color: #24292f;
            cursor: pointer;
            text-align: center;
            box-shadow: 0 4px 12px rgba(244, 190, 65, 0.2);
            transition: background 0.2s;
        }
        .btn-yellow-follow:hover {
            background-color: #e2ae33;
        }

        .right-widget {
            background-color: #ffffff;
            border: 1px solid #ebdcb9;
            border-radius: 8px;
            padding: 16px;
        }

        .widget-title {
            font-size: 13px;
            font-weight: 600;
            color: #24292f;
            margin-bottom: 12px;
        }

        .status-list {
            list-style: none;
            font-size: 13px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .status-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: #bfa668;
            font-weight: 500;
        }
    </style>
</head>
<body>

<div class="browser-window">
    <!-- 顶部浏览器控制栏 -->
    <div class="browser-header">
        <div class="browser-dots">
            <div class="dot dot-red"></div>
            <div class="dot dot-yellow"></div>
            <div class="dot dot-green"></div>
        </div>
        <div class="browser-tab">
            <span>🐱 AlexandraChen (Lexi) - GitHub</span>
        </div>
    </div>

    <!-- GitHub 导航栏 -->
    <div class="github-nav">
        <div class="github-logo"><b>GitHub</b></div>
        <div class="search-bar">Search for junq to...</div>
        <div class="nav-links">
            <span>Marketplace</span>
            <span>Explore</span>
        </div>
    </div>

    <!-- 滚动区域 -->
    <div class="window-content">
        <!-- 标签页选项卡 -->
        <div class="profile-tabs">
            <div class="tab-item active">
                📝 alexandrofile
            </div>
            <div class="tab-item">
                📦 Projects <span class="tab-badge">0</span>
            </div>
            <div class="tab-item">
                📰 Profiles
            </div>
        </div>

        <!-- 三栏核心布局 -->
        <div class="main-layout">
            
            <!-- 左侧：基础基础资料 -->
            <div class="left-sidebar">
                <div class="avatar-container">
                    <!-- 纯独创矢量SVG设计，直接集成奶油色插画风格头像 -->
                    <svg class="avatar-svg" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                        <defs>
                            <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                                <stop offset="0%" style="stop-color:#f6edd2;stop-opacity:1" />
                                <stop offset="100%" style="stop-color:#d4be83;stop-opacity:1" />
                            </linearGradient>
                        </defs>
                        <circle cx="100" cy="100" r="100" fill="url(#bgGrad)" />
                        <!-- 背景装饰码流 -->
                        <text x="20" y="50" fill="#ba9e59" font-size="12" opacity="0.3" font-family="monospace">0101</text>
                        <text x="150" y="80" fill="#ba9e59" font-size="12" opacity="0.3" font-family="monospace">&lt;/&gt;</text>
                        <text x="30" y="140" fill="#ba9e59" font-size="12" opacity="0.3" font-family="monospace">f(x)</text>
                        <!-- 头发后侧 -->
                        <path d="M50,110 Q100,50 150,110 Q160,160 150,190 L50,190 Z" fill="#3d3522"/>
                        <!-- 脸部 -->
                        <ellipse cx="100" cy="115" rx="45" ry="50" fill="#fcecd2" />
                        <!-- 头发前侧/刘海 -->
                        <path d="M52,100 Q100,60 148,100 Q140,75 100,75 Q60,75 52,100" fill="#2d2617"/>
                        <!-- 眼镜 -->
                        <circle cx="80" cy="110" r="14" stroke="#4a3e25" stroke-width="3" fill="none"/>
                        <circle cx="120" cy="110" r="14" stroke="#4a3e25" stroke-width="3" fill="none"/>
                        <line x1="94" y1="110" x2="106" y2="110" stroke="#4a3e25" stroke-width="3"/>
                        <!-- 眼睛 -->
                        <circle cx="80" cy="110" r="3" fill="#2d2617"/>
                        <circle cx="120" cy="110" r="3" fill="#2d2617"/>
                        <!-- 腮红与微笑 -->
                        <circle cx="68" cy="122" r="6" fill="#f4bca1" opacity="0.6"/>
                        <circle cx="132" cy="122" r="6" fill="#f4bca1" opacity="0.6"/>
                        <path d="M95,124 Q100,129 105,124" stroke="#4a3e25" stroke-width="2" fill="none"/>
                        <!-- 耳机 -->
                        <path d="M55,110 Q100,45 145,110" stroke="#876d33" stroke-width="6" fill="none"/>
                        <rect x="48" y="98" width="10" height="24" rx="4" fill="#a48847" />
                        <rect x="142" y="98" width="10" height="24" rx="4" fill="#a48847" />
                    </svg>
                </div>
                <h2 class="profile-name">Alexandra 'Lexi' Chen</h2>
                <div class="profile-username">@alexandrachen</div>
                <div class="profile-bio">she/her<br>📍 Shanghai, China<br>Coding away on side projects</div>
                <button class="btn-gray-follow">Follow</button>
            </div>

            <!-- 中间：README 核心以及黄色热力图 -->
            <div class="center-content">
                
                <!-- README 组件 -->
                <div class="readme-block">
                    <div class="readme-header">
                        <span>📖 README.md</span>
                        <span>✏️</span>
                    </div>
                    <div class="readme-body">
                        <!-- 内置矢量温馨插画Banner -->
                        <div class="custom-banner">
                            <div style="max-width: 60%;">
                                <h3 class="readme-title">👋 Hey there! I'm Alexandra!</h3>
                                <p class="readme-subtitle">I'm a Frontend Developer & Creative Coder</p>
                            </div>
                            <!-- 纯SVG绘制小猫与办公桌组合插画，深度还原图片风采 -->
                            <svg width="160" height="120" viewBox="0 0 160 120" xmlns="http://www.w3.org/2000/svg">
                                <rect x="10" y="85" width="140" height="6" fill="#bfa668" rx="2" />
                                <!-- 电脑 -->
                                <rect x="70" y="45" width="45" height="32" fill="#3d3522" rx="3" />
                                <rect x="73" y="48" width="39" height="26" fill="#ffffff" />
                                <path d="M65,77 L120,77 L115,85 L70,85 Z" fill="#a48847" />
                                <!-- 绿植 -->
                                <path d="M35,65 Q25,50 35,40 Q45,50 35,65" fill="#9cb881" />
                                <path d="M42,68 Q55,55 45,45 Q35,55 42,68" fill="#8ba770" />
                                <polygon points="32,65 44,65 40,85 36,85" fill="#d4be83" />
                                <!-- 可爱萌猫 -->
                                <ellipse cx="132" cy="70" rx="10" ry="14" fill="#dfa413" />
                                <circle cx="132" cy="56" r="8" fill="#dfa413" />
                                <polygon points="125,50 129,56 125,56" fill="#dfa413" />
                                <polygon points="139,50 135,56 139,56" fill="#dfa413" />
                                <path d="M132,78 Q140,82 145,72" stroke="#dfa413" stroke-width="3" fill="none" stroke-linecap="round" />
                            </svg>
                        </div>

                        <!-- 详情三栏栅格组件 -->
                        <div class="readme-grid">
                            <div class="grid-col">
                                <h4>📚 Projects & Impact</h4>
                                <ul>
                                    <li>💻 Portfolio Website</li>
                                    <li>📦 Open Source Contributions</li>
                                    <li>🎨 UI Library</li>
                                </ul>
                            </div>
                            <div class="grid-col">
                                <h4>🛠️ Tech Stack & Tools</h4>
                                <div class="tech-badges">
                                    <span class="badge"><span class="lang-dot" style="background:#f1e05a"></span>JS</span>
                                    <span class="badge"><span class="lang-dot" style="background:#3178c6"></span>TS</span>
                                    <span class="badge"><span class="lang-dot" style="background:#61dafb"></span>React</span>
                                    <span class="badge"><span class="lang-dot" style="background:#3572A5"></span>Python</span>
                                    <span class="badge"><span class="lang-dot" style="background:#F24E1E"></span>Figma</span>
                                </div>
                            </div>
                            <div class="grid-col">
                                <h4>📬 Find me online:</h4>
                                <ul>
                                    <li>💼 LinkedIn</li>
                                    <li>🐦 Twitter</li>
                                    <li>✍️ Medium</li>
                                </ul>
                                <div style="margin-top:12px; font-size:12px; color:#bfa668;">
                                    <b>🌱 Learning:</b> Next.js & Svelte
                                </div>
                            </div>
                        </div>

                    </div>
                </div>

                <!-- 奶油黄色系代码热力图组件 -->
                <div class="contributions-block">
                    <div class="contributions-title">2,354 contributions in the last year</div>
                    <div class="heatmap-container">
                        <div class="months-labels">
                            <span>Jan</span><span>Feb</span><span>Mar</span><span>Apr</span><span>May</span><span>Jun</span><span>Jul</span><span>Aug</span><span>Sep</span><span>Oct</span><span>Nov</span><span>Dec</span>
                        </div>
                        <div class="heatmap-grid-wrapper">
                            <div class="days-labels">
                                <span>Mon</span><span>Wed</span><span>Fri</span>
                            </div>
                            <div class="heatmap-grid" id="heatmapGrid"></div>
                        </div>
                    </div>
                </div>

                <!-- 精选仓库组件区 -->
                <div>
                    <div class="repos-section-title">Top Repositories</div>
                    <div class="repos-grid">
                        <div class="repo-card">
                            <div class="repo-top">
                                <h5>📁 Portfolio</h5>
                                <p class="repo-desc">Portfolio website is a long-term unique project showcasing personal works.</p>
                            </div>
                            <div class="repo-meta">
                                <span><span class="lang-dot" style="background:#f1e05a"></span> JavaScript</span>
                                <span>⭐ 1.2k</span>
                            </div>
                        </div>
                        <div class="repo-card">
                            <div class="repo-top">
                                <h5>📁 VueUI</h5>
                                <p class="repo-desc">VueUI, customized modular components library with beautiful creamy themes.</p>
                            </div>
                            <div class="repo-meta">
                                <span><span class="lang-dot" style="background:#41b883"></span> Vue</span>
                                <span>⭐ 850</span>
                            </div>
                        </div>
                        <div class="repo-card">
                            <div class="repo-top">
                                <h5>📁 OpenSourceDev</h5>
                                <p class="repo-desc">OpenSourceDev for massive web developer automation toolkits workflow.</p>
                            </div>
                            <div class="repo-meta">
                                <span><span class="lang-dot" style="background:#3572A5"></span> Python</span>
                                <span>⭐ 410</span>
                            </div>
                        </div>
                        <div class="repo-card">
                            <div class="repo-top">
                                <h5>📁 CodingSketches</h5>
                                <p class="repo-desc">Coding Sketches for creative canvas designs and interactions.</p>
                            </div>
                            <div class="repo-meta">
                                <span><span class="lang-dot" style="background:#f1e05a"></span> JavaScript</span>
                                <span>⭐ 215</span>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

            <!-- 右侧栏：黄色突出按钮及联系状态 -->
            <div class="right-sidebar">
                <button class="btn-yellow-follow">Follow</button>
                
                <div class="right-widget" style="font-size:13px;">
                    <div style="margin-bottom:8px;">👥 <b>337</b> followers</div>
                    <div>💝 Sponsorship info</div>
                </div>

                <div class="right-widget">
                    <div class="widget-title">Personalized status:</div>
                    <ul class="status-list">
                        <li class="status-item">✉️ info@alexanchen</li>
                        <li class="status-item">📞 +alexandrachen</li>
                        <li class="status-item">🌐 alexandrachen.com</li>
                    </ul>
                </div>
            </div>

        </div>
    </div>
</div>

<script>
    // 动态生成符合白黄色调色盘（奶油风）的精美贡献热力图格子
    const grid = document.getElementById('heatmapGrid');
    const totalCells = 45 * 7;
    for (let i = 0; i < totalCells; i++) {
        const cell = document.createElement('div');
        cell.classList.add('heatmap-cell');
        
        // 随机概率生成高亮黄色阶，使其分布自然逼真
        const rand = Math.random();
        if (rand > 0.85) {
            cell.classList.add('lvl-4');
        } else if (rand > 0.7) {
            cell.classList.add('lvl-3');
        } else if (rand > 0.5) {
            cell.classList.add('lvl-2');
        } else if (rand > 0.2) {
            cell.classList.add('lvl-1');
        } else {
            cell.classList.add('lvl-0');
        }
        grid.appendChild(cell);
    }
</script>

</body>
</html>
