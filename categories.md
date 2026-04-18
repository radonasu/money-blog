---
layout: default
title: カテゴリから探す
permalink: /categories/
---

<div class="categories-hero">
  <h1 class="categories-title">カテゴリから探す</h1>
  <p class="categories-sub">全{{ site.posts | size }}記事を6つのテーマに分けて紹介しています。</p>
</div>

<div class="categories-nav">
  <a href="#setsuzei" class="cat-nav-chip cat-nav-blue">💴 節税</a>
  <a href="#toushi" class="cat-nav-chip cat-nav-green">📈 投資・NISA・iDeCo</a>
  <a href="#hojokin" class="cat-nav-chip cat-nav-orange">🏛️ 補助金・助成金</a>
  <a href="#jutaku" class="cat-nav-chip cat-nav-purple">🏠 住宅・ローン</a>
  <a href="#hoken" class="cat-nav-chip cat-nav-red">🛡️ 保険・相続</a>
  <a href="#fukugyo" class="cat-nav-chip cat-nav-teal">💼 副業・フリーランス</a>
</div>

<section id="setsuzei" class="cat-section">
  <h2 class="cat-section-heading cat-heading-blue"><span class="cat-emoji">💴</span> 節税</h2>
  <p class="cat-section-desc">サラリーマン・個人事業主・経営者向けの合法的な節税テクニック</p>
  <div class="cat-post-list">
  {% assign keywords = "節税,税金,控除,ふるさと納税,確定申告,所得税,住民税,年末調整" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>

<section id="toushi" class="cat-section">
  <h2 class="cat-section-heading cat-heading-green"><span class="cat-emoji">📈</span> 投資・NISA・iDeCo</h2>
  <p class="cat-section-desc">非課税制度を活用して資産を増やすための実践ガイド</p>
  <div class="cat-post-list">
  {% assign keywords = "投資,NISA,iDeCo,株式,ETF,投信,つみたて,積立,資産形成,証券,シミュレーション,インデックス,S&P,ポートフォリオ,運用" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>

<section id="hojokin" class="cat-section">
  <h2 class="cat-section-heading cat-heading-orange"><span class="cat-emoji">🏛️</span> 補助金・助成金</h2>
  <p class="cat-section-desc">中小企業・個人事業主・サラリーマンが使える公的支援制度</p>
  <div class="cat-post-list">
  {% assign keywords = "補助金,助成金,給付金,公的支援,IT導入,事業再構築,ものづくり,小規模事業者,キャリアアップ" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>

<section id="jutaku" class="cat-section">
  <h2 class="cat-section-heading cat-heading-purple"><span class="cat-emoji">🏠</span> 住宅・ローン</h2>
  <p class="cat-section-desc">住宅ローン・繰り上げ返済・金利見直しの最適戦略</p>
  <div class="cat-post-list">
  {% assign keywords = "住宅,ローン,マンション,持ち家,賃貸,不動産,繰り上げ,金利,団信,フラット35" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>

<section id="hoken" class="cat-section">
  <h2 class="cat-section-heading cat-heading-red"><span class="cat-emoji">🛡️</span> 保険・相続</h2>
  <p class="cat-section-desc">生命保険・医療保険の見直しと相続税の完全ガイド</p>
  <div class="cat-post-list">
  {% assign keywords = "保険,相続,贈与,遺言,終活,医療保険,生命保険,共済,自動車保険,火災保険,がん保険" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>

<section id="fukugyo" class="cat-section">
  <h2 class="cat-section-heading cat-heading-teal"><span class="cat-emoji">💼</span> 副業・フリーランス</h2>
  <p class="cat-section-desc">副業収入・フリーランスの確定申告・経費計上の実践知識</p>
  <div class="cat-post-list">
  {% assign keywords = "副業,フリーランス,個人事業,開業,青色申告,白色申告,経費,freee,マネーフォワード" | split: "," %}
  {% for post in site.posts %}
    {% assign match = false %}
    {% for kw in keywords %}
      {% if post.title contains kw or post.categories contains kw %}{% assign match = true %}{% endif %}
    {% endfor %}
    {% if match %}
    <a class="cat-post-item" href="{{ post.url | relative_url }}">
      <span class="cat-post-date">{{ post.date | date: "%m/%d" }}</span>
      <span class="cat-post-title">{{ post.title }}</span>
      <span class="cat-post-arrow">→</span>
    </a>
    {% endif %}
  {% endfor %}
  </div>
</section>
