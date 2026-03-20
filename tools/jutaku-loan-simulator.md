---
layout: default
title: "住宅ローン 繰り上げ返済シミュレーター【2026年版】節約利息・短縮期間を自動計算"
description: "住宅ローンの繰り上げ返済効果を自動計算。残高・金利・繰り上げ額を入力するだけで、節約できる利息総額と返済期間の短縮効果がわかります。"
permalink: /tools/jutaku-loan-simulator/
---

<div class="tool-page">

<div class="tool-hero">
  <div class="tool-hero-inner">
    <div class="tool-badge">無料シミュレーター</div>
    <h1 class="tool-title">住宅ローン 繰り上げ返済シミュレーター</h1>
    <p class="tool-subtitle">繰り上げ返済で「いくら得するか」「何年短縮できるか」<br>をリアルタイムで計算します</p>
  </div>
</div>

<div class="tool-container">

  <div class="tool-main">

    <div class="sim-card">
      <h2 class="sim-card-title">📝 現在のローン情報を入力</h2>

      <div class="input-group">
        <label for="loan-balance">現在のローン残高</label>
        <div class="input-row">
          <input type="range" id="loan-balance-range" min="500" max="8000" step="100" value="3000">
          <div class="input-display">
            <input type="number" id="loan-balance" value="3000" min="500" max="8000" step="100">
            <span class="unit">万円</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label for="loan-rate">金利（年率）</label>
        <div class="input-row">
          <input type="range" id="loan-rate-range" min="0.1" max="4" step="0.05" value="0.5">
          <div class="input-display">
            <input type="number" id="loan-rate" value="0.5" min="0.1" max="4" step="0.05">
            <span class="unit">%</span>
          </div>
        </div>
        <p class="input-note">変動金利の現在の目安: 0.3〜0.7%　固定10年: 1.5〜2.5%</p>
      </div>

      <div class="input-group">
        <label for="remaining-years">残りの返済期間</label>
        <div class="input-row">
          <input type="range" id="remaining-years-range" min="1" max="35" step="1" value="25">
          <div class="input-display">
            <input type="number" id="remaining-years" value="25" min="1" max="35" step="1">
            <span class="unit">年</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label for="prepay-amount">繰り上げ返済額</label>
        <div class="input-row">
          <input type="range" id="prepay-range" min="10" max="500" step="10" value="100">
          <div class="input-display">
            <input type="number" id="prepay-amount" value="100" min="10" max="500" step="10">
            <span class="unit">万円</span>
          </div>
        </div>
      </div>

      <div class="input-group">
        <label>繰り上げ返済のタイプ</label>
        <div class="radio-group">
          <label class="radio-label">
            <input type="radio" name="prepay-type" value="period" checked>
            <strong>期間短縮型</strong>（返済期間を短くする・利息節約効果が大きい）
          </label>
          <label class="radio-label">
            <input type="radio" name="prepay-type" value="payment">
            <strong>返済額軽減型</strong>（毎月の返済額を減らす・月々の負担が軽くなる）
          </label>
        </div>
      </div>
    </div>

    <div class="result-card">
      <h2 class="sim-card-title">📊 繰り上げ返済の効果</h2>

      <div class="result-highlight">
        <div class="result-main-item accent-gold">
          <span class="result-main-label">節約できる利息</span>
          <span class="result-main-value" id="saved-interest">—</span>
        </div>
        <div class="result-main-item" id="period-result-item">
          <span class="result-main-label" id="period-label">返済期間の短縮</span>
          <span class="result-main-value" id="period-reduction">—</span>
        </div>
      </div>

      <div class="result-breakdown">
        <div class="breakdown-row">
          <span class="breakdown-label">繰り上げ返済前の利息総額</span>
          <span class="breakdown-value" id="before-interest">—</span>
        </div>
        <div class="breakdown-row">
          <span class="breakdown-label">繰り上げ返済後の利息総額</span>
          <span class="breakdown-value green" id="after-interest">—</span>
        </div>
        <div class="breakdown-row total-row">
          <span class="breakdown-label">繰り上げ返済前の返済期間</span>
          <span class="breakdown-value" id="before-period">—</span>
        </div>
        <div class="breakdown-row total-row" id="after-period-row">
          <span class="breakdown-label">繰り上げ返済後の返済期間</span>
          <span class="breakdown-value green" id="after-period">—</span>
        </div>
        <div class="breakdown-row" id="monthly-reduction-row" style="display:none">
          <span class="breakdown-label">毎月の返済額の減少</span>
          <span class="breakdown-value green" id="monthly-reduction">—</span>
        </div>
      </div>

      <div class="loan-visual">
        <div class="loan-compare">
          <div class="loan-col">
            <div class="loan-col-title">繰り上げ前</div>
            <div class="loan-bar-wrap">
              <div class="loan-bar-principal" id="before-principal-bar"></div>
              <div class="loan-bar-interest" id="before-interest-bar"></div>
            </div>
            <div class="loan-bar-labels">
              <span class="label-principal">元金</span>
              <span class="label-interest">利息 <span id="before-interest-pct"></span></span>
            </div>
          </div>
          <div class="loan-col">
            <div class="loan-col-title">繰り上げ後</div>
            <div class="loan-bar-wrap">
              <div class="loan-bar-principal" id="after-principal-bar"></div>
              <div class="loan-bar-interest loan-bar-interest-after" id="after-interest-bar"></div>
            </div>
            <div class="loan-bar-labels">
              <span class="label-principal">元金</span>
              <span class="label-interest green">利息 <span id="after-interest-pct"></span></span>
            </div>
          </div>
        </div>
      </div>

      <div class="result-note">
        <p>💡 繰り上げ返済の費用対効果：<strong id="roi-note">—</strong></p>
      </div>
    </div>

    <div class="sim-card">
      <h2 class="sim-card-title">⚠️ 繰り上げ返済で注意すること</h2>
      <table class="info-table">
        <tr>
          <th>チェック項目</th>
          <th>内容</th>
        </tr>
        <tr>
          <td>手数料の確認</td>
          <td>ネット銀行は無料〜数千円、大手行は数万円かかる場合も</td>
        </tr>
        <tr>
          <td>住宅ローン控除との兼ね合い</td>
          <td>控除期間中（最長13年）は残高を維持する方が得なケースも</td>
        </tr>
        <tr>
          <td>手元資金の確保</td>
          <td>生活費3〜6ヶ月分は手元に残してから繰り上げを検討</td>
        </tr>
        <tr>
          <td>金利上昇局面</td>
          <td>変動金利が上昇トレンドなら期間短縮型の優先度が上がる</td>
        </tr>
      </table>
    </div>

    <div class="cta-card">
      <h3>より有利な住宅ローンに借り換えを検討</h3>
      <p>金利が0.5%下がるだけで数百万円の節約になるケースも。現在の金利と比較してみましょう。</p>
      <div class="cta-buttons">
        <a href="https://mogecheck.jp/" class="cta-btn cta-primary" target="_blank" rel="noopener sponsored">モゲチェックで金利を比較 →</a>
        <a href="https://www.aruhi-corp.co.jp/" class="cta-btn cta-secondary" target="_blank" rel="noopener sponsored">ARUHIで借り換えシミュレーション →</a>
      </div>
    </div>

    <div class="sim-card">
      <p style="font-size:13px;color:#94a3b8;">※本シミュレーターは概算値を表示するものです。実際の返済額・利息は金融機関の計算方法により異なります。正確な数値は借入先の金融機関にお問い合わせください。</p>
    </div>

  </div>

  <aside class="tool-sidebar">
    <div class="sidebar-widget">
      <h3 class="widget-title">🔗 関連シミュレーター</h3>
      <ul class="sidebar-links">
        <li><a href="/money-blog/tools/ideco-simulator/">iDeCo 節税シミュレーター</a></li>
        <li><a href="/money-blog/tools/furusato-simulator/">ふるさと納税 控除上限額計算</a></li>
      </ul>
    </div>
    <div class="sidebar-widget">
      <h3 class="widget-title">📚 関連記事</h3>
      <ul class="sidebar-post-list">
        {% for post in site.posts %}
          {% if post.title contains '住宅' or post.title contains 'ローン' %}
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

