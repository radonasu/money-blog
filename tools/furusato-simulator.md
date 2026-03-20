---
layout: default
title: "ふるさと納税 控除上限額シミュレーター【2026年版】年収・家族構成から自動計算"
description: "ふるさと納税の控除上限額を年収・家族構成・住宅ローン有無で自動計算。2026年最新の税制に対応。損しない寄付額の目安がすぐわかります。"
permalink: /tools/furusato-simulator/
---

<div class="tool-page">

<div class="tool-hero">
  <div class="tool-hero-inner">
    <div class="tool-badge">無料シミュレーター</div>
    <h1 class="tool-title">ふるさと納税 控除上限額シミュレーター</h1>
    <p class="tool-subtitle">年収・家族構成を選ぶだけで<br>「損しない寄付の上限額」を自動計算します</p>
  </div>
</div>

<div class="tool-container">

  <div class="tool-main">

    <div class="sim-card">
      <h2 class="sim-card-title">📝 条件を入力</h2>

      <div class="input-group">
        <label for="ft-income">年収（額面・給与収入）</label>
        <div class="input-row">
          <input type="range" id="ft-income-range" min="200" max="3000" step="50" value="500">
          <div class="input-display">
            <input type="number" id="ft-income" value="500" min="200" max="3000" step="50">
            <span class="unit">万円</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label>家族構成</label>
        <div class="radio-group">
          <label class="radio-label"><input type="radio" name="family" value="single" checked> 独身・共働き（配偶者控除なし）</label>
          <label class="radio-label"><input type="radio" name="family" value="spouse"> 専業主婦（夫）あり</label>
          <label class="radio-label"><input type="radio" name="family" value="child1"> 共働き＋子1人（16歳未満）</label>
          <label class="radio-label"><input type="radio" name="family" value="child2"> 共働き＋子2人（16歳未満）</label>
          <label class="radio-label"><input type="radio" name="family" value="spouse-child1"> 専業主婦（夫）＋子1人（16歳未満）</label>
        </div>
      </div>

      <div class="input-group">
        <label>住宅ローン控除</label>
        <div class="radio-group">
          <label class="radio-label"><input type="radio" name="loan" value="none" checked> なし</label>
          <label class="radio-label"><input type="radio" name="loan" value="low"> あり（年間控除額 10万円以下）</label>
          <label class="radio-label"><input type="radio" name="loan" value="mid"> あり（年間控除額 10〜20万円）</label>
          <label class="radio-label"><input type="radio" name="loan" value="high"> あり（年間控除額 20万円超）</label>
        </div>
        <p class="input-note">住宅ローン控除が大きいと、所得税が少なくなりふるさと納税の上限が下がることがあります</p>
      </div>
    </div>

    <div class="result-card" id="ft-result-card">
      <h2 class="sim-card-title">📊 計算結果</h2>

      <div class="result-highlight">
        <div class="result-main-item">
          <span class="result-main-label">控除上限額（目安）</span>
          <span class="result-main-value" id="ft-limit">—</span>
        </div>
        <div class="result-main-item accent-gold">
          <span class="result-main-label">実質負担額（自己負担2,000円）</span>
          <span class="result-main-value" id="ft-burden">—</span>
        </div>
      </div>

      <div class="result-breakdown">
        <div class="breakdown-row">
          <span class="breakdown-label">おすすめ寄付額（上限の90%）</span>
          <span class="breakdown-value green" id="ft-recommend">—</span>
        </div>
        <div class="breakdown-row">
          <span class="breakdown-label">控除される住民税（目安）</span>
          <span class="breakdown-value" id="ft-jumin">—</span>
        </div>
        <div class="breakdown-row">
          <span class="breakdown-label">控除される所得税（目安）</span>
          <span class="breakdown-value" id="ft-shotoku">—</span>
        </div>
      </div>

      <div class="furusato-visual">
        <div class="fv-row">
          <div class="fv-label">寄付額</div>
          <div class="fv-bar-wrap">
            <div class="fv-bar fv-blue" id="fv-bar" style="width:100%">
              <span id="fv-donation-label">—</span>
            </div>
          </div>
        </div>
        <div class="fv-row">
          <div class="fv-label">戻ってくる</div>
          <div class="fv-bar-wrap">
            <div class="fv-bar fv-green" id="fv-return-bar" style="width:98%">
              <span id="fv-return-label">—</span>
            </div>
          </div>
        </div>
        <div class="fv-row">
          <div class="fv-label">実質負担</div>
          <div class="fv-bar-wrap">
            <div class="fv-bar fv-red" style="width:2%">
              <span>2,000円</span>
            </div>
          </div>
        </div>
      </div>

      <div class="result-note">
        <p>⚠️ ワンストップ特例制度を使う場合：寄付先は<strong>5自治体以内</strong>に絞ってください。6自治体以上は確定申告が必要です。</p>
      </div>
    </div>

    <div class="step-card">
      <h2 class="sim-card-title">🚀 ふるさと納税のやり方（3ステップ）</h2>
      <div class="steps">
        <div class="step">
          <div class="step-num">1</div>
          <div class="step-body">
            <strong>上限額を確認する</strong>
            <p>このシミュレーターで控除上限額を把握する</p>
          </div>
        </div>
        <div class="step">
          <div class="step-num">2</div>
          <div class="step-body">
            <strong>お気に入りの返礼品を選ぶ</strong>
            <p>ふるさとチョイス・楽天ふるさと納税などで寄付する</p>
          </div>
        </div>
        <div class="step">
          <div class="step-num">3</div>
          <div class="step-body">
            <strong>ワンストップ特例を申請</strong>
            <p>自治体から届く申請書に記入して返送（5自治体以内なら確定申告不要）</p>
          </div>
        </div>
      </div>
    </div>

    <div class="cta-card">
      <h3>おすすめのふるさと納税サイト</h3>
      <p>ポイント還元があってお得。楽天経済圏の方は楽天ふるさと納税が最もポイントが貯まります。</p>
      <div class="cta-buttons">
        <a href="https://www.rakuten.co.jp/furusato/" class="cta-btn cta-primary" target="_blank" rel="noopener sponsored">楽天ふるさと納税で探す →</a>
        <a href="https://www.furusato-tax.jp/" class="cta-btn cta-secondary" target="_blank" rel="noopener sponsored">ふるさとチョイスで探す →</a>
      </div>
    </div>

    <div class="sim-card">
      <p style="font-size:13px;color:#94a3b8;">※本シミュレーターは給与所得者を対象とした目安計算です。副業収入・医療費控除・その他の控除がある場合は実際の上限額と異なります。確定申告をする場合は税理士にご相談ください。</p>
    </div>

  </div>

  <aside class="tool-sidebar">
    <div class="sidebar-widget">
      <h3 class="widget-title">🔗 関連シミュレーター</h3>
      <ul class="sidebar-links">
        <li><a href="/money-blog/tools/ideco-simulator/">iDeCo 節税シミュレーター</a></li>
        <li><a href="/money-blog/tools/jutaku-loan-simulator/">住宅ローン繰り上げ返済計算</a></li>
      </ul>
    </div>
    <div class="sidebar-widget">
      <h3 class="widget-title">📚 関連記事</h3>
      <ul class="sidebar-post-list">
        {% for post in site.posts %}
          {% if post.title contains 'ふるさと' or post.title contains '節税' %}
          <li><a href="{{ post.url | relative_url }}">{{ post.title | truncate: 35 }}</a></li>
          {% endif %}
        {% endfor %}
      </ul>
    </div>
  </aside>

