<template>
  <section id="gallery" class="bg-black/40 py-16">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-3xl font-bold mb-8" data-aos="fade-right">Gallery</h2>
      <div class="grid sm:grid-cols-2 md:grid-cols-3 gap-6">
        <div
          v-for="(img, i) in gallery"
          :key="i"
          class="rounded-xl overflow-hidden shadow-lg"
          data-aos="zoom-in"
          :data-aos-delay="i * 80"
        >
          <img
            :src="img"
            alt="Gallery photo"
            class="w-full h-64 object-cover"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "WebGallery",
  props: {
    gallery: { type: Array, required: true },
  },
};
</script>
