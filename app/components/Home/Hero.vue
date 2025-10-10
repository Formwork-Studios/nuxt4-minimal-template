<script
  setup
  lang="ts"
></script>

<template>
  <div class="hero-container">
    <div class="grid-background">
      <svg
        class="grid-pattern"
        xmlns="http://www.w3.org/2000/svg"
      >
        <defs>
          <pattern
            id="grid"
            width="40"
            height="40"
            patternUnits="userSpaceOnUse"
          >
            <path
              d="M 40 0 L 0 0 0 40"
              fill="none"
              stroke="rgba(255,255,255,0.02)"
              stroke-width="1"
            />
          </pattern>
          <radialGradient
            id="fadeOut"
            cx="50%"
            cy="50%"
            r="70%"
          >
            <stop
              offset="0%"
              style="stop-color:white;stop-opacity:1"
            />
            <stop
              offset="60%"
              style="stop-color:white;stop-opacity:0.5"
            />
            <stop
              offset="100%"
              style="stop-color:white;stop-opacity:0"
            />
          </radialGradient>
        </defs>
        <rect
          width="100%"
          height="100%"
          fill="url(#grid)"
        />
        <rect
          width="100%"
          height="100%"
          fill="url(#fadeOut)"
          mask="url(#gridMask)"
        />
      </svg>
    </div>
    <div class="hero-background">
      <img
        src="/steam.png"
        alt="Steam"
        class="steam-image steam-base"
      />
      <img
        src="/steam.png"
        alt="Steam"
        class="steam-image steam-layer-1"
      />
      <img
        src="/steam.png"
        alt="Steam"
        class="steam-image steam-layer-2"
      />
    </div>
    <div class="gradient-overlay">
      <div class="blob blob-1"></div>
      <div class="blob blob-2"></div>
      <div class="blob blob-3"></div>
      <div class="blob blob-4"></div>
    </div>
    <div class="hero-content">
      <h1 class="text-purple-950 text-4xl md:text-6xl font-bold">
        MORE THAN A STEAM ROOM
      </h1>
    </div>
    <div
      id="bottom-row"
      class="bottom-row bg-stone-900/30 border-y"
    >
      <div class="grid grid-cols-3 grid-rows-2 w-full h-full">
        <div class="grid-box group border flex items-center justify-center"><span
            class="group-hover:text-black">BIOHACKING</span>
        </div>
        <div class="grid-box border flex items-center justify-center group"><span
            class="group-hover:text-black">CHOOSING A BRAND</span></div>
        <div class="grid-box border flex items-center justify-center"><span class="group-hover:text-black">SIZING
            QUIZ</span></div>
        <div class="grid-box border flex items-center justify-center"><span class="group-hover:text-black">DRY VS WET
            STEAM</span></div>
        <div class="grid-box border flex items-center justify-center"><span class="group-hover:text-black">USING A
            FAN</span></div>
        <div class="grid-box border flex items-center justify-center"><span class="group-hover:text-black">BUYERS
            GUIDE</span></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero-container {
  position: relative;
  height: 100vh;
  width: 100%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.grid-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -3;
  mask: radial-gradient(circle at center, black 0%, black 40%, transparent 100%);
  -webkit-mask: radial-gradient(circle at center, black 0%, black 40%, transparent 100%);
}

.grid-pattern {
  width: 100%;
  height: 100%;
}

.hero-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -2;
}

.steam-image {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 120%;
  height: calc(100% + 400px);
  object-fit: cover;
  object-position: center;
  margin-bottom: -400px;
}

.steam-base {
  opacity: 0.4;
  z-index: 1;
}

.steam-layer-1 {
  opacity: 0.08;
  z-index: 2;
  animation: steamFloat1 15s ease-in-out infinite;
}

.steam-layer-2 {
  opacity: 0.05;
  z-index: 3;
  animation: steamFloat2 20s ease-in-out infinite;
}

@keyframes steamFloat1 {

  0%,
  100% {
    transform: translateX(-50%) translate(0, 0) scale(1);
  }

  25% {
    transform: translateX(-50%) translate(5px, -10px) scale(1.02);
  }

  50% {
    transform: translateX(-50%) translate(-3px, -5px) scale(0.98);
  }

  75% {
    transform: translateX(-50%) translate(8px, -15px) scale(1.01);
  }
}

