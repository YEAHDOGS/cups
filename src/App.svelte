<script>
  import { onMount } from "svelte";
  import badge from "./assets/made-by-dogs.png";

  onMount(() => {
    const io = new IntersectionObserver(
      (entries) => {
        for (const e of entries) {
          if (e.isIntersecting) {
            e.target.querySelectorAll(".rv").forEach((el) => el.classList.add("in"));
          }
        }
      },
      { threshold: 0.3 }
    );
    document.querySelectorAll(".panel").forEach((p) => io.observe(p));
    return () => io.disconnect();
  });
</script>

<svelte:head>
  <title>CUPS — Bamboo Straws by DOGS</title>
  <meta name="description" content="Bamboo straws. Bamboo utensils. Bamboo cups. And the ice-pocket cup concept. Two words: bamboo straws." />
</svelte:head>

<!-- reusable bamboo-forest backdrop -->
{#snippet forest(uid)}
  <svg class="bg-art drift" viewBox="0 0 400 800" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
    <defs>
      <linearGradient id="sky-{uid}" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0" stop-color="#0c1710" />
        <stop offset="0.55" stop-color="#060c07" />
        <stop offset="1" stop-color="#030503" />
      </linearGradient>
      <linearGradient id="stalk-{uid}" x1="0" y1="0" x2="1" y2="0">
        <stop offset="0" stop-color="#2c4a12" />
        <stop offset="0.5" stop-color="#5c8a1e" />
        <stop offset="1" stop-color="#223a0d" />
      </linearGradient>
      <linearGradient id="stalkback-{uid}" x1="0" y1="0" x2="1" y2="0">
        <stop offset="0" stop-color="#16280a" />
        <stop offset="0.5" stop-color="#2b4a12" />
        <stop offset="1" stop-color="#101d07" />
      </linearGradient>
      <radialGradient id="mist-{uid}" cx="0.5" cy="0.5" r="0.5">
        <stop offset="0" stop-color="#a3e635" stop-opacity="0.14" />
        <stop offset="1" stop-color="#a3e635" stop-opacity="0" />
      </radialGradient>
      <filter id="blur-{uid}" x="-50%" y="-50%" width="200%" height="200%">
        <feGaussianBlur stdDeviation="7" />
      </filter>
    </defs>
    <rect width="400" height="800" fill="url(#sky-{uid})" />
    <polygon points="0,180 400,60 400,220 0,340" fill="#a3e635" opacity="0.045" />
    <polygon points="60,120 200,40 260,140 120,220" fill="#a3e635" opacity="0.035" />
    <g filter="url(#blur-{uid})" opacity="0.65">
      <rect x="40" y="-20" width="9" height="560" rx="4.5" fill="url(#stalkback-{uid})" />
      <rect x="120" y="60" width="9" height="620" rx="4.5" fill="url(#stalkback-{uid})" />
      <rect x="210" y="-40" width="9" height="600" rx="4.5" fill="url(#stalkback-{uid})" />
      <rect x="300" y="30" width="9" height="640" rx="4.5" fill="url(#stalkback-{uid})" />
      <rect x="360" y="-10" width="9" height="580" rx="4.5" fill="url(#stalkback-{uid})" />
    </g>
    <ellipse cx="200" cy="640" rx="220" ry="120" fill="url(#mist-{uid})" />
    <g opacity="0.9">
      <rect x="90" y="40" width="13" height="700" rx="6.5" fill="url(#stalk-{uid})" />
      <rect x="88" y="220" width="17" height="7" rx="3.5" fill="#16280a" opacity="0.8" />
      <rect x="88" y="430" width="17" height="7" rx="3.5" fill="#16280a" opacity="0.8" />
      <rect x="250" y="-20" width="13" height="760" rx="6.5" fill="url(#stalk-{uid})" />
      <rect x="248" y="170" width="17" height="7" rx="3.5" fill="#16280a" opacity="0.8" />
      <rect x="248" y="390" width="17" height="7" rx="3.5" fill="#16280a" opacity="0.8" />
      <rect x="248" y="600" width="17" height="7" rx="3.5" fill="#16280a" opacity="0.8" />
    </g>
    <g fill="#3d5c14" opacity="0.85">
      <ellipse cx="140" cy="180" rx="34" ry="9" transform="rotate(-24 140 180)" />
      <ellipse cx="150" cy="200" rx="30" ry="8" transform="rotate(-14 150 200)" />
      <ellipse cx="300" cy="300" rx="36" ry="9" transform="rotate(20 300 300)" />
      <ellipse cx="290" cy="322" rx="30" ry="8" transform="rotate(30 290 322)" />
      <ellipse cx="60" cy="480" rx="32" ry="9" transform="rotate(-18 60 480)" />
    </g>
    <g opacity="0.95">
      <rect x="8" y="120" width="20" height="700" rx="10" fill="url(#stalk-{uid})" />
      <rect x="5" y="330" width="26" height="9" rx="4.5" fill="#0f1f06" opacity="0.85" />
      <rect x="5" y="560" width="26" height="9" rx="4.5" fill="#0f1f06" opacity="0.85" />
      <rect x="372" y="60" width="20" height="760" rx="10" fill="url(#stalk-{uid})" />
      <rect x="369" y="260" width="26" height="9" rx="4.5" fill="#0f1f06" opacity="0.85" />
      <rect x="369" y="500" width="26" height="9" rx="4.5" fill="#0f1f06" opacity="0.85" />
    </g>
    <ellipse cx="200" cy="760" rx="240" ry="90" fill="url(#mist-{uid})" />
  </svg>
  <div class="scrim"></div>
{/snippet}

<main class="scroller">

  <!-- HERO -->
  <section class="panel" aria-label="Bamboo straws hero">
    {@render forest("hero")}
    <div class="wrap">
      <p class="kicker rv">Cups &middot; by DOGS</p>
      <h1 class="rv d1">BAMBOO<br />STRAWS<span class="dot">.</span></h1>
      <p class="sub rv d2">Two words. <b>The whole plan.</b></p>
      <a class="cta rv d3" href="#problem">See the plan</a>
    </div>
    <span class="cue">scroll</span>
  </section>

  <!-- PROBLEM -->
  <section class="panel" id="problem" aria-label="Why paper straws failed">
    <svg class="bg-art" viewBox="0 0 400 800" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
      <defs>
        <linearGradient id="pbg" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0" stop-color="#141007" />
          <stop offset="1" stop-color="#050403" />
        </linearGradient>
        <linearGradient id="soda" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0" stop-color="#3a2c12" />
          <stop offset="1" stop-color="#1c1508" />
        </linearGradient>
      </defs>
      <rect width="400" height="800" fill="url(#pbg)" />
      <g opacity="0.9">
        <path d="M150 300 L250 300 L235 640 L165 640 Z" fill="none" stroke="#8a7a55" stroke-width="5" opacity="0.7" />
        <path d="M154 340 L246 340 L235 640 L165 640 Z" fill="url(#soda)" opacity="0.85" />
        <path d="M205 300 C 200 220, 190 180, 150 150" fill="none" stroke="#c9b68a" stroke-width="13" stroke-linecap="round" opacity="0.85" />
        <path d="M150 150 l -12 -4 M150 150 l -4 -12" stroke="#c9b68a" stroke-width="8" stroke-linecap="round" opacity="0.5" />
      </g>
      <ellipse cx="200" cy="680" rx="150" ry="40" fill="#a3e635" opacity="0.05" />
    </svg>
    <div class="scrim"></div>
    <div class="wrap">
      <p class="kicker rv">01 &middot; The problem</p>
      <h2 class="rv d1">PAPER GOES <em>SOGGY.</em></h2>
      <p class="sub rv d2">Plastic never dies. <b>There's a third way.</b></p>
    </div>
  </section>

  <!-- LINEUP -->
  <section class="panel" id="lineup" aria-label="The product line">
    {@render forest("lineup")}
    <div class="wrap">
      <p class="kicker rv">02 &middot; The lineup</p>
      <h2 class="rv d1">STRAWS.<br />SPOONS.<br /><em>CUPS.</em></h2>
      <div class="cards">
        <div class="card rv d1">
          <p class="tag">Straws</p>
          <h3>Stiff to the last sip.</h3>
          <p>Real bamboo. <b>Washable. Compostable.</b> Not paper.</p>
        </div>
        <div class="card rv d2">
          <p class="tag">Utensils</p>
          <h3>Spoons that don't snap.</h3>
          <p>Ice-cream spoons. Forks. Knives. <b>The full table.</b></p>
        </div>
        <div class="card rv d3">
          <p class="tag">Cups</p>
          <h3>Bamboo, cold to the end.</h3>
          <p>The cup, <b>rebuilt from the plant up.</b></p>
        </div>
      </div>
    </div>
  </section>

  <!-- ICE-POCKET CONCEPT -->
  <section class="panel" id="concept" aria-label="The ice-pocket cup concept">
    <svg class="bg-art" viewBox="0 0 400 800" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
      <defs>
        <linearGradient id="cbg" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0" stop-color="#081018" />
          <stop offset="1" stop-color="#030507" />
        </linearGradient>
        <linearGradient id="drink" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0" stop-color="#7dd3fc" stop-opacity="0.55" />
          <stop offset="1" stop-color="#0c4a6e" stop-opacity="0.85" />
        </linearGradient>
        <linearGradient id="icepk" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0" stop-color="#bae6fd" />
          <stop offset="1" stop-color="#38bdf8" />
        </linearGradient>
        <linearGradient id="bamstalk" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0" stop-color="#4d7c0f" />
          <stop offset="0.5" stop-color="#a3e635" />
          <stop offset="1" stop-color="#3f6212" />
        </linearGradient>
      </defs>
      <rect width="400" height="800" fill="url(#cbg)" />
      <g opacity="0.95">
        <path d="M120 260 L280 260 L262 660 L138 660 Z" fill="rgba(163,230,53,0.06)" stroke="#f2f7ec" stroke-width="4" />
        <path d="M136 330 L264 330 L262 660 L138 660 Z" fill="url(#drink)" opacity="0.8" />
        <rect x="112" y="380" width="22" height="150" rx="11" fill="url(#icepk)" opacity="0.95" />
        <rect x="266" y="380" width="22" height="150" rx="11" fill="url(#icepk)" opacity="0.95" />
        <rect x="112" y="560" width="22" height="80" rx="11" fill="url(#icepk)" opacity="0.7" />
        <rect x="266" y="560" width="22" height="80" rx="11" fill="url(#icepk)" opacity="0.7" />
        <rect x="196" y="140" width="12" height="180" rx="6" fill="url(#bamstalk)" transform="rotate(6 200 200)" />
        <path d="M120 440 l -34 -10 M112 380 l -30 -34" stroke="#7dd3fc" stroke-width="2" stroke-dasharray="5 4" opacity="0.8" />
        <text x="20" y="356" fill="#7dd3fc" font-size="13" font-family="monospace" opacity="0.9">ice stays</text>
        <text x="20" y="372" fill="#7dd3fc" font-size="13" font-family="monospace" opacity="0.9">sealed</text>
        <path d="M280 500 l 34 8" stroke="#f2f7ec" stroke-width="2" stroke-dasharray="5 4" opacity="0.6" />
        <text x="318" y="512" fill="#f2f7ec" font-size="13" font-family="monospace" opacity="0.7">drink</text>
        <text x="318" y="528" fill="#f2f7ec" font-size="13" font-family="monospace" opacity="0.7">stays pure</text>
      </g>
    </svg>
    <div class="scrim"></div>
    <div class="wrap">
      <p class="kicker rv">03 &middot; Concept &middot; prototype only</p>
      <h2 class="rv d1">THE<br />ICE-POCKET<br />CUP<span class="dot" style="color:#7dd3fc">.</span></h2>
      <p class="sub rv d2">Ice lives <b>in the wall.</b></p>
      <p class="sub rv d3">Meltwater <b>never touches</b> your drink.</p>
      <p class="concept-note rv d3">Unvalidated concept. No product exists yet. We're prototyping it.</p>
    </div>
  </section>

  <!-- WHY NOBODY DID THIS -->
  <section class="panel" id="why" aria-label="Why bamboo straws have not taken off">
    {@render forest("why")}
    <div class="wrap">
      <p class="kicker rv">04 &middot; The real story</p>
      <h2 class="rv d1">WHY NOBODY<br />DID <em>THIS.</em></h2>
      <div class="facts">
        <div class="fact rv d1"><span class="n">01</span><p>Bamboo costs <b>more than paper.</b></p></div>
        <div class="fact rv d1"><span class="n">02</span><p>Grown, cut, and finished <b>in Asia.</b></p></div>
        <div class="fact rv d2"><span class="n">03</span><p>Paper giants <b>own the supply contracts.</b></p></div>
        <div class="fact rv d2"><span class="n">04</span><p>Bamboo <b>molds</b> if you neglect it.</p></div>
        <div class="fact rv d3"><span class="n">05</span><p>Nobody built the <b>brand.</b> We are.</p></div>
      </div>
    </div>
  </section>

  <!-- HOW WE WIN -->
  <section class="panel" id="win" aria-label="How DOGS wins">
    {@render forest("win")}
    <div class="wrap">
      <p class="kicker rv">05 &middot; The play</p>
      <h2 class="rv d1">HOW <em>DOGS</em><br />WINS.</h2>
      <p class="sub rv d1">Single-use. <b>Compostable.</b></p>
      <p class="sub rv d2">Built where bamboo grows. <b>Sold where paper failed.</b></p>
    </div>
  </section>

  <!-- ROADMAP -->
  <section class="panel" id="roadmap" aria-label="Roadmap">
    {@render forest("road")}
    <div class="wrap">
      <p class="kicker rv">06 &middot; Roadmap</p>
      <h2 class="rv d1">STRAWS<br /><em>FIRST.</em></h2>
      <div class="steps">
        <div class="step rv d1">
          <span class="n">1</span>
          <div><h3>Straws</h3><p>Now. The wedge.</p></div>
        </div>
        <div class="step rv d2">
          <span class="n">2</span>
          <div><h3>Utensils</h3><p>Next. The full table.</p></div>
        </div>
        <div class="step rv d3">
          <span class="n">3</span>
          <div><h3>Ice-pocket cup</h3><p>The moonshot. Patented or bust.</p></div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER: badge only, zero copy, reveal-free -->
  <footer class="panel" aria-label="Made by DOGS">
    {@render forest("foot")}
    <div class="wrap">
      <a class="badge" href="https://wearedogs.net" aria-label="Made by DOGS">
        <img src={badge} alt="Made by DOGS" />
      </a>
    </div>
  </footer>

</main>
