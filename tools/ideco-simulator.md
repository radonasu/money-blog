---
layout: default
title: "iDeCo節税シミュレーター【2026年版】年収別・積立額・節税効果を自動計算"
description: "iDeCoの節税効果を年収・掛け金・運用期間で自動計算。年間節税額・30年の積立資産・運用益をリアルタイムでシミュレーション。"
permalink: /tools/ideco-simulator/
---

<div class="tool-page">

<div class="tool-hero">
  <div class="tool-hero-inner">
    <div class="tool-badge">無料シミュレーター</div>
    <h1 class="tool-title">iDeCo 節税シミュレーター</h1>
    <p class="tool-subtitle">年収・掛け金・運用期間を入力するだけで<br>節税効果と老後資産を自動計算します</p>
  </div>
</div>

<div class="tool-container">

  <div class="tool-main">

    <div class="sim-card">
      <h2 class="sim-card-title">📝 条件を入力</h2>

      <div class="input-group">
        <label for="income">年収（手取りではなく額面）</label>
        <div class="input-row">
          <input type="range" id="income-range" min="200" max="2000" step="50" value="500">
          <div class="input-display">
            <input type="number" id="income" value="500" min="200" max="2000" step="50">
            <span class="unit">万円</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label for="monthly">月額掛け金</label>
        <div class="input-row">
          <input type="range" id="monthly-range" min="5000" max="68000" step="1000" value="23000">
          <div class="input-display">
            <input type="number" id="monthly" value="23000" min="5000" max="68000" step="1000">
            <span class="unit">円/月</span>
          </div>
        </div>
        <p class="input-note">会社員の上限: ¥23,000/月　自営業者: ¥68,000/月</p>
      </div>

      <div class="input-group">
        <label for="years">積立期間</label>
        <div class="input-row">
          <input type="range" id="years-range" min="5" max="35" step="1" value="20">
          <div class="input-display">
            <input type="number" id="years" value="20" min="5" max="35" step="1">
            <span class="unit">年</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label for="return-rate">想定利回り（年率）</label>
        <div class="input-row">
          <input type="range" id="return-range" min="0" max="7" step="0.5" value="3">
          <div class="input-display">
            <input type="number" id="return-rate" value="3" min="0" max="7" step="0.5">
            <span class="unit">%</span>
          </div>
        </div>
        <p class="input-note">インデックスファンドの長期平均: 3〜5%が目安</p>
      </div>

      <div class="input-group">
        <label>加入タイプ</label>
        <div class="radio-group">
          <label class="radio-label">
            <input type="radio" name="member-type" value="employee" checked> 会社員（企業年金なし）
          </label>
          <label class="radio-label">
            <input type="radio" name="member-type" value="self"> 自営業・フリーランス
          </label>
          <label class="radio-label">
            <input type="radio" name="member-type" value="employee-corp"> 会社員（企業年金あり）
          </label>
        </div>
      </div>
    </div>

    <div class="result-card" id="result-card">
      <h2 class="sim-card-title">📊 シミュレーション結果</h2>

      <div class="result-highlight">
        <div class="result-main-item">
          <span class="result-main-label">年間節税額</span>
          <span class="result-main-value" id="annual-tax-save">—</span>
        </div>
        <div class="result-main-item accent-gold">
          <span class="result-main-label">期間中の節税累計</span>
          <span class="result-main-value" id="total-tax-save">—</span>
        </div>
      </div>

      <div class="result-breakdown">
        <div class="breakdown-row">
          <span class="breakdown-label">積立総額（掛け金のみ）</span>
          <span class="breakdown-value" id="total-contribution">—</span>
        </div>
        <div class="breakdown-row">
          <span class="breakdown-label">運用益（税金ゼロ）</span>
          <span class="breakdown-value green" id="investment-gain">—</span>
        </div>
        <div class="breakdown-row total-row">
          <span class="breakdown-label">受取予定総額</span>
          <span class="breakdown-value" id="total-amount">—</span>
        </div>
        <div class="breakdown-row">
          <span class="breakdown-label">適用所得税率（目安）</span>
          <span class="breakdown-value" id="tax-rate">—</span>
        </div>
      </div>

      <div class="result-bar-section">
        <p class="bar-label">積立総額の内訳</p>
        <div class="stacked-bar">
          <div class="bar-contribution" id="bar-contribution"></div>
          <div class="bar-gain" id="bar-gain"></div>
        </div>
        <div class="bar-legend">
          <span class="legend-item blue">■ 掛け金</span>
          <span class="legend-item green">■ 運用益（非課税）</span>
        </div>
      </div>

      <div class="result-note">
        <p>💡 節税額に加え、運用益も非課税。普通口座で運用した場合に比べ<strong id="tax-merit">—</strong>お得になります。</p>
      </div>
    </div>

    <div class="cta-card">
      <h3>iDeCoを始めるなら手数料最安の証券会社で</h3>
      <p>口座管理手数料が業界最安水準。インデックスファンドも充実しています。</p>
      <div class="cta-buttons">
        <a href="https://www.sbi-sec.co.jp/lp/ideco/" class="cta-btn cta-primary" target="_blank" rel="noopener sponsored">SBI証券でiDeCoを始める →</a>
        <a href="https://www.rakuten-sec.co.jp/web/ideco/" class="cta-btn cta-secondary" target="_blank" rel="noopener sponsored">楽天証券でiDeCoを始める →</a>
      </div>
    </div>

    <div class="sim-card">
      <h2 class="sim-card-title">📖 iDeCoの節税の仕組み</h2>
      <table class="info-table">
        <tr><th>メリット</th><th>内容</th></tr>
        <tr><td>掛け金が全額控除</td><td>所得税・住民税が毎年軽減される</td></tr>
        <tr><td>運用益が非課税</td><td>通常20.315%の税金がゼロに</td></tr>
        <tr><td>受取時も控除あり</td><td>退職所得控除または公的年金等控除が適用</td></tr>
      </table>
      <p style="margin-top:16px;font-size:14px;color:#64748b;">※本シミュレーターは概算値です。実際の節税額は給与や家族構成により異なります。詳しくはファイナンシャルプランナーにご相談ください。</p>
    </div>

  </div>

  <aside class="tool-sidebar">
    <div class="sidebar-widget">
      <h3 class="widget-title">🔗 関連シミュレーター</h3>
      <ul class="sidebar-links">
        <li><a href="/money-blog/tools/furusato-simulator/">ふるさと納税 控除上限額計算</a></li>
        <li><a href="/money-blog/tools/jutaku-loan-simulator/">住宅ローン繰り上げ返済計算</a></li>
      </ul>
    </div>
    <div class="sidebar-widget">
      <h3 class="widget-title">📚 関連記事</h3>
      <ul class="sidebar-post-list">
        {% for post in site.posts %}
          {% if post.title contains 'iDeCo' or post.title contains '節税' or post.title contains 'NISA' %}
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
const fmtMan = n => (Math.round(n / 10000)).toLocaleString('ja-JP') + '万円';