</div>
</div>

<script>
const fmt = n => Math.round(n).toLocaleString('ja-JP') + '円';

// 給与所得控除（2026年）
function getKyuyoKoujo(income) {
  if (income <= 162.5) return 55;
  if (income <= 180)   return income * 0.4 - 10;
  if (income <= 360)   return income * 0.3 + 8;
  if (income <= 660)   return income * 0.2 + 44;
  if (income <= 850)   return income * 0.1 + 110;
  return 195;
}

// 基礎控除
const KISO_KOUJO = 48;

// 所得税率
function getIncomeTax(taxable) {
  if (taxable <= 195)  return taxable * 0.05;
  if (taxable <= 330)  return taxable * 0.10 - 9.75;
  if (taxable <= 695)  return taxable * 0.20 - 42.75;
  if (taxable <= 900)  return taxable * 0.23 - 63.6;
  if (taxable <= 1800) return taxable * 0.33 - 153.6;
  if (taxable <= 4000) return taxable * 0.40 - 279.6;
  return taxable * 0.45 - 479.6;
}

function calcFurusato() {
  const income = parseFloat(document.getElementById('ft-income').value) || 500;
  const family = document.querySelector('input[name="family"]:checked').value;
  const loan = document.querySelector('input[name="loan"]:checked').value;

  // 配偶者控除
  const spouseKoujo = (family === 'spouse' || family === 'spouse-child1') ? 38 : 0;

  // 扶養控除（16歳未満は児童手当のため扶養控除なし）
  // 16歳未満の子は控除なし
  const dependentKoujo = 0;

  // 給与所得
  const kyuyoShotoku = income - getKyuyoKoujo(income);

  // 課税所得（所得税）
  const taxableIncome = kyuyoShotoku - KISO_KOUJO - spouseKoujo - dependentKoujo;

  // 住民税所得割
  const juminTaxable = kyuyoShotoku - 43 - spouseKoujo - dependentKoujo; // 住民税基礎控除43万

  // 住宅ローン控除影響
  let loanDeduction = 0;
  if (loan === 'low') loanDeduction = 5;
  else if (loan === 'mid') loanDeduction = 15;
  else if (loan === 'high') loanDeduction = 25;

  // 所得税率
  let incomeTaxRate = 0.05;
  if (taxableIncome > 195) incomeTaxRate = 0.10;
  if (taxableIncome > 330) incomeTaxRate = 0.20;
  if (taxableIncome > 695) incomeTaxRate = 0.23;
  if (taxableIncome > 900) incomeTaxRate = 0.33;

  // 住民税所得割 = 課税所得 × 10%（概算）
  const juminTax = Math.max(0, juminTaxable * 10 - loanDeduction * 10000) * 10000;

  // ふるさと納税上限額の計算
  // 上限 = (住民税所得割 × 0.2) / (0.9 - 所得税率 × 1.021) + 2000
  const denominator = 0.9 - incomeTaxRate * 1.021;
  const limitRaw = (juminTaxable * 10 * 0.2) / denominator + 0.2;
  const limit = Math.max(0, Math.round(limitRaw * 10000 / 1000) * 1000);

  // 控除内訳
  const shotokuReturn = Math.round(limit * incomeTaxRate * 1.021);
  const juminReturn = limit - 2000 - shotokuReturn;

  const recommend = Math.round(limit * 0.9 / 1000) * 1000;
  const returnPct = limit > 0 ? Math.round((limit - 2000) / limit * 100) : 98;

  document.getElementById('ft-limit').textContent = fmt(limit);
  document.getElementById('ft-burden').textContent = '2,000円（' + fmt(limit) + '寄付した場合）';
  document.getElementById('ft-recommend').textContent = fmt(recommend);
  document.getElementById('ft-jumin').textContent = fmt(Math.max(0, juminReturn));
  document.getElementById('ft-shotoku').textContent = fmt(Math.max(0, shotokuReturn));
  document.getElementById('fv-donation-label').textContent = fmt(limit);
  document.getElementById('fv-return-label').textContent = fmt(Math.max(0, limit - 2000)) + ' 戻る';
  document.getElementById('fv-return-bar').style.width = Math.max(2, returnPct) + '%';
}

// range sync
const rng = document.getElementById('ft-income-range');
const num = document.getElementById('ft-income');
rng.addEventListener('input', () => { num.value = rng.value; calcFurusato(); });
num.addEventListener('input', () => { rng.value = num.value; calcFurusato(); });
document.querySelectorAll('input[name="family"], input[name="loan"]').forEach(r => r.addEventListener('change', calcFurusato));

calcFurusato();
</script>
