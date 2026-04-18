---
layout: default
title: カテゴリから探す
permalink: /categories/
---

<div class="categories-hero">
  <h1 class="categories-title">カテゴリから探す</h1>
  <p class="categories-sub">全{{ site.posts | size }}記事を7つのテーマに分けて紹介しています。</p>
</div>

<div class="categories-nav">
  <a href="#setsuzei"  class="cat-nav-chip cat-nav-blue">💴 節税</a>
  <a href="#toushi"    class="cat-nav-chip cat-nav-green">📈 投資・NISA・iDeCo</a>
  <a href="#hojokin"   class="cat-nav-chip cat-nav-orange">🏛️ 補助金・助成金</a>
  <a href="#jutaku"    class="cat-nav-chip cat-nav-purple">🏠 住宅・ローン</a>
  <a href="#hoken"     class="cat-nav-chip cat-nav-red">🛡️ 保険・相続</a>
  <a href="#fukugyo"   class="cat-nav-chip cat-nav-teal">💼 副業・フリーランス</a>
  <a href="#setsuyaku" class="cat-nav-chip cat-nav-pink">🛒 節約・家計</a>
</div>

{% assign cats = "setsuzei,toushi,hojokin,jutaku,hoken,fukugyo,setsuyaku" | split: "," %}
{% assign labels = "💴 節税|📈 投資・NISA・iDeCo|🏛️ 補助金・助成金|🏠 住宅・ローン|🛡️ 保険・相続|💼 副業・フリーランス|🛒 節約・家計" | split: "|" %}
{% assign descs = "サラリーマン・個人事業主・経営者向けの合法的な節税テクニック|非課税制度を活用して資産を増やすための実践ガイド|中小企業・個人事業主・サラリーマンが使える公的支援制度|住宅ローン・繰り上げ返済・金利見直しの最適戦略|生命保険・医療保険の見直しと相続税の完全ガイド|副業収入・フリーランスの確定申告・経費計上の実践知識|節約・貯金・ポイント活用・キャッシュレスで家計を最適化" | split: "|" %}
{% assign colors = "blue,green,orange,purple,red,teal,pink" | split: "," %}

{% for slug in cats %}
{% assign i = forloop.index0 %}
{% assign matched = site.posts | where: "primary_category", slug %}
<section id="{{ slug }}" class="cat-section">
  <h2 class="cat-section-heading cat-heading-{{ colors[i] }}">
    <span class="cat-emoji">{{ labels[i] | slice: 0, 2 }}</span>
    <span>{{ labels[i] | slice: 2, 100 | strip }}</span>
    <span class="cat-count">{{ matched | size }}記事</span>
  </h2>
  <p class="cat-section-desc">{{ descs[i] }}</p>
  <div class="cat-post-list">
  {% if matched.size == 0 %}
    <div class="cat-empty">このカテゴリにはまだ記事がありません。</div>
  {% else %}
  {% for post in matched %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
  {% endfor %}
  {% endif %}
  </div>
</section>
{% endfor %}
