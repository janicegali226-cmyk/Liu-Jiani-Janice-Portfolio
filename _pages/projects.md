---
title: "Projects"
layout: archive
permalink: /projects/
classes: wide
---

Welcome to my project page! The following are my practical achievements in business analysis and data visualization.

{% assign data = site.data.projects %}

<div class="entries-grid">
  {% for item in data %}
    <div class="list__item">
      <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
        
        <div class="archive__item-teaser">
          <a href="{{ item.link }}" target="_blank">
            <img src="{{ item.image | relative_url }}" alt="{{ item.title }}">
          </a>
        </div>

        <h2 class="archive__item-title no_toc" itemprop="headline">
          <a href="{{ item.link }}" target="_blank" rel="noopener noreferrer">
            {{ item.title }} <i class="fas fa-external-link-alt" aria-hidden="true" style="font-size: 0.7em;"></i>
          </a>
        </h2>

        <div class="archive__item-excerpt" itemprop="description">
          <p>{{ item.excerpt }}</p>
        </div>

        {% if item.tags %}
          <p class="page__taxonomy">
            <strong><i class="fas fa-fw fa-tags" aria-hidden="true"></i> Tags: </strong>
            <span itemprop="keywords">
              {% for tag in item.tags %}
                <span class="page__taxonomy-item" style="background: #f2f3f3; padding: 2px 8px; border-radius: 4px; margin-right: 5px;">{{ tag }}</span>
              {% endfor %}
            </span>
          </p>
        {% endif %}

      </article>
    </div>
  {% endfor %}
</div>
