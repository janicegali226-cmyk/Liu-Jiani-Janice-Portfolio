---
title: "Projects"
layout: archive
permalink: /projects/
classes: wide
---

Welcome to my project page!

{% assign data = site.data.projects %}

<div class="projects-container">
  {% for item in data %}
    <div class="project-card">
      <div class="project-image">
        <a href="{{ item.link }}" target="_blank">
          <img src="{{ item.image | relative_url }}" alt="{{ item.title }}">
        </a>
      </div>

      <div class="project-info">
        <h2 class="project-title no_toc">
          <a href="{{ item.link }}" target="_blank">
            {{ item.title }} <i class="fas fa-external-link-alt" aria-hidden="true" style="font-size: 0.6em;"></i>
          </a>
        </h2>
        <p class="project-excerpt">{{ item.excerpt }}</p>
        
        {% if item.tags %}
          <div class="project-tags">
            {% for tag in item.tags %}
              <span class="tag-label">{{ tag }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>

<style>
.project-card {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  margin-bottom: 3em;
  border-bottom: 1px solid #f2f3f3;
  padding-bottom: 2em;
  gap: 2em; /* 左右间距 */
}

.project-image {
  flex: 0 0 35%; /* 图片占据 35% 宽度，且不缩放 */
}

.project-image img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 1px 5px rgba(0,0,0,0.1);
}

.project-info {
  flex: 1; /* 文字占据剩余空间 */
}

.project-title {
  margin-top: 0 !important;
  font-size: 1.5rem !important;
}

.tag-label {
  display: inline-block;
  background: #f2f3f3;
  color: #494e52;
  padding: 2px 10px;
  border-radius: 4px;
  font-size: 0.8rem;
  margin-right: 8px;
  margin-top: 5px;
}

/* 响应式设计：手机端自动改为上下堆叠 */
@media (max-width: 600px) {
  .project-card {
    flex-direction: column;
  }
  .project-image {
    width: 100%;
    margin-bottom: 1em;
  }
}
</style>