@keyframes steamFloat2 {

  0%,
  100% {
    transform: translateX(-50%) translate(0, 0) scale(1);
  }

  30% {
    transform: translateX(-50%) translate(-8px, -12px) scale(1.03);
  }

  60% {
    transform: translateX(-50%) translate(6px, -8px) scale(0.97);
  }

  90% {
    transform: translateX(-50%) translate(-4px, -18px) scale(1.02);
  }
}

.hero-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  text-align: center;
  width: 100%;
}

.gradient-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  pointer-events: none;
  filter: blur(2px);
}

.blob {
  position: absolute;
  border-radius: 50%;
  mix-blend-mode: multiply;
  filter: blur(1px);
  opacity: 0.4;
}

.blob-1 {
  width: 60vw;
  height: 60vw;
  background: radial-gradient(circle, rgba(67, 56, 202, 0.2) 0%, rgba(30, 27, 75, 0.15) 50%, transparent 70%);
  top: -20%;
  left: -20%;
  animation: morph1 20s ease-in-out infinite;
}

.blob-2 {
  width: 50vw;
  height: 50vw;
  background: radial-gradient(circle, rgba(59, 39, 176, 0.18) 0%, rgba(45, 25, 128, 0.12) 50%, transparent 70%);
  top: 20%;
  right: -15%;
  animation: morph2 25s ease-in-out infinite reverse;
}

.blob-3 {
  width: 40vw;
  height: 40vw;
  background: radial-gradient(circle, rgba(76, 29, 149, 0.15) 0%, rgba(31, 20, 87, 0.1) 50%, transparent 70%);
  bottom: -10%;
  left: 10%;
  animation: morph3 18s ease-in-out infinite;
}

.blob-4 {
  width: 45vw;
  height: 45vw;
  background: radial-gradient(circle, rgba(55, 48, 163, 0.12) 0%, rgba(29, 25, 112, 0.08) 50%, transparent 70%);
  bottom: 30%;
  right: 5%;
  animation: morph4 22s ease-in-out infinite reverse;
}

@keyframes morph1 {

  0%,
  100% {
    transform: scale(1) translate(0, 0) rotate(0deg);
    border-radius: 50% 50% 50% 50%;
  }

  25% {
    transform: scale(1.2) translate(10vw, 5vh) rotate(90deg);
    border-radius: 60% 40% 30% 70%;
  }

  50% {
    transform: scale(0.8) translate(5vw, -10vh) rotate(180deg);
    border-radius: 30% 70% 70% 30%;
  }

  75% {
    transform: scale(1.1) translate(-5vw, 8vh) rotate(270deg);
    border-radius: 70% 30% 50% 50%;
  }
}

@keyframes morph2 {

  0%,
  100% {
    transform: scale(1) translate(0, 0) rotate(0deg);
    border-radius: 40% 60% 40% 60%;
  }

  33% {
    transform: scale(1.3) translate(-8vw, 12vh) rotate(120deg);
    border-radius: 60% 40% 60% 40%;
  }

  66% {
    transform: scale(0.9) translate(12vw, -8vh) rotate(240deg);
    border-radius: 30% 70% 30% 70%;
  }
}

@keyframes morph3 {

  0%,
  100% {
    transform: scale(1) translate(0, 0) rotate(0deg);
    border-radius: 50% 50% 50% 50%;
  }

  30% {
    transform: scale(1.4) translate(8vw, -6vh) rotate(110deg);
    border-radius: 70% 30% 60% 40%;
  }

  70% {
    transform: scale(0.7) translate(-10vw, 10vh) rotate(220deg);
    border-radius: 40% 60% 30% 70%;
  }
}

@keyframes morph4 {

  0%,
  100% {
    transform: scale(1) translate(0, 0) rotate(0deg);
    border-radius: 60% 40% 50% 50%;
  }

  40% {
    transform: scale(1.1) translate(-12vw, -5vh) rotate(160deg);
    border-radius: 50% 50% 70% 30%;
  }

  80% {
    transform: scale(1.3) translate(6vw, 8vh) rotate(320deg);
    border-radius: 30% 70% 40% 60%;
  }
}

.bottom-row {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 2;
  height: 12rem;
  /* h-48 equivalent */
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.grid-box {
  transition: all 0.3s ease;
  cursor: pointer;
}

.grid-box:hover {
  background-color: rgba(255, 255, 255, 0.5);

}
</style>
