<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Platform Welcome</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&family=Poppins:wght@400;600&display=swap" rel="stylesheet">
    <style>
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        @keyframes bounce {
            0%, 100% { transform: translateX(0); }
            50% { transform: translateX(8px); }
        }
        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 0.8;
            }
            100% {
                transform: scale(30, 30);
                opacity: 0;
            }
        }
        @keyframes floatAnimation {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --accent-color: #e74c3c;
            --background-color: #f8f9fa;
            --text-color: #2c3e50;
        }
        body {
            margin: 0;
            padding: 0;
            font-family: 'Roboto', sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        #ai-platform-welcome {
            padding: 30px;
            transition: background-color 0.5s ease;
        }
        #ai-platform-welcome .gradient-box {
            background: linear-gradient(135deg, var(--secondary-color), var(--primary-color), #2980b9);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: white;
            padding: 25px;
            text-align: left;
            font-size: 16px;
            border-radius: 10px;
            margin-bottom: 30px;
            line-height: 1.8;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        #ai-platform-welcome .gradient-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        #ai-platform-welcome .gradient-box a {
            color: #ecf0f1;
            text-decoration: none;
            transition: color 0.3s ease, text-shadow 0.3s ease;
        }
        #ai-platform-welcome .gradient-box a:hover {
            color: #fff;
            text-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
        }
        #ai-platform-welcome .arrow {
            color: #ecf0f1;
            animation: bounce 1.5s infinite;
            display: inline-block;
        }
        #ai-platform-welcome h1, #ai-platform-welcome h2 {
            color: var(--secondary-color);
            transition: color 0.3s ease;
            font-family: 'Poppins', sans-serif;
        }
        #ai-platform-welcome .feature-box {
            background: #ffffff;
            border-left: 5px solid var(--primary-color);
            padding: 20px;
            margin-bottom: 25px;
            border-radius: 8px;
            transition: all 0.4s ease;
            opacity: 1;
            transform: translateY(0);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            font-weight:normal;
        }
        #ai-platform-welcome .feature-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        #ai-platform-welcome .custom-gradient-button {
            background: linear-gradient(90deg, var(--primary-color), #2980b9);
            border: none;
            color: white;
            padding: 15px 30px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 18px;
            margin: 15px 0;
            cursor: pointer;
            border-radius: 50px;
            transition: all 0.4s ease;
            max-width: 100%;
            box-sizing: border-box;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }
        #ai-platform-welcome .custom-gradient-button:hover {
            background: linear-gradient(90deg, #2980b9, var(--primary-color));
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(52, 152, 219, 0.4);
        }
        #ai-platform-welcome .custom-gradient-button::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        #ai-platform-welcome .custom-gradient-button:hover::after {
            animation: ripple 1.2s ease-out;
        }
        #ai-platform-welcome .welcome-section {
            background: linear-gradient(135deg, var(--background-color) 0%, #e9ecef 100%);
            border-radius: 15px;
            padding: 40px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
            margin-bottom: 50px;
        }
        #ai-platform-welcome .welcome-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(52, 152, 219, 0.1) 0%, rgba(52, 152, 219, 0) 70%);
            transform: rotate(30deg);
            pointer-events: none;
        }
        #ai-platform-welcome .welcome-title {
            font-size: 3em;
            color: var(--secondary-color);
            margin-bottom: 25px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        #ai-platform-welcome .welcome-description {
            font-size: 1.2em;
            color: var(--text-color);
            margin-bottom: 30px;
            line-height: 1.8;
        }
        #ai-platform-welcome .highlight {
            background: linear-gradient(120deg, rgba(52, 152, 219, 0.2) 0%, rgba(52, 152, 219, 0.4) 100%);
            background-repeat: no-repeat;
            background-size: 100% 0.4em;
            background-position: 0 88%;
            transition: background-size 0.3s ease-in;
            padding: 0 4px;
        }
        #ai-platform-welcome .highlight:hover {
            background-size: 100% 100%;
        }
        #ai-platform-welcome .floating-element {
            animation: floatAnimation 3s ease-in-out infinite;
        }
        #ai-platform-welcome .feature-icon {
            font-size: 2em;
            color: var(--primary-color);
            margin-bottom: 10px;
        }
        #ai-platform-welcome .price-tag {
            background-color: var(--accent-color);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-weight: bold;
            display: inline-block;
            margin-bottom: 10px;
        }
        @media (max-width: 768px) {
            #ai-platform-welcome {
                padding: 15px;
            }
            #ai-platform-welcome .welcome-title {
                font-size: 2em;
            }
            #ai-platform-welcome .welcome-description {
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <div id="ai-platform-welcome">
        <div class="gradient-box">
            小白快速使用方法：点击"<a href="https://api.yyapi.fun/token">令牌</a>" <span class="arrow">→</span> 然后点击"添加新的令牌" <span class="arrow">→</span> 在弹出来的页面完成配置后 <span class="arrow">→</span> 新的令牌添加完成 <span class="arrow">→</span> 在新的令牌的右侧位置点击"聊天" <span class="arrow">→</span> 即可快速开始与AI聊天。
        </div>
        <div class="content">
            <div class="welcome-section">
                <h1 class="welcome-title floating-element">🎉 <font style="background: linear-gradient(to right, #3a5fcd, #6495ed); -webkit-background-clip: text; color: transparent;">欢迎光临我们的平台！</font></h1>
                <p class="welcome-description">以<span class="highlight">极低的价格</span>使用 GPT-4，我们已<span class="highlight">稳定运行1年</span>！我们的平台为您提供<span class="highlight">最新、最强大</span>的自然语言处理功能，支持 <strong>GPT 4.0全系列</strong>、<strong>GPT 3.5全系列</strong>、<strong>Claude3全系列</strong>、<strong>dalle-3绘画模型</strong>、<strong>DeepSeek全系列</strong>、<strong>豆包全系列</strong>、<strong>通义千问全系列</strong>、<strong>零一万物全系列</strong>、<strong>月之暗面全系列</strong>、<strong>智谱清言全系列</strong>等许多模型。快来体验吧！ 🚀</p>
                <h2>本站专供大饼AI变声器小羊饼智慧客服</h2>
                <p><strong>无限免费使用部分模型：</strong><a href="https://yyai.deno.dev">点击即用</a> （仅限开源模型，访问密码yuychat.cn）</p>
            </div>
            <div class="feature-box">
                <div class="feature-icon">💻 <strong>平台注册与登录<strong></div>
                <ul>
                    <li><strong>注册用户无限使用 </strong></li>
                    <li>专供大饼AI变声器小羊饼智慧客服</li>
                </ul>
            </div>
            <div class="feature-box">
                <div class="feature-icon">🌟 <strong>价格优势</strong>
                <small><div class="price-tag"><strong>0 ¥ / 1 $</strong></div></small></div>
                <h2><strong>专供大饼AI变声器小羊饼智慧客服 || 支持支付宝在线充值！</strong></h2>
                <a href="https://www.yuychat.cn/pricing" class="custom-gradient-button">点击查看支持的模型及其价格</a>
            </div>
            <div class="feature-box">
                <div class="feature-icon">🌍 <strong>常用主流模型推荐</strong></div>
                <ul>
                    <li>全球AI模型TOP1：<strong>claude-3-5-sonnet</strong></li>
                    <li>最具性价比模型：<strong>deepseek-chat</strong></li>
                    <li>稳定低价老牌模型：<strong>gpt-4o</strong></li>
                    <li>全球绘画模型TOP1：<strong>FLUX.1</strong></li>
                </ul>
                <p>模型能力实时更新：</strong><a href="https://livebench.ai">点击查看</a></p>
            </div>
            <div class="feature-box">
                <div class="feature-icon">📅 <strong>使用方法</strong></div>
                <ol>
                    <li>如果您想直接使用，请参考首页顶部内容。</li>
                    <li>如果您是其他客户端使用，代理地址填写<span class="highlight"> <strong>下列请求地址之一</strong></span>: 由于客户端地址不统一，如果上述地址不行请尝试以下两个地址：<span class="highlight"> <strong>下列请求地址之一</strong></span>/v1 或<span class="highlight"> <strong>下列请求地址之一</strong></span>/v1/chat/completions（Apikey请在您的令牌中查看，如果没有令牌请新建一个。）</li>
                </ol>
                <p>请求地址:</p>
                <pre>https://www.yuychat.cn</pre>
                <p></p>
                <h2><strong>对于开发者，代码方面，如何请求，怎么使用请参考<a href="https://openai.apifox.cn/api-67883981">点击查看</a></strong></h2>
            </div>
            <div class="feature-box">
                <div class="feature-icon">🎁 <strong>提示</strong></div>
                <ul>
                    <li>所有的<strong>赠送额度</strong>、<strong>奖励额度</strong>、<strong>兑换额度</strong>均与官方对应美刀的使用额度相等。</li>
                    <li>如果出现回复为空的情况，请检查您填写的模型名称是否正确(注意区分中英文"-")</li>
                    <li>🚫 提醒您：请严格遵守相关法律规定以及本站规定，如有违法违规提问，将会封禁您的账号。详见<a href="https://api.yyapi.fun/about">服务条款</a></li>
                </ul>
            </div>
        </div>
    </div>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/ScrollTrigger.min.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', (event) => {
            gsap.registerPlugin(ScrollTrigger);

            // Preloader animation
            gsap.to('body', { opacity: 1, duration: 1, ease: 'power2.inOut' });

            // Animate feature boxes
            const featureBoxes = document.querySelectorAll('#ai-platform-welcome .feature-box');
            featureBoxes.forEach((box, index) => {
                gsap.from(box, {
                    opacity: 0,
                    y: 50,
                    duration: 0.8,
                    ease: "power3.out",
                    scrollTrigger: {
                        trigger: box,
                        start: "top 80%",
                        end: "bottom 20%",
                        toggleActions: "play none none reverse"
                    }
                });
            });

            // Gradient box parallax effect
            const gradientBox = document.querySelector('#ai-platform-welcome .gradient-box');
            gradientBox.addEventListener('mousemove', (e) => {
                const rect = gradientBox.getBoundingClientRect();
                const x = (e.clientX - rect.left) / rect.width;
                const y = (e.clientY - rect.top) / rect.height;
                gsap.to(gradientBox, {
                    backgroundPosition: `${x * 100}% ${y * 100}%`,
                    duration: 0.5,
                    ease: "power2.out"
                });
            });

            // Welcome section background color change on scroll
            const welcomeSection = document.querySelector('#ai-platform-welcome .welcome-section');
            ScrollTrigger.create({
                trigger: welcomeSection,
                start: "top top",
                end: "bottom top",
                onUpdate: (self) => {
                    const progress = self.progress;
                    const color1 = [248, 249, 250]; // #f8f9fa
                    const color2 = [233, 236, 239]; // #e9ecef
                    const r = Math.round(color1[0] + (color2[0] - color1[0]) * progress);
                    const g = Math.round(color1[1] + (color2[1] - color1[1]) * progress);
                    const b = Math.round(color1[2] + (color2[2] - color1[2]) * progress);
                    welcomeSection.style.backgroundColor = `rgb(${r},${g},${b})`;
                }
            });

            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    gsap.to(window, {duration: 1, scrollTo: targetId, ease: "power2.inOut"});
                });
            });

            // Hover effect for feature boxes
            featureBoxes.forEach(box => {
                box.addEventListener('mouseenter', () => {
                    gsap.to(box, {scale: 1.03, duration: 0.3, ease: "power2.out"});
                });
                box.addEventListener('mouseleave', () => {
                    gsap.to(box, {scale: 1, duration: 0.3, ease: "power2.out"});
                });
            });

            // Parallax effect for welcome section
            gsap.to(".welcome-section", {
                backgroundPositionY: "30%",
                ease: "none",
                scrollTrigger: {
                    trigger: ".welcome-section",
                    start: "top bottom",
                    end: "bottom top",
                    scrub: true
                }
            });

            // Floating element animation
            gsap.to(".floating-element", {
                y: -20,
                duration: 1.5,
                ease: "power1.inOut",
                repeat: -1,
                yoyo: true
            });

            // Gradient box animation
            const gradientTimeline = gsap.timeline({repeat: -1});
            gradientTimeline.to('.gradient-box', {
                backgroundPosition: '100% 50%',
                duration: 15,
                ease: 'none'
            }).to('.gradient-box', {
                backgroundPosition: '0% 50%',
                duration: 15,
                ease: 'none'
            });

            // Custom gradient button animation
            const buttons = document.querySelectorAll('.custom-gradient-button');
            buttons.forEach(button => {
                button.addEventListener('mouseenter', () => {
                    gsap.to(button, {scale: 1.05, duration: 0.3, ease: "power2.out"});
                });
                button.addEventListener('mouseleave', () => {
                    gsap.to(button, {scale: 1, duration: 0.3, ease: "power2.out"});
                });
            });

            // Text reveal animation
            const textElements = document.querySelectorAll('.welcome-description, .feature-box p, .feature-box li');
            textElements.forEach(el => {
                gsap.from(el, {
                    opacity: 0,
                    y: 20,
                    duration: 0.8,
                    scrollTrigger: {
                        trigger: el,
                        start: 'top 90%',
                        end: 'bottom 10%',
                        toggleActions: 'play none none reverse'
                    }
                });
            });

            // Animate feature icons
            const featureIcons = document.querySelectorAll('.feature-icon');
            featureIcons.forEach(icon => {
                gsap.from(icon, {
                    scale: 0,
                    opacity: 0,
                    duration: 0.5,
                    ease: "back.out(1.7)",
                    scrollTrigger: {
                        trigger: icon,
                        start: "top 80%",
                        toggleActions: "play none none reverse"
                    }
                });
            });

            // Animate price tags
            const priceTags = document.querySelectorAll('.price-tag');
            priceTags.forEach(tag => {
                gsap.from(tag, {
                    scale: 0,
                    opacity: 0,
                    duration: 0.5,
                    ease: "elastic.out(1, 0.3)",
                    scrollTrigger: {
                        trigger: tag,
                        start: "top 80%",
                        toggleActions: "play none none reverse"
                    }
                });
            });

            // Add a subtle parallax effect to the background
            gsap.to("body", {
                backgroundPosition: "50% 100%",
                ease: "none",
                scrollTrigger: {
                    trigger: "body",
                    start: "top top",
                    end: "bottom top",
                    scrub: true
                }
            });

            // Animate highlights on scroll
            const highlights = document.querySelectorAll('.highlight');
            highlights.forEach(highlight => {
                gsap.from(highlight, {
                    backgroundSize: "0% 0.4em",
                    duration: 0.8,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: highlight,
                        start: "top 80%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
        });
    </script>
</body>
</html>
