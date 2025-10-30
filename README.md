## 🌟 TECH STACK

<div align="center">

### Python is the Sun ☀️ - Other Technologies Orbit Around It 🪐

<br>

<!-- 🚀 Solar System Animation Start -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="-320 -220 640 440" width="700" height="500">
  <defs>
    <filter id="glow">
      <feGaussianBlur stdDeviation="8" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <style><![CDATA[
      .orbit { fill: none; stroke: rgba(0,255,0,0.18); stroke-width:1; }
      .label { fill: #00ff00; font-family: 'Fira Code', monospace; font-size: 12px; }
      .planet text { font-size: 10px; fill: #000; }
    ]]></style>
  </defs>

  <!-- Background -->
  <rect x="-320" y="-220" width="640" height="440" fill="transparent"/>

  <!-- Sun -->
  <g>
    <circle r="35" fill="#ffeb3b" filter="url(#glow)"/>
    <circle r="20" fill="#ffcc00"/>
    <text x="-22" y="6" class="label" font-size="14">Python ☀️</text>
  </g>

  <!-- Orbit paths -->
  <circle class="orbit" r="80"/>
  <circle class="orbit" r="130"/>
  <circle class="orbit" r="180"/>
  <circle class="orbit" r="230"/>

  <!-- Planet 1 - GitHub -->
  <g class="planet">
    <g transform="translate(80,0)">
      <circle r="9" fill="#00ff00"/>
      <image href="https://techstack-generator.vercel.app/github-icon.svg" width="20" height="20" x="-10" y="-10"/>
    </g>
    <animateTransform attributeName="transform" type="rotate" from="0" to="360" dur="6s" repeatCount="indefinite"/>
  </g>

  <!-- Planet 2 - MySQL -->
  <g class="planet">
    <g transform="translate(130,0)">
      <circle r="10" fill="#33ff99"/>
      <image href="https://techstack-generator.vercel.app/mysql-icon.svg" width="24" height="24" x="-12" y="-12"/>
    </g>
    <animateTransform attributeName="transform" type="rotate" from="0" to="-360" dur="10s" repeatCount="indefinite"/>
  </g>

  <!-- Planet 3 - Docker -->
  <g class="planet">
    <g transform="translate(180,0)">
      <circle r="12" fill="#66ff66"/>
      <image href="https://techstack-generator.vercel.app/docker-icon.svg" width="26" height="26" x="-13" y="-13"/>
    </g>
    <animateTransform attributeName="transform" type="rotate" from="0" to="360" dur="15s" repeatCount="indefinite"/>
  </g>

  <!-- Planet 4 - Nginx -->
  <g class="planet">
    <g transform="translate(230,0)">
      <circle r="13" fill="#99ffcc"/>
      <image href="https://techstack-generator.vercel.app/nginx-icon.svg" width="28" height="28" x="-14" y="-14"/>
    </g>
    <animateTransform attributeName="transform" type="rotate" from="0" to="-360" dur="20s" repeatCount="indefinite"/>
  </g>

  <!-- Decorative stars -->
  <g opacity="0.6">
    <circle cx="-250" cy="-150" r="1.4" fill="#00ff00"/>
    <circle cx="200" cy="140" r="1.2" fill="#00ff00"/>
    <circle cx="-180" cy="100" r="1.1" fill="#00ff00"/>
    <circle cx="160" cy="-120" r="1.3" fill="#00ff00"/>
  </g>

</svg>
<!-- 🚀 Solar System Animation End -->

<br>

</div>
