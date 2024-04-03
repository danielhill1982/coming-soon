 
<script setup lang="ts">

import { gsap } from "gsap";

onMounted(() => {
window.addEventListener("load", () => {
const heroOverlay = document.querySelector(".hero-overlay");
const heroOverlayHeading = document.querySelector("#hero-overlay-heading");
var tl = gsap.timeline();
tl.from("#hero-overlay-line", {
  duration: 5,
  scaleX: 0,
  transformOrigin: "right center",
});
tl.from(heroOverlayHeading, {
  duration: 1.2,
  opacity: 0,
  y: 30,
  transformOrigin: "bottom",
  ease: "back",
});
tl.to(heroOverlay,{
    duration: 1.5,
    yPercent: 0,
    height:0,
    transformOrigin: "bottom"
  });
tl.to(heroOverlayHeading,{
    duration: 1.5,
    autoAlpha:0
  },"<");
tl.to("#hero-overlay-line", {
    autoAlpha:0
  },"<");
});
});
</script>

<style>
*{
  margin: 0;
}
html {
  margin: 0;
  background: url("https://picsum.photos/3840/2160?random");
  height: 100%;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

body {
  margin: 0;
}

.base {
  height:100vh;
  
}

.hero-overlay {
  background: url("https://picsum.photos/3840/2160?random");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #000;
  position: absolute;
  z-index:100;
  inset:0;
}

.hero {
  position:relative;
  z-index:10;
  color: #fff;
  background-color: rgb(0, 0, 0, 0.75);
}

.heading-primary {
  padding-top:40vh;
  text-align:center;
  font-size: 50px;
}

#hero-overlay-heading {
  font-weight:700;
}

.line {
  width: 300px;
  height: 10px;
  background: white;
  margin-top:30px;
  margin-inline: auto;

}

#hero-overlay-line {
  background:#fff;
}
</style>

<template>
    <div class="hero base">

<h1 id="hero-heading" class="heading-primary">
  A new personal website is <br>being created here.
</h1>
<div id="hero-line" class="line"></div>

</div>
<div class="hero-overlay base">

<p id="hero-overlay-heading" class="heading-primary">
  A new personal website is <br>being created here.
</p>
<div id="hero-overlay-line" class="line"></div>
</div>
</template> 
