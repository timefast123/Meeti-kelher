<template>
  <div class="text-white font-sans">
    <!-- Hero Section -->
    <section
      class="relative bg-gradient-to-br from-pink-900 via-purple-900 to-black"
    >
      <div
        class="max-w-6xl mx-auto px-4 py-16 grid md:grid-cols-2 gap-8 items-center"
      >
        <div data-aos="fade-right">
          <h1 class="text-5xl font-extrabold mb-4">{{ profile.name }}</h1>
          <p class="text-lg text-gray-300 mb-6">{{ profile.tagline }}</p>
          <button
            class="px-6 py-3 rounded-xl bg-pink-600 hover:bg-pink-500 transition"
          >
            Watch my Private
          </button>
        </div>
        <div data-aos="zoom-in">
          <img
            src="./assets/profile.png"
            alt="Hero Portrait"
            class="rounded-2xl shadow-2xl"
          />
        </div>
      </div>
    </section>

    <!-- About Component -->
    <WebAbout :about="profile.about" />

    <!-- Gallery Component -->
    <WebGallery :gallery="gallery" />

    <!-- Highlights (inline example) -->
    <section id="highlights" class="max-w-6xl mx-auto px-4 py-16">
      <h2 class="text-3xl font-bold mb-8" data-aos="fade-up">Highlights</h2>
      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="(role, i) in roles"
          :key="i"
          class="p-6 rounded-xl bg-gray-900 border border-gray-700"
          data-aos="fade-up"
          :data-aos-delay="i * 100"
        >
          <h3 class="text-lg font-semibold">{{ role.title }}</h3>
          <p class="text-sm text-gray-400">
            {{ role.platform }} • {{ role.year }}
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Component -->
    <WebContact :profile="profile" />
  </div>
</template>

<script>
import AOS from "aos";
import "aos/dist/aos.css";

import WebAbout from "./components/WebAbout.vue";
import WebGallery from "./components/WebGallery.vue";
import WebContact from "./components/WebContact.vue";

export default {
  name: "ActressPortfolio",
  components: { WebAbout, WebGallery, WebContact },
  data() {
    return {
      profile: {
        name: "Meetii Kalher",
        tagline: "Bold. Versatile. Camera-ready.",
        about:
          "A Mumbai-based actress known for bold characters and emotional depth. With 3+ years of experience in web-series, I bring a fearless and versatile energy to every role.",
        email: "meetiikalher@gmail.com",
        phone: "+91 98XX-XXX-XXX",
      },
      gallery: [
        "https://images.unsplash.com/photo-1517841905240-472988babdf9?q=80&w=800",
        "https://images.unsplash.com/photo-1520975922284-5f99f1b5f2b3?q=80&w=800",
        "https://images.unsplash.com/photo-1512314889357-e157c22f938d?q=80&w=800",
      ],
      roles: [
        {
          title: "Lead — Midnight Streets (S3)",
          platform: "StreamX",
          year: 2025,
        },
        {
          title: "Antagonist — Neon Rules (S1)",
          platform: "VistaPlay",
          year: 2024,
        },
        {
          title: "Cameo — City of Echoes",
          platform: "FilmFest Short",
          year: 2023,
        },
      ],
    };
  },
  mounted() {
    AOS.init({ duration: 800, once: true });
  },
};
</script>