// 月次返済計算
function calcMonthlyPayment(principal, annualRate, months) {
  if (annualRate === 0) return principal / months;
  const r = annualRate / 12 / 100;
  return principal * r * Math.pow(1 + r, months) / (Math.pow(1 + r, months) - 1);
}

// 利息総額計算
function calcTotalInterest(principal, annualRate, months) {
  const monthly = calcMonthlyPayment(principal, annualRate, months);
  return monthly * months - principal;
}

// 期間短縮型：繰り上げ後の新しい残高で期間を計算
function calcNewMonths(newPrincipal, monthlyPayment, annualRate) {
  if (annualRate === 0) return Math.ceil(newPrincipal / monthlyPayment);
  const r = annualRate / 12 / 100;
  if (monthlyPayment <= newPrincipal * r) return 999; // 返済不能
  return Math.ceil(Math.log(monthlyPayment / (monthlyPayment - newPrincipal * r)) / Math.log(1 + r));
}

function calcLoan() {
  const balance = (parseFloat(document.getElementById('loan-balance').value) || 3000) * 10000;
  const rate = parseFloat(document.getElementById('loan-rate').value) || 0.5;
  const remainYears = parseFloat(document.getElementById('remaining-years').value) || 25;
  const prepay = (parseFloat(document.getElementById('prepay-amount').value) || 100) * 10000;
  const type = document.querySelector('input[name="prepay-type"]:checked').value;
  const remainMonths = remainYears * 12;

  // 繰り上げ前
  const beforeMonthly = calcMonthlyPayment(balance, rate, remainMonths);
  const beforeInterest = Math.max(0, beforeMonthly * remainMonths - balance);

  // 新しい元金
  const newBalance = Math.max(0, balance - prepay);

  let savedInterest, afterInterest, afterMonths, monthlyReduction;

  if (type === 'period') {
    // 期間短縮型：月々の返済額は同じ
    afterMonths = calcNewMonths(newBalance, beforeMonthly, rate);
    afterInterest = Math.max(0, beforeMonthly * afterMonths - newBalance);
    savedInterest = beforeInterest - afterInterest;
    monthlyReduction = 0;

    const shortMonths = remainMonths - afterMonths;
    const shortYears = Math.floor(shortMonths / 12);
    const shortMon = shortMonths % 12;
    const afterYears = Math.floor(afterMonths / 12);
    const afterMon = afterMonths % 12;

    document.getElementById('period-label').textContent = '返済期間の短縮';
    document.getElementById('period-reduction').textContent =
      shortYears > 0 ? shortYears + '年' + (shortMon > 0 ? shortMon + 'ヶ月' : '') :
      shortMon > 0 ? shortMon + 'ヶ月' : '変化なし';
    document.getElementById('after-period').textContent = afterYears + '年' + (afterMon > 0 ? afterMon + 'ヶ月' : '');
    document.getElementById('after-period-row').style.display = '';
    document.getElementById('monthly-reduction-row').style.display = 'none';

  } else {
    // 返済額軽減型：返済期間は同じ
    afterMonths = remainMonths;
    const afterMonthly = calcMonthlyPayment(newBalance, rate, remainMonths);
    afterInterest = Math.max(0, afterMonthly * remainMonths - newBalance);
    savedInterest = beforeInterest - afterInterest;
    monthlyReduction = beforeMonthly - afterMonthly;

    document.getElementById('period-label').textContent = '毎月の返済額減少';
    document.getElementById('period-reduction').textContent = fmt(Math.round(monthlyReduction));
    document.getElementById('after-period-row').style.display = 'none';
    document.getElementById('monthly-reduction-row').style.display = '';
    document.getElementById('monthly-reduction').textContent = fmt(Math.round(monthlyReduction)) + '/月';
  }

  const roi = savedInterest > 0 ? Math.round(savedInterest / prepay * 100) : 0;

  // UI update
  document.getElementById('saved-interest').textContent = fmtMan(Math.max(0, savedInterest));
  document.getElementById('before-interest').textContent = fmtMan(beforeInterest);
  document.getElementById('after-interest').textContent = fmtMan(Math.max(0, afterInterest));
  document.getElementById('before-period').textContent = remainYears + '年';
  document.getElementById('roi-note').textContent =
    prepay > 0 ? fmtMan(prepay) + 'の繰り上げ返済で' + fmtMan(Math.max(0, savedInterest)) + '節約（ROI ' + roi + '%）' : '—';

  // Bar chart
  const totalBefore = balance + beforeInterest;
  const principalPct = Math.round(balance / totalBefore * 100);
  const interestBeforePct = 100 - principalPct;
  const totalAfter = balance + Math.max(0, afterInterest);
  const interestAfterPct = Math.round(Math.max(0, afterInterest) / totalAfter * 100);

  document.getElementById('before-principal-bar').style.height = principalPct + '%';
  document.getElementById('before-interest-bar').style.height = interestBeforePct + '%';
  document.getElementById('after-principal-bar').style.height = Math.round(balance / totalAfter * 100) + '%';
  document.getElementById('after-interest-bar').style.height = interestAfterPct + '%';
  document.getElementById('before-interest-pct').textContent = interestBeforePct + '%';
  document.getElementById('after-interest-pct').textContent = interestAfterPct + '%';
}

// range sync
[
  ['loan-balance', 'loan-balance-range'],
  ['loan-rate', 'loan-rate-range'],
  ['remaining-years', 'remaining-years-range'],
  ['prepay-amount', 'prepay-range']
].forEach(([numId, rngId]) => {
  const num = document.getElementById(numId);
  const rng = document.getElementById(rngId);
  num.addEventListener('input', () => { rng.value = num.value; calcLoan(); });
  rng.addEventListener('input', () => { num.value = rng.value; calcLoan(); });
});
document.querySelectorAll('input[name="prepay-type"]').forEach(r => r.addEventListener('change', calcLoan));

calcLoan();
</script>
