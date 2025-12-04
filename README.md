<!doctype html>
<html lang="hi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Pricing — TradeDiary Style (Free)</title>
  <meta name="description" content="Simple pricing page with free plan highlighted."/>
  <style>
    /* ====== Basic Reset ====== */
    *{box-sizing:border-box;margin:0;padding:0;font-family:Inter,Segoe UI,Roboto,Arial,sans-serif}
    html,body{height:100%;}
    body{
      background:linear-gradient(180deg,#f6f9ff 0%,#ffffff 100%);
      color:#102a43;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.4;
    }

    .container{max-width:1100px;margin:48px auto;padding:0 20px;}

    /* ====== Header ====== */
    header{display:flex;align-items:center;justify-content:space-between;margin-bottom:28px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{
      width:46px;height:46px;border-radius:10px;background:#0f1724;color:#fff;display:flex;align-items:center;justify-content:center;font-weight:700;
      box-shadow:0 6px 18px rgba(16,42,67,0.08);
    }
    .brand h1{font-size:18px;color:#0b2440}
    nav a{color:#334e68;text-decoration:none;margin-left:18px;font-weight:600}
    nav a.cta{background:#0b69ff;color:white;padding:8px 14px;border-radius:8px}

    /* ====== Hero ====== */
    .hero{display:flex;flex-direction:column;gap:10px;margin-bottom:28px}
    .hero h2{font-size:28px;color:#06263b}
    .hero p{color:#3b5367}

    /* ====== Toggle ====== */
    .toggle{display:inline-flex;background:#e9f0ff;padding:6px;border-radius:999px;gap:6px;margin-top:6px}
    .toggle button{
      border:0;background:transparent;padding:8px 12px;border-radius:999px;font-weight:700;color:#254d7e;cursor:pointer;
    }
    .toggle button.active{background:white;box-shadow:0 6px 18px rgba(11,105,255,0.12)}

    /* ====== Pricing cards ====== */
    .cards{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:18px}
    @media (max-width:880px){.cards{grid-template-columns:1fr;}}
    .card{
      background:linear-gradient(180deg,#fff,#fbfdff);
      border-radius:14px;padding:22px;border:1px solid rgba(11,35,60,0.06);
      box-shadow:0 6px 24px rgba(16,42,67,0.04);
      display:flex;flex-direction:column;gap:12px;position:relative;overflow:hidden;
    }
    .badge{position:absolute;top:14px;right:14px;background:#e6f3ff;color:#0b69ff;padding:6px 10px;border-radius:999px;font-weight:700;font-size:12px}
    .card.free{border:2px solid #0b69ff;transform:translateY(-4px);box-shadow:0 10px 30px rgba(11,105,255,0.08)}
    .title{font-weight:800;font-size:18px;color:#07263e}
    .price{font-size:28px;font-weight:800;color:#0b69ff}
    .price small{display:block;font-size:13px;color:#3b5367;font-weight:600}
    .features{list-style:none;padding-left:0;margin-top:6px;color:#254d7e}
    .features li{padding:8px 0;border-top:1px dashed rgba(16,42,67,0.04);font-weight:600;font-size:14px}
    .btn{
      margin-top:8px;padding:12px 14px;border-radius:10px;border:0;font-weight:800;cursor:pointer;
    }
    .btn.primary{background:#0b69ff;color:white}
    .btn.ghost{background:#eef6ff;color:#0b69ff;border:1px solid rgba(11,105,255,0.1)}

    /* ====== Footer small ====== */
    .note{margin-top:22px;color:#415a72;font-size:14px}

    /* ====== tiny responsive tweaks ====== */
    @media (max-width:480px){
      .brand h1{font-size:16px}
      .hero h2{font-size:22px}
      .price{font-size:24px}
    }

  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">TD</div>
        <div>
          <h1>TradeDiary — Demo</h1>
          <div style="font-size:12px;color:#546e7a">Simple pricing page</div>
        </div>
      </div>
      <nav>
        <a href="#features">Features</a>
        <a href="#pricing" class="cta">Get Started</a>
      </nav>
    </header>

    <section class="hero" id="pricing">
      <h2>Plans for every trader — start with Free</h2>
      <p>Free forever plan for hobby traders. Upgrade as you grow. Toggle to see monthly/yearly pricing.</p>

      <div class="toggle" role="tablist" aria-label="Billing toggle">
        <button id="monthlyBtn" class="active" aria-pressed="true">Monthly</button>
        <button id="yearlyBtn" aria-pressed="false">Yearly (save 20%)</button>
      </div>
    </section>

    <section class="cards" aria-label="Pricing plans">
      <!-- Free -->
      <div class="card free" aria-labelledby="freeTitle">
        <div class="badge">Popular</div>
        <div class="title" id="freeTitle">Free</div>
        <div class="price" data-monthly="₹0" data-yearly="₹0">₹0 <small>/ month</small></div>
        <ul class="features">
          <li>1 demo portfolio</li>
          <li>Up to 50 trades / month</li>
          <li>Basic charts & indicators</li>
          <li>Email support</li>
        </ul>
        <button class="btn primary" onclick="cta('free')">Start Free</button>
      </div>

      <!-- Pro -->
      <div class="card" aria-labelledby="proTitle">
        <div class="title" id="proTitle">Pro</div>
        <div class="price" data-monthly="₹499" data-yearly="₹399*">₹499 <small>/ month</small></div>
        <ul class="features">
          <li>5 portfolios</li>
          <li>Unlimited trades</li>
          <li>Advanced charts & alerts</li>
          <li>Priority email support</li>
        </ul>
        <button class="btn ghost" onclick="cta('pro')">Start Free Trial</button>
      </div>

      <!-- Enterprise -->
      <div class="card" aria-labelledby="entTitle">
        <div class="title" id="entTitle">Enterprise</div>
        <div class="price" data-monthly="Contact" data-yearly="Contact">Contact <small>/ custom</small></div>
        <ul class="features">
          <li>Team accounts</li>
          <li>Personal onboarding</li>
          <li>Dedicated support</li>
          <li>Custom integrations</li>
        </ul>
        <button class="btn ghost" onclick="cta('enterprise')">Contact Sales</button>
      </div>
    </section>

    <p class="note">* Yearly prices shown are per month equivalent after discount. Free plan has no hidden fees.</p>
  </div>

  <script>
    // Toggle monthly/yearly pricing
    const monthlyBtn = document.getElementById('monthlyBtn');
    const yearlyBtn = document.getElementById('yearlyBtn');
    const priceEls = document.querySelectorAll('.price');

    function setBilling(mode){
      priceEls.forEach(el=>{
        const monthly = el.getAttribute('data-monthly') || '';
        const yearly = el.getAttribute('data-yearly') || '';
        if(mode === 'monthly'){
          el.innerHTML = monthly + ' <small>/ month</small>';
        } else {
          el.innerHTML = yearly + ' <small>/ month</small>';
        }
      });

      if(mode === 'monthly'){
        monthlyBtn.classList.add('active'); monthlyBtn.setAttribute('aria-pressed','true');
        yearlyBtn.classList.remove('active'); yearlyBtn.setAttribute('aria-pressed','false');
      } else {
        yearlyBtn.classList.add('active'); yearlyBtn.setAttribute('aria-pressed','true');
        monthlyBtn.classList.remove('active'); monthlyBtn.setAttribute('aria-pressed','false');
      }
    }

    monthlyBtn.addEventListener('click',()=>setBilling('monthly'));
    yearlyBtn.addEventListener('click',()=>setBilling('yearly'));

    // CTA handler - for demo we'll just show an alert; replace with your signup link
    function cta(plan){
      if(plan === 'free'){
        window.location.href = '#'; // replace with sign-up link
        alert('Aap Free plan choose kar rahe hain. Signup link add karna hai toh bataiye.');
      } else if(plan === 'pro'){
        alert('Pro trial ke liye signup page create karen. (Demo)');
      } else {
        alert('Contact sales at: sales@example.com (demo)');
      }
    }

    // default
    setBilling('monthly');
  </script>
</body>
</html 
