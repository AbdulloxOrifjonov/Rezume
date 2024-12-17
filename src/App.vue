<!-- @format -->

<script setup>
import { onMounted } from "vue";
import gsap from "gsap";

import ScrollTrigger from "gsap/ScrollTrigger";

// ScrollTrigger plaginini o‘rnatish
gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  // Fade-in-left animatsiyasi
  gsap.utils.toArray(".gsap-fade-in-left").forEach((el) => {
    gsap.fromTo(
      el,
      {
        opacity: 0,
        x: -50,
      },
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
      {
        opacity: 0,
        x: 50,
      },
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
      {
        opacity: 0,
        y: 50,
      },
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
  { name: "Home", link: "#" },
  { name: "About", link: "#" },
  { name: "Portfolio", link: "#" },
  { name: "Contact", link: "#" },
];
</script>

<template>
  <div class="app">
    <!-- Header -->
    <header class="bg-gray-800 text-white py-4 px-8 shadow-md">
      <nav class="flex justify-between items-center">
        <h1 class="text-2xl font-bold">MyPortfolio</h1>
        <ul class="flex space-x-6">
          <li v-for="item in navItems" :key="item.name">
            <a :href="item.link" class="text-lg hover:text-gray-400 transition">{{ item.name }}</a>
          </li>
        </ul>
      </nav>
    </header>

    <!-- Hero Section -->
    <main class="">
      <div class="hero py-20 px-8 flex text-white items-center justify-between w-full">
        <div class="gsap-fade-in-left w-[50%]">
          <h2 class="text-4xl font-bold mb-4">
            Hi, I'm <span class="text-blue-400">Orifjonov Abdulloh</span>
          </h2>
          <p class="text-lg text-gray-300 mb-6">
            A passionate web developer who loves crafting beautiful and functional websites. Let me
            help bring your ideas to life.
          </p>
          <button class="bg-blue-500 text-white py-2 px-4 rounded hover:bg-blue-400 transition">
            Download Resume
          </button>
        </div>

        <div class="gsap-fade-in-right w-[50%] flex items-center justify-center">
          <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTtuphMb4mq-EcVWhMVT8FCkv5dqZGgvn_QiA&s"
            alt="Your Image"
            class="rounded-full shadow-lg border-4 border-blue-500"
          />
        </div>
      </div>
      <section class="portfolio py-20 px-8 bg-gray-500">
        <div class="">
          <h2 class="text-3xl font-bold text-center mb-8 text-white">My Works</h2>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
            <div class="bg-white shadow-lg rounded overflow-hidden gsap-fade-in-up">
              <img src="https://via.placeholder.com/300x200" alt="Project Image" class="w-full" />
              <div class="p-4">
                <h3 class="text-xl font-bold mb-2">Project Title</h3>
                <p class="text-gray-600">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus lacinia odio
                  vitae vestibulum.
                </p>
                <button
                  class="bg-blue-500 text-white py-1 px-3 mt-4 rounded hover:bg-blue-400 transition"
                >
                  View More
                </button>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Portfolio Section -->

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

/* .gsap-fade-in-left {
  opacity: 0;
  transform: translateX(-50px);
} */

.gsap-fade-in-right {
  opacity: 0;
  transform: translateX(50px);
}

.gsap-fade-in-up {
  opacity: 0;
  transform: translateY(50px);
}
</style>
