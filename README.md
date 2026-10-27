<img width="300" height="300" alt="purple_pulsing_star" src="https://github.com/user-attachments/assets/0a0296fc-a141-4383-980e-ab813d823467" />
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 500" width="100%" height="100%" preserveAspectRatio="xMidYMid meet">
  <defs>
    <!-- Background Vignette Gradient -->
    <radialGradient id="spaceGlow" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#2e1065" stop-opacity="0.6"/>
      <stop offset="45%" stop-color="#17062e" stop-opacity="0.3"/>
      <stop offset="100%" stop-color="#0a0514" stop-opacity="0"/>
    </radialGradient>

    <!-- Outer Aura Gradient -->
    <radialGradient id="outerAura" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#d8b4fe" stop-opacity="0.8"/>
      <stop offset="30%" stop-color="#a855f7" stop-opacity="0.5"/>
      <stop offset="65%" stop-color="#7e22ce" stop-opacity="0.2"/>
      <stop offset="100%" stop-color="#3b0764" stop-opacity="0"/>
    </radialGradient>

    <!-- Core Star Radial Gradient -->
    <radialGradient id="starCore" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#ffffff"/>
      <stop offset="25%" stop-color="#f3e8ff"/>
      <stop offset="55%" stop-color="#c084fc"/>
      <stop offset="85%" stop-color="#9333ea"/>
      <stop offset="100%" stop-color="#6b21a8"/>
    </radialGradient>

    <!-- Ray Gradient -->
    <linearGradient id="rayGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#ffffff" stop-opacity="0.9"/>
      <stop offset="40%" stop-color="#c084fc" stop-opacity="0.7"/>
      <stop offset="80%" stop-color="#7c3aed" stop-opacity="0.3"/>
      <stop offset="100%" stop-color="#4c1d95" stop-opacity="0"/>
    </linearGradient>

    <!-- Neon Glow Filter -->
    <filter id="purpleGlow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="10" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <!-- Intense Center Bloom Filter -->
    <filter id="intenseBloom" x="-80%" y="-80%" width="260%" height="260%">
      <feGaussianBlur in="SourceGraphic" stdDeviation="16" result="blur1"/>
      <feGaussianBlur in="SourceGraphic" stdDeviation="6" result="blur2"/>
      <feMerge>
        <feMergeNode in="blur1"/>
        <feMergeNode in="blur2"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <style>
    /* Pulsing expanding aura rings */
    .aura-wave-1 {
      transform-origin: 250px 250px;
      animation: expandAura 3s cubic-bezier(0.4, 0, 0.2, 1) infinite;
    }
    .aura-wave-2 {
      transform-origin: 250px 250px;
      animation: expandAura 3s cubic-bezier(0.4, 0, 0.2, 1) infinite 1.5s;
    }

    /* Core pulsing animation */
    .pulsing-star {
      transform-origin: 250px 250px;
      animation: starBreathing 3s ease-in-out infinite;
    }

    /* Slow ambient spinning of diagonal spikes */
    .diagonal-rays {
      transform-origin: 250px 250px;
      animation: slowRotate 24s linear infinite;
    }

    /* Shimmering horizontal/vertical flares */
    .flare-cross {
      transform-origin: 250px 250px;
      animation: crossGlimmer 2.5s ease-in-out infinite alternate;
    }

    /* Floating orbital sparkles */
    .sparkle-1 { animation: twinkle 2.2s ease-in-out infinite 0.2s; transform-origin: 180px 140px; }
    .sparkle-2 { animation: twinkle 2.7s ease-in-out infinite 0.9s; transform-origin: 340px 170px; }
    .sparkle-3 { animation: twinkle 2.0s ease-in-out infinite 1.4s; transform-origin: 150px 320px; }
    .sparkle-4 { animation: twinkle 2.4s ease-in-out infinite 0.5s; transform-origin: 320px 330px; }
    .sparkle-5 { animation: twinkle 3.0s ease-in-out infinite 1.1s; transform-origin: 250px 100px; }

    @keyframes starBreathing {
      0% {
        transform: scale(0.92);
        filter: drop-shadow(0 0 15px rgba(168, 85, 247, 0.6)) brightness(0.95);
      }
      50% {
        transform: scale(1.08);
        filter: drop-shadow(0 0 35px rgba(216, 180, 254, 0.9)) brightness(1.2);
      }
      100% {
        transform: scale(0.92);
        filter: drop-shadow(0 0 15px rgba(168, 85, 247, 0.6)) brightness(0.95);
      }
    }

    @keyframes expandAura {
      0% {
        transform: scale(0.5);
        opacity: 0.9;
      }
      70% {
        opacity: 0.4;
      }
      100% {
        transform: scale(1.4);
        opacity: 0;
      }
    }

    @keyframes crossGlimmer {
      0% {
        transform: scaleX(0.9) scaleY(1.1);
        opacity: 0.8;
      }
      100% {
        transform: scaleX(1.1) scaleY(0.9);
        opacity: 1;
      }
    }

    @keyframes slowRotate {
      0%   { transform: rotate(45deg); }
      100% { transform: rotate(405deg); }
    }

    @keyframes twinkle {
      0%, 100% {
        opacity: 0.15;
        transform: scale(0.4);
      }
      50% {
        opacity: 0.95;
        transform: scale(1.15);
      }
    }
  </style>

  <!-- Ambient Space Glow -->
  <circle cx="250" cy="250" r="230" fill="url(#spaceGlow)"/>

  <!-- Pulsing Shockwave Aura 1 -->
  <circle class="aura-wave-1" cx="250" cy="250" r="140" fill="url(#outerAura)"/>

  <!-- Pulsing Shockwave Aura 2 -->
  <circle class="aura-wave-2" cx="250" cy="250" r="140" fill="url(#outerAura)"/>

  <!-- Orbiting Sparkle Starlets -->
  <g id="sparkles">
    <!-- Top Left -->
    <path class="sparkle-1" d="M 180 130 Q 180 140 170 140 Q 180 140 180 150 Q 180 140 190 140 Q 180 140 180 130 Z" fill="#e9d5ff" filter="url(#purpleGlow)"/>
    <!-- Top Right -->
    <path class="sparkle-2" d="M 340 160 Q 340 170 330 170 Q 340 170 340 180 Q 340 170 350 170 Q 340 170 340 160 Z" fill="#f3e8ff" filter="url(#purpleGlow)"/>
    <!-- Bottom Left -->
    <path class="sparkle-3" d="M 150 312 Q 150 320 142 320 Q 150 320 150 328 Q 150 320 158 320 Q 150 320 150 312 Z" fill="#d8b4fe" filter="url(#purpleGlow)"/>
    <!-- Bottom Right -->
    <path class="sparkle-4" d="M 320 322 Q 320 330 312 330 Q 320 330 320 338 Q 320 330 328 330 Q 320 330 320 322 Z" fill="#e9d5ff" filter="url(#purpleGlow)"/>
    <!-- Top Center -->
    <path class="sparkle-5" d="M 250 94 Q 250 100 244 100 Q 250 100 250 106 Q 250 100 256 100 Q 250 100 250 94 Z" fill="#ffffff" filter="url(#purpleGlow)"/>
  </g>

  <!-- Diagonal Rotating Ray Cluster -->
  <g class="diagonal-rays">
    <!-- 4-point secondary flare -->
    <path d="M 250 130 Q 250 250 370 250 Q 250 250 250 370 Q 250 250 130 250 Q 250 250 250 130 Z"
          fill="url(#rayGradient)"
          opacity="0.6"
          filter="url(#purpleGlow)"/>
    <ellipse cx="250" cy="250" rx="130" ry="8" fill="url(#rayGradient)" opacity="0.4"/>
    <ellipse cx="250" cy="250" rx="8" ry="130" fill="url(#rayGradient)" opacity="0.4"/>
  </g>

  <!-- Main Pulsing Star System -->
  <g class="pulsing-star">
    <!-- Outer Soft Backlight Bloom -->
    <circle cx="250" cy="250" r="70" fill="url(#outerAura)" filter="url(#intenseBloom)"/>

    <!-- Sharp Horizontal & Vertical Optical Flares -->
    <g class="flare-cross" filter="url(#purpleGlow)">
      <!-- Long Horizontal Beam -->
      <path d="M 20 250 Q 250 242 480 250 Q 250 258 20 250 Z" fill="url(#rayGradient)"/>
      <!-- Long Vertical Beam -->
      <path d="M 250 20 Q 242 250 250 480 Q 258 250 250 20 Z" fill="url(#rayGradient)"/>
      <!-- Core Inner Diamond Spikes -->
      <polygon points="250,50 262,238 450,250 262,262 250,450 238,262 50,250 238,238" fill="url(#rayGradient)" opacity="0.85"/>
    </g>

    <!-- Main Curved 4-Pointed Star Body -->
    <path d="M 250 65 
             Q 250 250 435 250 
             Q 250 250 250 435 
             Q 250 250 65 250 
             Q 250 250 250 65 Z"
          fill="url(#starCore)"
          filter="url(#purpleGlow)"/>

    <!-- Intense Concentrated Center Core -->
    <circle cx="250" cy="250" r="28" fill="#ffffff" filter="url(#intenseBloom)"/>
    <circle cx="250" cy="250" r="14" fill="#ffffff"/>
  </g>
</svg>
