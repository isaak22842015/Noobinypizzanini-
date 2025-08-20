#!/usr/bin/env bash
set -euo pipefail

NAME="noobinypizzanini"
mkdir -p "$NAME/assets"

cat > "$NAME/index.html" <<'HTML'
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Noobiny Pizzanini — Wood-Fired Pizza Done Playfully</title>
  <meta name="description" content="Noobiny Pizzanini — playful wood-fired pies, crispy edges, gooey centers. Order online, view our menu, and find our shop." />
  <link rel="preload" href="assets/logo.svg" as="image" type="image/svg+xml">
  <link rel="icon" href="assets/favicon.svg" type="image/svg+xml">
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <a class="skip-link" href="#main">Skip to content</a>
  <header class="site-header" id="top">
    <div class="container nav-wrap">
      <a class="brand" href="#top" aria-label="Noobiny Pizzanini home">
        <img src="assets/logo.svg" alt="" width="40" height="40" />
        <span>Noobiny <strong>Pizzanini</strong></span>
      </a>

      <button class="nav-toggle" aria-expanded="false" aria-controls="nav" aria-label="Toggle navigation">
        <span class="bar"></span><span class="bar"></span><span class="bar"></span>
      </button>

      <nav id="nav" class="nav">
        <ul>
          <li><a href="#menu">Menu</a></li>
          <li><a href="#build">Build Your Own</a></li>
          <li><a href="#locations">Locations</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a class="btn order-btn" href="#order">Order</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="main">
    <section class="hero">
      <div class="container hero-inner">
        <h1>Wood-Fired Pizza, <span class="underline">Zero Stress</span></h1>
        <p class="lead">We do pies the playful way: crispy edges, bubbly crusts, and toppings that don’t take themselves too seriously.</p>
        <div class="hero-cta">
          <a class="btn primary" href="#menu">See the Menu</a>
          <a class="btn ghost" href="#build">Build Your Own</a>
        </div>
        <figure class="hero-pie" aria-hidden="true">
          <img src="assets/hero-pie.svg" alt="" width="520" height="520">
        </figure>
      </div>
      <div class="ticker" role="marquee" aria-label="Daily deals">
        <div class="ticker-track">
          <span>🍕 2-for-Tuesday on classic margherita • 🧃 Free drink with any lunch combo • 🍨 Add a mini gelato for $2</span>
          <span aria-hidden="true">🍕 2-for-Tuesday on classic margherita • 🧃 Free drink with any lunch combo • 🍨 Add a mini gelato for $2</span>
        </div>
      </div>
    </section>

    <section id="featured" class="featured">
      <div class="container">
        <h2>House Favorites</h2>
        <div class="cards" role="list">
          <article class="card" role="listitem">
            <div class="card-media gradient-1" aria-hidden="true"></div>
            <div class="card-body">
              <h3>Spicy Noob</h3>
              <p>Calabrian chili oil, pepperoni cups, mozzarella, honey drizzle.</p>
              <div class="price-row"><span>$15</span><button class="btn small add" data-name="Spicy Noob" data-price="15">Add</button></div>
            </div>
          </article>
          <article class="card" role="listitem">
            <div class="card-media gradient-2" aria-hidden="true"></div>
            <div class="card-body">
              <h3>Green Machine</h3>
              <p>Pesto base, fresh mozz, basil ribbons, roasted zucchini.</p>
              <div class="price-row"><span>$14</span><button class="btn small add" data-name="Green Machine" data-price="14">Add</button></div>
            </div>
          </article>
          <article class="card" role="listitem">
            <div class="card-media gradient-3" aria-hidden="true"></div>
            <div class="card-body">
              <h3>Cheese Cloud</h3>
              <p>Four-cheese blend, garlic confit, sea salt, thyme.</p>
              <div class="price-row"><span>$13</span><button class="btn small add" data-name="Cheese Cloud" data-price="13">Add</button></div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="menu" class="menu section-alt">
      <div class="container">
        <h2>Menu</h2>
        <div class="menu-grid">
          <div class="menu-col">
            <h3>Classics</h3>
            <ul class="menu-list">
              <li><span>Margherita</span><span>$12</span></li>
              <li><span>Pepperoni</span><span>$13</span></li>
              <li><span>Veggie Deluxe</span><span>$14</span></li>
              <li><span>BBQ Chicken</span><span>$15</span></li>
            </ul>
          </div>
          <div class="menu-col">
            <h3>Snacks</h3>
            <ul class="menu-list">
              <li><span>Garlic Knots</span><span>$6</span></li>
              <li><span>Caprese Skewers</span><span>$7</span></li>
              <li><span>Spicy Wings</span><span>$9</span></li>
            </ul>
          </div>
          <div class="menu-col">
            <h3>Drinks &amp; Sweets</h3>
            <ul class="menu-list">
              <li><span>Italian Soda</span><span>$4</span></li>
              <li><span>Lemon Iced Tea</span><span>$3</span></li>
              <li><span>Mini Gelato</span><span>$5</span></li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="build" class="build">
      <div class="container">
        <h2>Build Your Own</h2>
        <form class="builder" aria-describedby="priceOut">
          <div class="builder-row">
            <label for="size">Size</label>
            <select id="size" name="size">
              <option value="10" data-base="8">Small (10")</option>
              <option value="12" data-base="10" selected>Medium (12")</option>
              <option value="16" data-base="13">Large (16")</option>
            </select>
          </div>
          <fieldset class="builder-row toppings">
            <legend>Toppings ($1.50 each)</legend>
            <label><input type="checkbox" value="Pepperoni"> Pepperoni</label>
            <label><input type="checkbox" value="Mushroom"> Mushroom</label>
            <label><input type="checkbox" value="Onion"> Onion</label>
            <label><input type="checkbox" value="Olives"> Olives</label>
            <label><input type="checkbox" value="Jalapeño"> Jalapeño</label>
            <label><input type="checkbox" value="Pineapple"> Pineapple</label>
          </fieldset>
          <div class="builder-row">
            <output id="priceOut" for="size toppings" aria-live="polite">$10.00</output>
            <button type="button" class="btn add-built">Add to Cart</button>
          </div>
        </form>
      </div>
    </section>

    <section id="locations" class="locations section-alt">
      <div class="container">
        <h2>Locations &amp; Hours</h2>
        <div class="loc-grid">
          <div class="loc-card">
            <h3>Downtown</h3>
            <p>123 Slice St, Your City</p>
            <p>Mon–Thu 11–9 • Fri–Sat 11–11 • Sun 12–8</p>
          </div>
          <div class="loc-card">
            <h3>Eastside</h3>
            <p>456 Dough Ave, Your City</p>
            <p>Daily 11–9</p>
          </div>
          <div class="loc-card highlight">
            <h3>Food Truck</h3>
            <p>Fridays at River Market</p>
            <p>5–9 PM • Weather permitting</p>
          </div>
        </div>
      </div>
    </section>

    <section id="order" class="order">
      <div class="container">
        <h2>Your Order</h2>
        <div class="cart">
          <ul class="cart-items" aria-live="polite"></ul>
          <div class="cart-summary">
            <div><span>Subtotal</span><span id="subtotal">$0.00</span></div>
            <div><span>Tax (8%)</span><span id="tax">$0.00</span></div>
            <div class="total"><span>Total</span><span id="total">$0.00</span></div>
            <button class="btn primary checkout">Checkout</button>
            <p class="muted">Demo only — no payment processed.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="contact section-alt">
      <div class="container">
        <h2>Contact Us</h2>
        <form class="contact-form" netlify aria-label="Contact form">
          <div class="field">
            <label for="name">Name</label>
            <input id="name" name="name" required autocomplete="name" />
          </div>
          <div class="field">
            <label for="email">Email</label>
            <input id="email" name="email" type="email" required autocomplete="email" />
          </div>
          <div class="field">
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="4" required></textarea>
          </div>
          <button class="btn">Send</button>
          <p class="muted">Prefer talking? Call (555) 013-PIZZA</p>
        </form>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container foot-grid">
      <div>
        <a class="brand small" href="#top">
          <img src="assets/logo.svg" alt="" width="28" height="28" />
          <span>Noobiny <strong>Pizzanini</strong></span>
        </a>
        <p class="muted">© <span id="year"></span> Noobiny Pizzanini. All rights reserved.</p>
      </div>
      <nav aria-label="Footer">
        <ul class="foot-links">
          <li><a href="#menu">Menu</a></li>
          <li><a href="#build">Build</a></li>
          <li><a href="#locations">Locations</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </div>
  </footer>

  <div class="toast" role="status" aria-live="polite" aria-atomic="true"></div>

  <script src="script.js"></script>
</body>
</html>
HTML

cat > "$NAME/styles.css" <<'CSS'
/* Noobiny Pizzanini — styles */
:root{
  --bg: #0b0b0c;
  --panel: #111115;
  --soft: #18181f;
  --text: #eaeaf0;
  --muted: #a4a6b3;
  --brand: #ff4d4f;
  --brand-2: #ffa94d;
  --radius: 14px;
  --shadow: 0 10px 30px rgba(0,0,0,.35);
}

*{box-sizing:border-box}
html,body{margin:0;padding:0}
body{
  background: radial-gradient(1200px 600px at 90% -10%, rgba(255,77,79,.18), transparent 60%),
              radial-gradient(1000px 500px at -10% 20%, rgba(255,169,77,.14), transparent 60%),
              var(--bg);
  color:var(--text);
  font: 16px/1.55 system-ui, -apple-system, Segoe UI, Roboto, Inter, Arial, sans-serif;
}

img{max-width:100%;display:block}

.container{width:min(1100px, 92vw);margin-inline:auto;padding: clamp(16px, 2vw, 28px)}

.skip-link{position:absolute;left:-9999px;top:auto}
.skip-link:focus{left:1rem;top:1rem;background:#fff;color:#000;padding:.6rem 1rem;border-radius:10px;z-index:1000}

.site-header{
  position:sticky;top:0;backdrop-filter:saturate(140%) blur(8px);
  background:linear-gradient(180deg, rgba(11,11,12,.9), rgba(11,11,12,.75) 60%, transparent);
  border-bottom:1px solid rgba(255,255,255,.06);
  z-index:100;
}
.nav-wrap{display:flex;align-items:center;gap:20px;justify-content:space-between}
.brand{display:inline-flex;align-items:center;gap:10px;font-weight:700;letter-spacing:.3px;text-decoration:none;color:var(--text)}
.brand small{font-size:.9rem}
.brand span strong{color:var(--brand)}
.nav ul{display:flex;align-items:center;gap:18px;list-style:none;margin:0;padding:0}
.nav a{color:var(--text);text-decoration:none;opacity:.9}
.nav a:hover{opacity:1}
.nav .btn.order-btn{padding:.55rem .9rem;border-radius:999px;border:1px solid rgba(255,255,255,.15)}

.nav-toggle{display:none;position:relative;width:42px;height:36px;border:0;background:transparent;cursor:pointer}
.nav-toggle .bar{position:absolute;left:8px;right:8px;height:3px;background:#fff;border-radius:3px;transition:transform .25s ease}
.nav-toggle .bar:nth-child(1){top:9px}
.nav-toggle .bar:nth-child(2){top:16px}
.nav-toggle .bar:nth-child(3){top:23px}

/* Hero */
.hero{position:relative;padding-top:28px}
.hero-inner{display:grid;grid-template-columns:1.1fr .9fr;align-items:center;gap:24px}
h1{font-size:clamp(2rem, 3.4vw + 1rem, 4rem);line-height:1.05;margin:.2em 0 .3em}
.lead{font-size:clamp(1rem, .7vw + .9rem, 1.25rem);color:var(--muted);margin:0 0 1.3rem}
.hero-cta{display:flex;gap:12px}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:.5rem;padding:.7rem 1.05rem;border-radius:12px;border:1px solid rgba(255,255,255,.16);background:var(--soft);color:#fff;text-decoration:none;cursor:pointer}
.btn.primary{background:linear-gradient(135deg, var(--brand), var(--brand-2));border:0;box-shadow:var(--shadow)}
.btn.ghost{background:transparent}
.btn.small{padding:.4rem .65rem;border-radius:10px;font-size:.92rem}
.btn:focus-visible{outline:3px solid #fff;outline-offset:2px}

.underline{background:linear-gradient(120deg, rgba(255,77,79,.5), rgba(255,169,77,.5));box-decoration-break:clone;padding:.05em .18em;border-radius:.3em}

.hero-pie{position:relative;filter:drop-shadow(var(--shadow))}
.ticker{overflow:hidden;border-block:1px solid rgba(255,255,255,.06);margin-top:24px}
.ticker-track{display:flex;gap:40px;white-space:nowrap;animation:scroll 28s linear infinite;padding:10px 0;color:#fff9}
@keyframes scroll{to{transform:translateX(-50%)}}

/* Featured */
.featured h2{margin:0 0 .6rem}
.cards{display:grid;grid-template-columns:repeat(3, 1fr);gap:16px}
.card{border:1px solid rgba(255,255,255,.08);background:linear-gradient(180deg, rgba(255,255,255,.02), rgba(255,255,255,.01));border-radius:var(--radius);overflow:hidden}
.card-media{height:160px}
.gradient-1{background:conic-gradient(from 30deg, #ffedc2, #ffd3c2, #ff9ca2, #ffd3c2, #ffedc2)}
.gradient-2{background:conic-gradient(from 60deg, #e2ffd1, #b8ffd1, #b8f0ff, #e2ffd1)}
.gradient-3{background:conic-gradient(from 0deg, #fff6c2, #ffd7a8, #ffc2e7, #fff6c2)}
.card-body{padding:14px 14px 12px}
.card h3{margin:.2rem 0 .4rem}
.card p{margin:0 0 .8rem;color:var(--muted)}
.price-row{display:flex;align-items:center;justify-content:space-between}

/* Menu */
.section-alt{background:rgba(255,255,255,.02);border-block:1px solid rgba(255,255,255,.06)}
.menu h2{margin:0 0 .8rem}
.menu-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.menu-col{background:linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01));border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);padding:14px}
.menu-col h3{margin:.2rem 0 .6rem}
.menu-list{list-style:none;margin:0;padding:0;display:grid;gap:8px}
.menu-list li{display:flex;align-items:center;justify-content:space-between;border-bottom:1px dashed rgba(255,255,255,.08);padding:6px 0}

/* Build */
.build h2{margin:0 0 .6rem}
.builder{display:grid;gap:14px;background:linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01));border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);padding:16px}
.builder-row{display:grid;gap:6px}
.builder .toppings{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:10px;border:1px dashed rgba(255,255,255,.12);border-radius:10px;padding:10px}
.builder output{font-size:1.5rem;font-weight:700}
.add-built{justify-self:start}

/* Locations */
.loc-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.loc-card{padding:14px;border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);background:linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01))}
.loc-card.highlight{outline:2px solid rgba(255,169,77,.5)}

/* Order/Cart */
.order h2{margin:0 0 .6rem}
.cart{display:grid;grid-template-columns:1.4fr .6fr;gap:16px}
.cart-items{list-style:none;margin:0;padding:0;display:grid;gap:10px}
.cart-item{display:grid;grid-template-columns:1fr auto auto;gap:10px;align-items:center;padding:10px;border:1px solid rgba(255,255,255,.08);border-radius:12px}
.cart-item .remove{opacity:.8}
.cart-summary{border:1px solid rgba(255,255,255,.08);border-radius:12px;padding:14px;display:grid;gap:8px;background:linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01))}
.cart-summary > div{display:flex;justify-content:space-between}
.cart-summary .total{font-size:1.2rem;font-weight:700}
.muted{color:var(--muted);font-size:.95rem}

/* Contact */
.contact-form{display:grid;gap:10px}
.field{display:grid;gap:6px}
input, select, textarea{
  background:#0f0f14;border:1px solid rgba(255,255,255,.12);border-radius:10px;color:#fff;padding:.7rem .75rem
}
input:focus, select:focus, textarea:focus{outline:2px solid var(--brand);border-color:transparent}

/* Footer */
.site-footer{border-top:1px solid rgba(255,255,255,.06);margin-top:28px}
.foot-grid{display:flex;justify-content:space-between;align-items:flex-start;gap:20px}
.foot-links{list-style:none;margin:0;padding:0;display:grid;gap:6px}
.brand.small span{font-size:1rem}

/* Toast */
.toast{position:fixed;left:50%;bottom:22px;transform:translateX(-50%);background:#111;color:#fff;padding:.7rem 1rem;border-radius:10px;border:1px solid rgba(255,255,255,.14);box-shadow:var(--shadow);opacity:0;pointer-events:none;transition:opacity .2s, transform .2s;z-index:200}
.toast.show{opacity:1;transform:translateX(-50%) translateY(-6px)}

/* Responsive */
@media (max-width: 900px){
  .hero-inner{grid-template-columns:1fr}
  .cards{grid-template-columns:1fr 1fr}
  .menu-grid{grid-template-columns:1fr}
  .loc-grid{grid-template-columns:1fr}
  .cart{grid-template-columns:1fr}
  .nav-toggle{display:inline-block}
  .nav{position:absolute;right:16px;top:64px;display:none;background:#0f0f14;border:1px solid rgba(255,255,255,.12);border-radius:12px}
  .nav.open{display:block}
  .nav ul{flex-direction:column;align-items:stretch;padding:10px}
  .nav a{padding:.5rem .6rem}
}
@media (prefers-reduced-motion: reduce){
  .ticker-track{animation:none}
}
CSS

cat > "$NAME/script.js" <<'JS'
// Noobiny Pizzanini — interactivity
(function(){
  const $ = (s, ctx=document)=>ctx.querySelector(s);
  const $$ = (s, ctx=document)=>[...ctx.querySelectorAll(s)];

  // Mobile nav
  const navToggle = $('.nav-toggle');
  const nav = $('#nav');
  navToggle?.addEventListener('click', ()=>{
    const open = nav.classList.toggle('open');
    navToggle.setAttribute('aria-expanded', open?'true':'false');
  });

  // Price builder
  const sizeSel = $('#size');
  const toppings = $$('#build .toppings input[type="checkbox"]');
  const priceOut = $('#priceOut');
  const addBuilt = $('.add-built');

  function calcPrice(){
    const base = parseFloat(sizeSel.selectedOptions[0].dataset.base);
    const topp = toppings.filter(t=>t.checked).length * 1.5;
    const total = (base + topp);
    priceOut.textContent = `$${total.toFixed(2)}`;
    return total;
  }
  sizeSel?.addEventListener('change', calcPrice);
  toppings.forEach(t=>t.addEventListener('change', calcPrice));
  calcPrice();

  // Cart
  const cartList = $('.cart-items');
  const subtotalEl = $('#subtotal');
  const taxEl = $('#tax');
  const totalEl = $('#total');
  const toast = $('.toast');

  let cart = [];

  function format(n){ return `$${n.toFixed(2)}`; }

  function renderCart(){
    cartList.innerHTML = '';
    cart.forEach((item, i)=>{
      const li = document.createElement('li');
      li.className='cart-item';
      li.innerHTML = `
        <span>${item.name}${item.details?` <small class="muted">(${item.details})</small>`:''}</span>
        <span>${format(item.price)}</span>
        <button class="btn small remove" aria-label="Remove ${item.name}">×</button>
      `;
      li.querySelector('.remove').addEventListener('click', ()=>{
        cart.splice(i,1); renderCart(); showToast('Removed from cart');
      });
      cartList.appendChild(li);
    });
    const sub = cart.reduce((a,c)=>a+c.price,0);
    const tax = sub * 0.08;
    const tot = sub + tax;
    subtotalEl.textContent = format(sub);
    taxEl.textContent = format(tax);
    totalEl.textContent = format(tot);
  }

  function showToast(msg){
    toast.textContent = msg;
    toast.classList.add('show');
    setTimeout(()=>toast.classList.remove('show'), 1800);
  }

  // Add buttons in featured
  $$('.add').forEach(btn=>{
    btn.addEventListener('click', ()=>{
      const name = btn.dataset.name;
      const price = parseFloat(btn.dataset.price);
      cart.push({name, price});
      renderCart();
      showToast(`${name} added to cart`);
    });
  });

  // Add from builder
  addBuilt?.addEventListener('click', ()=>{
    const size = sizeSel.value;
    const tops = toppings.filter(t=>t.checked).map(t=>t.value);
    const price = calcPrice();
    const name = `Custom ${size}"`;
    const details = tops.length? tops.join(', ') : 'Cheese only';
    cart.push({name, details, price});
    renderCart();
    showToast('Custom pizza added');
  });

  // Checkout demo
  $('.checkout')?.addEventListener('click', ()=>{
    if(cart.length===0) return showToast('Your cart is empty');
    showToast('This is a demo — no payment processed.');
  });

  // Year in footer
  $('#year').textContent = new Date().getFullYear();
})();
JS

cat > "$NAME/assets/logo.svg" <<'SVG'
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 120">
  <defs>
    <linearGradient id="g" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0" stop-color="#ff4d4f"/>
      <stop offset="1" stop-color="#ffa94d"/>
    </linearGradient>
  </defs>
  <circle cx="60" cy="60" r="56" fill="url(#g)" />
  <g transform="translate(60,60)">
    <circle r="42" fill="#111115"/>
    <path d="M0-36 A36 36 0 0 1 31  -18 L0 0Z" fill="#ffd166"/>
    <path d="M31-18 A36 36 0 0 1 31  18 L0 0Z" fill="#ef476f"/>
    <path d="M31 18 A36 36 0 0 1 0  36 L0 0Z" fill="#06d6a0"/>
    <path d="M0 36 A36 36 0 0 1 -31 18 L0 0Z" fill="#118ab2"/>
    <path d="M-31 18 A36 36 0 0 1 -31 -18 L0 0Z" fill="#ffd166"/>
    <path d="M-31 -18 A36 36 0 0 1 0 -36 L0 0Z" fill="#ef476f"/>
    <circle r="5" fill="#fff"/>
  </g>
</svg>
SVG

cat > "$NAME/assets/hero-pie.svg" <<'SVG'
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 520 520" role="img" aria-label="Decorative pizza">
  <defs>
    <filter id="shadow" x="-50%" y="-50%" width="200%" height="200%">
      <feDropShadow dx="0" dy="12" stdDeviation="16" flood-color="rgba(0,0,0,.35)"/>
    </filter>
  </defs>
  <g filter="url(#shadow)">
  <circle cx="260" cy="260" r="220" fill="#ffd166"/>
  <circle cx="260" cy="260" r="180" fill="#e85f61"/>
  <g fill="#ffe38f" opacity=".9">
    <circle cx="180" cy="260" r="34"/>
    <circle cx="300" cy="200" r="28"/>
    <circle cx="360" cy="300" r="26"/>
    <circle cx="240" cy="340" r="22"/>
    <circle cx="220" cy="180" r="20"/>
    <circle cx="140" cy="200" r="18"/>
  </g>
  <g fill="#b80d28">
    <circle cx="180" cy="180" r="24"/>
    <circle cx="320" cy="150" r="26"/>
    <circle cx="360" cy="230" r="22"/>
    <circle cx="280" cy="320" r="24"/>
    <circle cx="200" cy="320" r="20"/>
  </g>
  <path d="M260 260 L460 160" stroke="#ffefc0" stroke-width="10" stroke-linecap="round"/>
  </g>
</svg>
SVG

cat > "$NAME/assets/favicon.svg" <<'SVG'
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64">
  <defs><linearGradient id="g" x1="0" y1="0" x2="1" y2="1">
    <stop offset="0" stop-color="#ff4d4f"/>
    <stop offset="1" stop-color="#ffa94d"/>
  </linearGradient></defs>
  <rect width="64" height="64" rx="12" fill="url(#g)"/>
  <circle cx="32" cy="32" r="20" fill="#111115"/>
  <circle cx="32" cy="26" r="12" fill="#ffd166"/>
</svg>
SVG

cat > "$NAME/README.md" <<'MD'
# Noobiny Pizzanini
A playful, modern, responsive pizza site. Static (no backend).

## Files
- `index.html` — single-page site
- `styles.css` — theme and responsive layout
- `script.js` — cart demo + builder
- `assets/logo.svg`, `assets/hero-pie.svg`, `assets/favicon.svg` — vector art

## Quick start
Open `index.html` in your browser, or serve locally:

```bash
python -m http.server 8080
