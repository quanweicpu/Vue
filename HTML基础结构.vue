<template>
    <div class="container">
      <!-- 个人信息部分 -->
      <header>
        <!-- 个人头像，使用占位图，替换为你自己的头像 -->
        <img :src="profilePicture" alt="我的头像">
        <!-- 姓名，使用 h1 标签 -->
        <h1>{{ name }}</h1>
        <!-- 个人简介，使用 p 标签 -->
        <p>{{ intro }}</p>
      </header>
  
      <!-- 联系方式部分 -->
      <section class="contact-info">
        <!-- 小标题：联系方式 -->
        <div class="section-title">联系方式</div>
        <!-- 联系方式：使用 v-for 渲染 p 标签 -->
        <p v-for="(info, key) in contactInfo" :key="key">{{ key }}: {{ info }}</p>
        <!-- 个人网站：使用 a 标签做超链接 -->
        <p>个人网站：<a :href="website" target="_blank">www.example.com</a></p>
      </section>
  
      <!-- 教育背景部分 -->
      <section class="education">
        <!-- 小标题：教育背景 -->
        <div class="section-title">教育背景</div>
        <!-- 教育信息，使用 p 标签 -->
        <p><strong>{{ education.school }}</strong> - {{ education.major }} ({{ education.start }} - {{ education.end }})</p>
      </section>
  
      <!-- 技能部分 -->
      <section class="skills">
        <!-- 小标题：技能 -->
        <div class="section-title">技能</div>
        <!-- 技能列表，使用 v-for 渲染 -->
        <ul>
          <li v-for="(skill, index) in skills" :key="index">{{ skill }}</li>
        </ul>
      </section>
  
      <!-- 工作经历部分 -->
      <section class="experience">
        <!-- 小标题：工作经历 -->
        <div class="section-title">工作经历</div>
        <p><strong>{{ experience.position }}</strong> - {{ experience.company }} ({{ experience.start }} - {{ experience.end }})</p>
        <ul>
          <li v-for="(task, index) in experience.tasks" :key="index">{{ task }}</li>
        </ul>
      </section>
  
      <!-- 项目经验部分 -->
      <section class="projects">
        <!-- 小标题：项目经验 -->
        <div class="section-title">项目经验</div>
        <p><strong>{{ projects.name }}</strong></p>
        <ul>
          <li v-for="(project, index) in projects.tasks" :key="index">{{ project }}</li>
        </ul>
      </section>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // 个人信息
  const profilePicture = 'https://via.placeholder.com/150';
  const name = '张三';
  const intro = '电子商务专业 | Web 开发爱好者';
  
  // 联系信息
  const contactInfo = {
    电话: '**********',
    邮箱: '**************.com',
    地址: '*******'
  };
  const website = 'https://www.example.com';
  
  // 教育背景
  const education = {
    school: '****',
    major: '电子商务专业',
    start: '2018',
    end: '2022'
  };
  
  // 技能列表
  const skills = ['HTML/CSS/JavaScript', 'React', 'Node.js', '数据库：MySQL, MongoDB', 'Git版本控制'];
  
  // 工作经历
  const experience = {
    position: '前端开发实习生',
    company: '腾讯公司',
    start: '2021年6月',
    end: '2021年9月',
    tasks: [
      '参与公司内部项目的前端开发，使用 React 实现功能模块。',
      '优化网站性能，提升用户体验。'
    ]
  };
  
  // 项目经验
  const projects = {
    name: '在线商城平台',
    tasks: [
      '使用 HTML, CSS, JavaScript 实现电商网站前端页面。',
      '实现商品列表展示、购物车功能、订单结算流程。',
      '使用 Ajax 动态加载商品数据。'
    ]
  };
  </script>
  
  <style scoped>
  body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
  }
  .container {
    width: 80%;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  header {
    text-align: center;
  }
  header img {
    border-radius: 50%;
    width: 150px;
    height: 150px;
  }
  h1 {
    color: #333;
  }
  .section-title {
    font-size: 1.5em;
    color: #007BFF;
    margin-top: 20px;
  }
  .contact-info p {
    margin: 5px 0;
  }
  </style>
  