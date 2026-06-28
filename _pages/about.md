---
permalink: /
title: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

  <div class="section-title">About</div>
<section class="profile-panel">
  <p>I am a Ph.D. student in Computing Science at <a href="https://www.sfu.ca/">Simon Fraser University</a>, advised by <a href="https://cs.sfu.ca/~jcliu/">Prof. Jiangchuan Liu</a>. I started my Ph.D. in 2023.</p>
  <p>My research spans applied artificial intelligence and networked systems, with a recent focus on Physical AI for challenging field environments.</p>
  <p>I am a core technical contributor to the <a href="https://salmonvision.org/">SalmonVision</a> collaborative, where we develop deployable ecological AI pipelines for wild salmon monitoring and stewardship.</p>
</section>

<section class="academic-section">
  <div class="section-title">Research</div>

  <img class="research-sketch" src="{{ '/images/research-sketch.png' | relative_url }}" alt="Research overview sketch">
</section>

<section class="academic-section">
  <div class="section-title">Recent Publications</div>

  <div class="publication-list">
  {% for pub in site.data.selected_publications %}
    <article class="publication" id="{{ pub.key }}">
      <div class="publication-tag">{{ pub.tag | default: pub.short_venue }}</div>
      <div class="publication-content">
        <span class="publication-title">{{ pub.title }}</span>
        <br>
        {{ pub.authors }}
      </div>
    </article>
  {% endfor %}
  </div>
</section>
