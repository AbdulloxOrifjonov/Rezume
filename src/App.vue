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

// ScrollTrigger plaginini o‘rnatish
gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  // Fade-in-left animatsiyasi
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

  // Fade-in-right animatsiyasi
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

  // Fade-in-up animatsiyasi
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
        class="hero py-[100px] px-8 flex flex-col lg:flex-row text-white items-center justify-around w-full"
      >
        <div class="gsap-fade-in-left w-full lg:w-[50%] text-center lg:text-left mb-6 lg:mb-0">
          <h2 class="text-4xl font-bold mb-4">
            Hi, I'm <span class="text-blue-400">Orifjonov Abdulloh</span>
          </h2>
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
            class="rounded-full shadow-lg border-4 border-blue-500 w-full"
          />
        </div>
      </div>

      <!-- About Me Section -->
      <section id="about_me" class="about-me bg-gray-100 py-16 px-4 sm:px-8">
        <h2 class="text-4xl font-bold text-center text-gray-800 mb-8">About Me</h2>
        <div class="max-w-4xl mx-auto bg-white shadow-lg rounded-lg p-6 gsap-fade-in-up">
          <p class="text-lg text-gray-700 mb-4"><strong>Ism:</strong> Abdullox Orifjonov</p>
          <p class="text-lg text-gray-700 mb-4"><strong>Tug'ilgan sana:</strong> 15-yanvar, 2008</p>
          <p class="text-lg text-gray-700 mb-4"><strong>Telefon:</strong> +998 33 011 99 01</p>
          <p class="text-lg text-gray-700 mb-4">
            <strong>Email:</strong> abdulloxstrike1@gmail.com
          </p>
          <p class="text-lg text-gray-700 mb-4">
            <strong>Telegram: </strong>
            <a
              href="https://t.me/Abdullox99"
              class="text-blue-600"
              target="_blank"
              rel="noopener noreferrer"
              >@Abdullox99</a
            >
          </p>
          <p class="text-lg text-gray-700 mb-4"><strong>Manzil:</strong> Toshkent, Shayhontohur</p>
          <p class="text-lg text-gray-700 mb-4">
            <strong>Maqsad:</strong> Senior Frontend Developer sifatida rivojlanish
          </p>
          <p class="text-lg text-gray-700 mb-4"><strong>Ta'lim:</strong> PDP Academy</p>
          <p class="text-lg text-gray-700">
            <strong>Ko'nikmalar:</strong> HTML, CSS, JavaScript, React, Redux, Redux Thunk, Redux
            Toolkit, Context API, Next.js, Vue.js
          </p>
        </div>
      </section>

      <!-- Portfolio Section -->
      <section id="skills" class="portfolio py-20 px-4 sm:px-8 bg-gray-500">
        <div>
          <h2 class="text-4xl font-bold text-center mb-8 text-gray-100">Skills</h2>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Balance App -->
            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="balance" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Wallet App</h3>
                <p class="text-gray-600">Wallet app with React</p>
                <a href="https://wallet-app1.netlify.app/" target="_blank">
                  <button class="bg-blue-500 text-white py-1 px-3 mt-4 rounded">View More</button>
                </a>
              </div>
            </div>
            <!-- Digital Market -->
            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="digital" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Digital Market</h3>
                <p class="text-gray-600">This website is about digital marketing</p>
                <a href="https://digital-market-figma.netlify.app/" target="_blank">
                  <button class="bg-blue-500 text-white py-1 px-3 mt-4 rounded">View More</button>
                </a>
              </div>
            </div>
            <!-- Choco Market -->
            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="choco" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Choco Market</h3>
                <p class="text-gray-600">Website about chocolate marketing</p>
                <a href="https://choco-figma.netlify.app/" target="_blank">
                  <button class="bg-blue-500 text-white py-1 px-3 mt-4 rounded">View More</button>
                </a>
              </div>
            </div>
            <!-- IDS -->
            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="ids" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Web-Site IDS</h3>
                <p class="text-gray-600">This real project is about IDS company</p>
                <a href="https://ids-projectt.netlify.app/" target="_blank">
                  <button class="bg-blue-500 text-white py-1 px-3 mt-4 rounded">View More</button>
                </a>
              </div>
            </div>
            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="yesil" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Yesil Dan</h3>
                <p class="text-gray-600">This website provides information about the flour mill</p>
                <a href="https://yesil-dan.netlify.app/" target="_blank">
                  <button
                    class="bg-blue-500 text-white py-1 px-3 mt-4 rounded hover:bg-blue-400 transition"
                  >
                    View More
                  </button>
                </a>
              </div>
            </div>

            <div class="bg-gray-100 shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img :src="gym" alt="" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">GYM Rat</h3>
                <p class="text-gray-600">
                  The task of this GYM Rat SRM appliaction is to automate the work of Gyms
                </p>
                <a href="https://landing.gymrat.uz/" target="_blank">
                  <button
                    class="bg-blue-500 text-white py-1 px-3 mt-4 rounded hover:bg-blue-400 transition"
                  >
                    View More
                  </button>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-4 text-center">
      <p>&copy; 2024 MyPortfolio. All Rights Reserved.</p>
    </footer>
  </div>
</template>

<style scoped>
.hero {
  background: #2a2a2a;
}

.gsap-fade-in-up {
  opacity: 0;
  transform: translateY(50px);
}
</style>
