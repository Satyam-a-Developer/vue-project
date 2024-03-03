<template>
    <div class="container">
      <div class="pin-with-css">Pin me</div>
    </div>
  </template>
  
  <script>
  import { gsap, ScrollTrigger } from "gsap/all";
  gsap.registerPlugin(ScrollTrigger);
  
  export default {
    mounted: function () {
      this.scrollAnimation();
    },
    methods: {
      scrollAnimation() {
        const tl = gsap.timeline();
  
        // pin with css
        var pinWithCss = gsap.timeline({
          scrollTrigger: {
            trigger: ".pin-with-css",
            pin: true,
            pinSpacing: true,
            markers: true,
            start: "top top",
            end: "+=300%",
            scrub: 0,
          },
          x: 200, // Adjust the distance the box should move
          scale: 1,
          rotation: 360, // Adjust rotation as needed
          ease: "none", // Linear ease
        });
        pinWithCss.to(".pin-with-css", {
          scale: 1,
          rotation: 360,
          x: 500,
          ease: "none",
        });
      },
    },
  };
  </script>
  
  <style>
  .container {
    height: 8000px;
  }
  
  .pin-with-css {
    width: 300px;
    height: 300px;
    background: #cccccc;
    font-family: "Arial";
    font-size: 100px;
    text-align: center;
  }
  
  .pin-with-css {
    transform: scale(0.5);
  }
  </style>
  