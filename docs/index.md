---
layout: home
hero:
  name: "您好！欢迎您的到来"
  text: "我的技术简历已经在这里等你很久喽"
  tagline: 现在点击下方按钮，查看我的全栈开发能力吧
  actions:
    - theme: brand
      text: 进入简历
      link: /resume
---

<style>
/* 整体页面样式 */
.VPHome {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  min-height: 100vh;
  position: relative;
  overflow: hidden;
}

/* 缓慢移动的光点 */
.floating-dots {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 1;
}

.floating-dot {
  position: absolute;
  width: 2px;
  height: 2px;
  background: rgba(255, 255, 255, 0.4);
  border-radius: 50%;
  animation: floatDot 20s linear infinite;
}

/* 代码符号 */
.code-symbol {
  position: absolute;
  color: rgba(255, 255, 255, 0.2);
  font-size: 16px;
  font-family: 'Courier New', monospace;
  font-weight: bold;
  z-index: 1;
}

.symbol-1 {
  top: 20%;
  left: 5%;
}

.symbol-2 {
  bottom: 20%;
  right: 5%;
}

/* 添加背景动画元素 */
.VPHome::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.2) 0%, transparent 50%);
  animation: float 6s ease-in-out infinite;
}

/* 英雄区域优化 - 绝对居中 */
.VPHomeHero {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  text-align: center;
  width: 100%;
  padding: 0 1rem;
}

/* 名称样式 - 淡入+上移 */
.VPHomeHero .name {
  font-size: 3.5rem;
  font-weight: 700;
  background: linear-gradient(45deg, #fff, #e3f2fd);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 1rem;
  text-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  animation: fadeInUp 0.5s ease-out forwards;
  opacity: 0;
}

/* 主文本样式 - 延迟0.2秒 */
.VPHomeHero .text {
  font-size: 2rem;
  font-weight: 600;
  color: #fff;
  margin-bottom: 1.5rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  animation: fadeInUp 0.5s ease-out 0.2s forwards;
  opacity: 0;
}

/* 标签行样式 - 延迟0.4秒 */
.VPHomeHero .tagline {
  font-size: 1.2rem;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 3rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
  animation: fadeInUp 0.5s ease-out 0.4s forwards;
  opacity: 0;
}

/* 按钮容器 - 延迟0.6秒 */
.VPHomeHero .actions {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
  animation: fadeInUp 0.5s ease-out 0.6s forwards;
  opacity: 0;
}

/* 主要按钮样式 */
.VPHomeHero .action.brand {
  background: linear-gradient(45deg, #ff6b6b, #ffa726);
  border: none;
  border-radius: 50px;
  padding: 1rem 2.5rem;
  font-size: 1.1rem;
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
  position: relative;
  overflow: hidden;
}

.VPHomeHero .action.brand::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  transition: left 0.5s;
}

.VPHomeHero .action.brand:hover::before {
  left: 100%;
}

.VPHomeHero .action.brand:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(255, 107, 107, 0.6);
}

/* 技能标签浮动动画 */
.skills-floating {
  position: absolute;
  color: rgba(255, 255, 255, 0.1);
  font-size: 0.9rem;
  font-weight: 500;
  animation: floatAround 15s linear infinite;
  z-index: 1;
}

/* 动画定义 */
@keyframes fadeInUp {
  0% { 
    opacity: 0; 
    transform: translateY(20px); 
  }
  100% { 
    opacity: 1; 
    transform: translateY(0); 
  }
}

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(180deg); }
}

@keyframes floatAround {
  0% { 
    transform: translate(0, 0) rotate(0deg); 
    opacity: 0;
  }
  10% { opacity: 0.3; }
  50% { 
    transform: translate(100px, -50px) rotate(180deg); 
    opacity: 0.6;
  }
  90% { opacity: 0.3; }
  100% { 
    transform: translate(0, 0) rotate(360deg); 
    opacity: 0;
  }
}

/* 光点浮动动画 */
@keyframes floatDot {
  0% {
    transform: translate(0, 0);
  }
  25% {
    transform: translate(10px, 10px);
  }
  50% {
    transform: translate(5px, 20px);
  }
  75% {
    transform: translate(-5px, 15px);
  }
  100% {
    transform: translate(0, 0);
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .VPHomeHero .name {
    font-size: 2.5rem;
  }
  
  .VPHomeHero .text {
    font-size: 1.5rem;
  }
  
  .VPHomeHero .tagline {
    font-size: 1.1rem;
    padding: 0 1rem;
  }
  
  .VPHomeHero .actions {
    flex-direction: column;
    align-items: center;
  }
  
  .VPHomeHero .action {
    width: 80%;
    text-align: center;
  }
}

/* 滚动指示器 - 放在按钮上方 */
.scroll-indicator {
  position: absolute;
  bottom: 120px; /* 放在按钮上方 */
  left: 50%;
  transform: translateX(-50%);
  color: rgba(255, 255, 255, 0.7);
  animation: bounce 2s infinite;
  z-index: 2;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  40% {
    transform: translateX(-50%) translateY(-10px);
  }
  60% {
    transform: translateX(-50%) translateY(-5px);
  }
}
</style>

<!-- 添加浮动光点 -->
<div class="floating-dots">
  <div class="floating-dot" style="top: 10%; left: 15%; animation-delay: 0s;"></div>
  <div class="floating-dot" style="top: 20%; left: 80%; animation-delay: -2s;"></div>
  <div class="floating-dot" style="top: 40%; left: 25%; animation-delay: -4s;"></div>
  <div class="floating-dot" style="top: 60%; left: 70%; animation-delay: -6s;"></div>
  <div class="floating-dot" style="top: 80%; left: 40%; animation-delay: -8s;"></div>
  <div class="floating-dot" style="top: 30%; left: 60%; animation-delay: -10s;"></div>
</div>

<!-- 添加代码符号 -->
<div class="code-symbol symbol-1">&lt;/&gt;</div>
<div class="code-symbol symbol-2">//</div>

<!-- 添加浮动技能标签 -->
<div class="skills-floating" style="top: 20%; left: 10%; animation-delay: 0s;">Vue.js</div>
<div class="skills-floating" style="top: 30%; right: 15%; animation-delay: -2s;">React</div>
<div class="skills-floating" style="top: 60%; left: 15%; animation-delay: -4s;">Node.js</div>
<div class="skills-floating" style="top: 70%; right: 10%; animation-delay: -6s;">TypeScript</div>
<div class="skills-floating" style="top: 40%; left: 5%; animation-delay: -8s;">Python</div>

<!-- 滚动指示器 - 放在按钮上方 -->
<div class="scroll-indicator">
  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
    <path d="M12 5v14M19 12l-7 7-7-7"/>
  </svg>
</div>
