<!-- @format -->

<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import balance from "@/images/balance.jpg";
import choco from "@/images/choco.jpg";
import digital from "@/images/digital.jpg";
import yesil from "@/images/yesil_dan.jpg";
import ids from "@/images/ids.jpg";
import gym from "@/images/gym.jpg";
import im from "@/images/i'm.jpg";

import ScrollTrigger from "gsap/ScrollTrigger";

// ScrollTrigger plugin registration
gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  // Fade-in-left animation
  gsap.utils.toArray(".gsap-fade-in-left").forEach((el) => {
    gsap.fromTo(
      el,
      { opacity: 0, x: -50 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: el,
          start: "top 80%",
          end: "top 50%",
          scrub: true,
        },
      },
    );
  });

  // Fade-in-right animation
  gsap.utils.toArray(".gsap-fade-in-right").forEach((el) => {
    gsap.fromTo(
      el,
      { opacity: 0, x: 50 },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        scrollTrigger: {
          trigger: el,
          start: "top 80%",
          end: "top 50%",
          scrub: true,
        },
      },
    );
  });

  // Fade-in-up animation
  gsap.utils.toArray(".gsap-fade-in-up").forEach((el) => {
    gsap.fromTo(
      el,
      { opacity: 0, y: 50 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        stagger: 0.2,
        scrollTrigger: {
          trigger: el,
          start: "top 80%",
          end: "top 50%",
          scrub: true,
        },
      },
    );
  });

  // Hero image animation (scale and fade-in)
  gsap.fromTo(
    ".hero-img",
    { opacity: 0, scale: 0.9 },
    {
      opacity: 1,
      scale: 1,
      duration: 1,
      ease: "power2.out",
      scrollTrigger: {
        trigger: ".hero-img",
        start: "top 80%",
        end: "top 50%",
        scrub: true,
      },
    },
  );
});

const navItems = [
  { name: "Home", link: "#home" },
  { name: "About", link: "#about_me" },
  { name: "Skills", link: "#skills" },
];
</script>

<template>
  <div class="app">
    <!-- Header -->
    <header class="bg-gray-800 text-white py-4 px-8 shadow-md">
      <nav class="flex justify-between items-center">
        <h1 class="text-2xl font-bold">MyPortfolio</h1>
        <ul class="hidden md:flex space-x-6">
          <li v-for="item in navItems" :key="item.name">
            <a :href="item.link" class="text-lg hover:text-gray-400 transition">{{ item.name }}</a>
          </li>
        </ul>
      </nav>
    </header>

    <!-- Hero Section -->
    <main>
      <div
        id="home"
        class="hero py-[100px] px-8 flex flex-col lg:flex-row text-white items-center justify-around w-full bg-gray-600"
      >
        <div
          class="gsap-fade-in-left w-full lg:w-[50%] flex flex-col justify-start items-start text-left lg:text-left mb-6 lg:mb-0"
        >
          <h2 class="text-left font-bold mb-4 text-white text-4xl">Hi, I'm Orifjonov Abdulloh</h2>
          <p class="text-lg text-gray-300 mb-6">
            He crafts responsive websites where technologies meet creativity
          </p>
        </div>

        <div
          class="gsap-fade-in-right w-[80%] sm:w-[60%] lg:w-[30%] flex items-center justify-center"
        >
          <img
            :src="im"
            alt="Your Image"
            class="hero-img rounded-full shadow-lg border-4 border-blue-500 w-full"
          />
        </div>
      </div>

      <!-- About Me Section -->
      <section id="about_me" class="about-me bg-gray-600 py-16 px-4 sm:px-8">
        <h2 class="text-4xl font-bold text-center text-gray-100 mb-8">About Me</h2>
        <div class="max-w-4xl mx-auto bg-gray-300 shadow-lg rounded-lg p-6 gsap-fade-in-up">
          <p class="text-lg mb-4"><strong>Ism:</strong> Abdullox Orifjonov</p>
          <p class="text-lg mb-4"><strong>Yosh:</strong> 17</p>
          <p class="text-lg mb-4"><strong>Telefon:</strong> +998 33 011 99 01</p>
          <p class="text-lg mb-4">
            <strong>Telegram: </strong>
            <a
              href="https://t.me/Abdullox99"
              class="text-blue-600"
              target="_blank"
              rel="noopener noreferrer"
              >@Abdullox99</a
            >
          </p>
          <p class="text-lg mb-4"><strong>Manzil:</strong> Toshkent, Shayhontohur</p>
          <p class="text-lg mb-4">
            <strong>Maqsad:</strong> Senior Frontend Developer sifatida rivojlanish
          </p>
          <p class="text-lg mb-4">
            <strong>Shaxsiy Xususiyatlar:</strong> Muloqotga ochiq, muammolarni hal qilishga
            yo'naltirilgan, mas'uliyatli va o'rganishga chanqoq.
          </p>

          <p class="text-lg mb-4"><strong>Ta'lim:</strong> PDP Academy</p>
          <p class="text-lg mb-4">
            <strong>Ko'nikmalar:</strong> HTML, CSS, JavaScript, React, Redux, Redux Thunk, Redux
            Toolkit, Context API, Next.js, Vue.js
          </p>

          <p class="text-lg mb-4">
            <strong>Til Bilimlari:</strong> O'zbek tili (ona tili), Ingliz tili (30%), Rus tili
            (70%).
          </p>
        </div>
      </section>

      <!-- Portfolio Section -->
      <section id="skills" class="portfolio py-20 px-4 sm:px-8 bg-gray-600">
        <div>
          <h2 class="text-4xl font-bold text-center mb-8 text-gray-100">Skills</h2>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Cards -->
            <div
              v-for="(item, index) in [
                {
                  img: balance,
                  title: 'Wallet App',
                  desc: 'Wallet app with React',
                  link: 'https://wallet-app1.netlify.app/',
                },
                {
                  img: choco,
                  title: 'Chocolate App',
                  desc: 'Chocolate App made with Vue.js',
                  link: 'https://choco-figma.netlify.app/',
                },
                {
                  img: digital,
                  title: 'Digital Store',
                  desc: 'Digital Store web app',
                  link: 'https://digital-market-figma.netlify.app/',
                },
                {
                  img: yesil,
                  title: 'Yesil Dan',
                  desc: 'Agricultural web app',
                  link: 'https://yesil-dan.netlify.app/',
                },
                {
                  img: ids,
                  title: 'IDS',
                  desc: 'Project management app',
                  link: 'https://ids-projectt.netlify.app/',
                },
                {
                  img: gym,
                  title: 'Gym App',
                  desc: 'Gym management app',
                  link: 'https://landing.gymrat.uz/',
                },
              ]"
              :key="index"
              class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up hover:scale-105 transform transition duration-300 ease-in-out"
            >
              <img :src="item.img" :alt="item.title" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">{{ item.title }}</h3>
                <p class="text-gray-600">{{ item.desc }}</p>
                <a :href="item.link" target="_blank">
                  <button class="bg-blue-500 text-white py-1 px-3 mt-4 rounded">View More</button>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped>
.hero {
  background-image: url("https://example.com/hero-background.jpg");
  background-size: cover;
  background-position: center;
  color: white;
}

.hero-img {
  transition: transform 0.3s ease-in-out;
}

.hero-img:hover {
  transform: scale(1.05);
}

#about_me p {
  font-size: 1.125rem;
  color: #333;
}

#skills .grid div:hover {
  transform: scale(1.05);
  transition: transform 0.3s ease-in-out;
}
</style>
