<template>
  hello world
  <div class="content">
    <p>
      Hello there! I'm Satyam Joshi, a passionate Frontend Developer with a
      knack for crafting beautiful and user-friendly web experiences.
    </p>
    <div class="viewheight">
      <div class="container">
        <div class="image"></div>
        <div class="pin-with-css">
          <p>Wanna watch projects preview</p>
        </div>
      </div>
    </div>
    <div class="sidecontent">
      <span>Connet with me </span>
      <span>
        <a href="https://github.com/Satyam-a-Developer" target="_blank">
          <li>github</li>
        </a>
      </span>
      <span>
        <a href="https://twitter.com/Satyamjosh44160" target="_blank">
          <li>twitter</li>
        </a>
      </span>

      <span>
        <a
          href="https://www.linkedin.com/in/satyam-joshi-9b8266240/"
          target="_blank"
        >
          <li>linkdin</li>
        </a>
      </span>
      <span>
        <a href="mailto:satyam.joshi567@gmail.com" target="_blank">
          <li>Gmail</li>
        </a>
      </span>
    </div>
    <!-- Add more content if needed -->
  </div>

  <div class="preview">
    <a href="https://portfolio-iota-eight-14.vercel.app/" target="_blank">
      portfolio
    </a>
    <aside>Made around 2020</aside>
   
  </div>
  <div class="explore">
    
    <h1>
    explor my projects
  </h1>
  <div class="back-image"></div>
  </div>  
  <div class="page2">
    <span>
      lets explore my skills<br />
      1.HTML
      <br />
      2.css
      <br />
      3.javascript
      <a href=" ">explore more</a>
    </span>
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
      tl.from("p", {
        y: 100,
        ease: "power4.out",
        delay: 1,
        opacity: 0,
        skewY: 7,
        stagger: {
          amount: 0.3,
        },
      });
      gsap.from("span", {
        y: 70,
        ease: "power4.out",
        delay: 0,
        duration: 4,
        opacity: 0,
        skewY: 7,
        stagger: {
          amount: 3,
        },
      });
      gsap.to(".sidecontent a", {
        scrollTrigger: {
          trigger: ".sidecontent",
          start: "top 10%", // Adjust start point
          end: "top 10%", // Adjust end point
          scrub: 1,
        },
        x: 200,
        rotation: 360,
        ease: "none",
      });
      var pinWithCss2 = gsap.timeline({
        scrollTrigger: {
          trigger: ".explore",
          pin: true,
          pinSpacing: true,
          start: "top 200px",
          end: "+=30%",
          scrub: 1,
        },
        y: 10, // Adjust the distance the box should move
        scale: 1,
        // rotation: 360, // Adjust rotation as needed
        ease: "none", // Linear ease
      });
      pinWithCss2.to(".explore", {
        scale: 1,
        rotation: 360,
        x: -500,
        ease: "none",
      });
      // pin with css
      var pinWithCss = gsap.timeline({
        scrollTrigger: {
          trigger: ".container",
          pin: true,
          pinSpacing: true,
          start: "top 200px",
          end: "+=120%",
          scrub: 1,
        },
        y: 10, // Adjust the distance the box should move
        scale: 1,
        // rotation: 360, // Adjust rotation as needed
        ease: "none", // Linear ease
      });
      pinWithCss.to(".container", {
        scale: 1,
        rotation: 360,
        x: 200,
        ease: "none",
      });
    },
  },
};
</script>

<style>
.explore{
  padding: 10px;
  border-radius: 30px;
  position: absolute;
  top: 190%;
  left: 68%;
}

.page2 a {
  text-decoration: none;
  color: aqua;
}
.page2 {
  width: 30vw;
  margin-top: 20vh;
  min-height: 40vh;
}
.page2 span {
  padding: 10px;
  border-radius: 30px;

  background-color: #669bbc;
  display: flex;
  justify-content: center;
  font-size: 40px;
  align-items: center;
}
.preview a {
  text-decoration: line-through;
  margin-right: 100px;
}
.preview {
  padding: 10px;
  border-radius: 30px;
  position: absolute;
  top: 130%;
  left: 68%;
  width: 450px; /* Set a maximum width to prevent overflowing */
  min-height: 40vh;
  background-color: #669bbc;
  display: flex;
  justify-content: center;
  font-size: 4vw; /* Adjust font size using relative unit */
  align-items: center;
}
.viewheight {
  height: 8000px;
}

li {
  list-style: none;
  color: #669bbc;
}
.sidecontent {
  font-size: 50px;
  word-wrap: break-word;
  background-color: rgb(0, 0, 0);
  /* width: 100vw; */
  min-width: 400px;
  padding: 50px;
  margin-left: 10vw;
  height: 40vh;
  color: white;

  display: flex;
  flex-direction: column;
  border-radius: 10px;
  align-items: center;
}
.sidecontent a {
  text-decoration: none;
}
.container {
  width: 300px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-top: 30vh;
  align-items: center;
  height: 300px;
  font-family: "Arial";
  font-size: 100px;
  text-align: center;
}

/* .container {
    transform: scale(0.5);
  } */

.pin-with-css p {
  font-size: 30px;
}
.content {
  display: flex;
  height: 200vh;
  width: 100vw;
  justify-content: space-between;
  width: 80vw;
}
p {
  font-size: 100px;
  opacity: 1;
}

.image {
  background-image: url("https://cdn-icons-png.flaticon.com/512/2351/2351966.png");
  background-position: center;
  background-size: contain;
  width: 100px;
  background-repeat: no-repeat;
  height: 100px;
}
.back-image {
  background-position: center;
  transform: rotate(180deg);
  background-image: url("https://cdn-icons-png.flaticon.com/512/2351/2351966.png");
  background-size: contain;
  width: 100px;
  background-repeat: no-repeat;
  height: 100px;

}

.scroll p {
  width: 40rem;

  font-size: 30px;
  position: relative;
  z-index: 100;
}
.scroll {
  /* position: absolute;  */
  font-size: 30px;
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  /* height: 200vh; */

  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.8);
}
</style>
