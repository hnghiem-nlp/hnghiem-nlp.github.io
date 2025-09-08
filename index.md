---
layout: home
title: "Huy Nghiem"
---

I’m a PhD student at the University of Maryland working at the intersection of **NLP**, **fairness**, and **causal methods**.  
My current work studies how large language models justify decisions in **college admissions** and **content moderation**, with a focus on structured rationales, counterfactual evaluation, and bias auditing.

I collaborate across **NLP + HCI + causal inference**, building pipelines for data generation, alignment (DPO/KTO/GRPO), and explanation analysis at scale.

## Selected Publications

{%- comment -%}
Shows up to 4 papers marked `selected: true` in /_publications/*.  
Swap the placeholder thumbnails later by replacing files in /assets/img/papers/.
{%- endcomment -%}

{%- assign featured = site.publications
   | where_exp: "p", "p.selected == true"
   | sort: "year" | reverse -%}

<div class="paper-grid">
  {%- for pub in featured limit:4 -%}
  <a class="paper-card" href="{{ pub.pdf | default: pub.paperurl | default: pub.url | relative_url }}" target="_blank" rel="noopener">
    <div class="pc-thumb">
      {%- if pub.image -%}
        <img src="{{ pub.image | relative_url }}" alt="{{ pub.title | escape }}">
      {%- else -%}
        <div class="pc-thumb-fallback">📄</div>
      {%- endif -%}
    </div>
    <div class="pc-body">
      <div class="pc-venue">
        {%- if pub.venue -%}{{ pub.venue }}{%- endif -%}
        {%- if pub.year -%}{% if pub.venue %} · {% endif %}{{ pub.year }}{%- endif -%}
      </div>
      <div class="pc-title">{{ pub.title }}</div>
      {%- if pub.authors -%}
      <div class="pc-authors">{{ pub.authors }}</div>
      {%- endif -%}
      {%- if pub.excerpt or pub.abstract -%}
      <div class="pc-excerpt">{{ pub.excerpt | default: pub.abstract }}</div>
      {%- endif -%}
      <div class="pc-tags">
        {%- if pub.pdf or pub.paperurl -%}<span class="pc-tag">paper</span>{%- endif -%}
        {%- if pub.code -%}<span class="pc-tag">code</span>{%- endif -%}
      </div>
    </div>
  </a>
  {%- endfor -%}
</div>

<p><a href="{{ '/publications/' | relative_url }}">All publications →</a></p>

## News

<ul class="news-list">
{%- for post in site.posts limit:5 -%}
  <li>
    <strong>{{ post.date | date: "%b %Y" }}</strong> —
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{%- endfor -%}
</ul>
<p><a href="{{ '/year-archive/' | relative_url }}">All updates →</a></p>