// 所得税率（簡易）
function getTaxRate(income) {
  if (income <= 195) return 0.05;
  if (income <= 330) return 0.10;
  if (income <= 695) return 0.20;
  if (income <= 900) return 0.23;
  if (income <= 1800) return 0.33;
  return 0.40;
}

function calc() {
  const income = parseFloat(document.getElementById('income').value) || 500;
  const monthly = parseFloat(document.getElementById('monthly').value) || 23000;
  const years = parseFloat(document.getElementById('years').value) || 20;
  const rate = parseFloat(document.getElementById('return-rate').value) / 100 || 0.03;

  const incomeTaxRate = getTaxRate(income);
  const housingTaxRate = 0.10;
  const totalTaxRate = incomeTaxRate + housingTaxRate;

  const annualContribution = monthly * 12;
  const annualTaxSave = Math.round(annualContribution * totalTaxRate);
  const totalTaxSave = annualTaxSave * years;

  // 複利計算（月次）
  const monthlyRate = rate / 12;
  const months = years * 12;
  let totalAmount;
  if (monthlyRate === 0) {
    totalAmount = monthly * months;
  } else {
    totalAmount = monthly * ((Math.pow(1 + monthlyRate, months) - 1) / monthlyRate);
  }
  const totalContribution = monthly * months;
  const investmentGain = totalAmount - totalContribution;

  // 通常課税との差（運用益の20.315%）
  const taxMerit = Math.round(investmentGain * 0.20315) + totalTaxSave;

  // UI更新
  document.getElementById('annual-tax-save').textContent = fmt(annualTaxSave);
  document.getElementById('total-tax-save').textContent = fmtMan(totalTaxSave);
  document.getElementById('total-contribution').textContent = fmtMan(totalContribution);
  document.getElementById('investment-gain').textContent = fmtMan(investmentGain);
  document.getElementById('total-amount').textContent = fmtMan(totalAmount);
  document.getElementById('tax-rate').textContent = Math.round(totalTaxRate * 100) + '%（所得税' + Math.round(incomeTaxRate * 100) + '%＋住民税10%）';
  document.getElementById('tax-merit').textContent = fmtMan(taxMerit) + '以上';

  // Bar
  const pct = totalContribution / totalAmount * 100;
  document.getElementById('bar-contribution').style.width = pct + '%';
  document.getElementById('bar-gain').style.width = (100 - pct) + '%';
}

// sync range ↔ number
['income','monthly','years','return-rate'].forEach(id => {
  const num = document.getElementById(id);
  const range = document.getElementById(id + '-range') || document.getElementById(id.replace('-rate','') + '-range');
  const rng = document.getElementById(id + '-range');
  if (num && rng) {
    num.addEventListener('input', () => { rng.value = num.value; calc(); });
    rng.addEventListener('input', () => { num.value = rng.value; calc(); });
  } else if (num) {
    num.addEventListener('input', calc);
  }
});
document.querySelectorAll('input[name="member-type"]').forEach(r => r.addEventListener('change', calc));

calc();
</script>
