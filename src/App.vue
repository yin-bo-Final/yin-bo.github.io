<template>
  <div id="app">
    <!-- 导航栏 -->
    <nav class="navbar">
      <div class="nav-container">
        <div class="nav-logo">
          <h2>Yin-Bo</h2>
        </div>
        <ul class="nav-menu">
          <li class="nav-item">
            <a href="#home" class="nav-link">首页</a>
          </li>
          <li class="nav-item">
            <a href="#about" class="nav-link">关于我</a>
          </li>
          <li class="nav-item">
            <a href="#projects" class="nav-link">项目</a>
          </li>
          <li class="nav-item">
            <a href="#contact" class="nav-link">联系</a>
          </li>
        </ul>
      </div>
    </nav>

    <!-- 主要内容区域 -->
    <main>
      <!-- 首页部分 -->
      <section id="home" class="hero-section">
        <div class="hero-content">
          <h1 class="hero-title">欢迎来到我的个人网站</h1>
          <p class="hero-subtitle">前端开发者 | 技术爱好者 | 创作者</p>
          <div class="hero-buttons">
            <button class="btn btn-primary">了解更多</button>
            <button class="btn btn-secondary">查看项目</button>
          </div>
        </div>
        <div class="hero-image">
          <div class="avatar-placeholder">
            <span>👨‍💻</span>
          </div>
        </div>
      </section>

      <!-- 关于我部分 -->
      <section id="about" class="about-section">
        <div class="container">
          <h2 class="section-title">关于我</h2>
          <div class="about-content">
            <div class="about-text">
              <p>我是一名充满激情的前端开发者，热爱创造优秀的用户体验。</p>
              <p>技术栈包括：Vue.js, React, JavaScript, CSS3, HTML5等。</p>
              <div class="skills">
                <span class="skill-tag">Vue.js</span>
                <span class="skill-tag">React</span>
                <span class="skill-tag">JavaScript</span>
                <span class="skill-tag">CSS3</span>
                <span class="skill-tag">HTML5</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- 项目部分 -->
      <section id="projects" class="projects-section">
        <div class="container">
          <h2 class="section-title">我的项目</h2>
          <div class="projects-grid">
            <div class="project-card">
              <div class="project-image">
                <div class="project-placeholder">📱</div>
              </div>
              <div class="project-content">
                <h3>个人网站</h3>
                <p>使用Vue 3构建的现代化个人网站</p>
                <div class="project-tags">
                  <span>Vue 3</span>
                  <span>Vite</span>
                  <span>CSS3</span>
                </div>
              </div>
            </div>
            <div class="project-card">
              <div class="project-image">
                <div class="project-placeholder">🎮</div>
              </div>
              <div class="project-content">
                <h3>游戏应用</h3>
                <p>基于Web技术的互动游戏应用</p>
                <div class="project-tags">
                  <span>JavaScript</span>
                  <span>Canvas</span>
                  <span>HTML5</span>
                </div>
              </div>
            </div>
            <div class="project-card">
              <div class="project-image">
                <div class="project-placeholder">📊</div>
              </div>
              <div class="project-content">
                <h3>数据可视化</h3>
                <p>数据展示和分析工具</p>
                <div class="project-tags">
                  <span>Chart.js</span>
                  <span>Vue</span>
                  <span>API</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- 联系部分 -->
      <section id="contact" class="contact-section">
        <div class="container">
          <h2 class="section-title">联系我</h2>
          <div class="contact-content">
            <div class="contact-info">
              <div class="contact-item">
                <span class="contact-icon">📧</span>
                <span>邮箱：your.email@example.com</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">🌐</span>
                <span>网站：yin-bo.github.io</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">📱</span>
                <span>微信：your-wechat</span>
              </div>
            </div>
            <div class="social-links">
              <a href="https://space.bilibili.com/205429568" class="social-link" target="_blank">
                <span>📺 Bilibili</span>
              </a>
              <a href="https://github.com/yin-bo" class="social-link" target="_blank">
                <span>🐙 GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- 页脚 -->
    <footer class="footer">
      <div class="container">
        <p>&copy; 2024 Yin-Bo. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  mounted() {
    // 平滑滚动效果
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
        }
      });
    });
  }
}
</script>
