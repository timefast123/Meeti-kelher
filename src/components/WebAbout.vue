<template>
  <section id="about" class="max-w-6xl mx-auto px-4 py-16">
    <h2 class="text-3xl font-bold mb-6" data-aos="fade-up">About</h2>
    <p
      class="text-gray-300 leading-relaxed"
      data-aos="fade-up"
      data-aos-delay="100"
    >
      {{ about }}
    </p>
  </section>
</template>

<script>
export default {
  name: "WebAbout",
  props: {
    about: { type: String, required: true },
  },
};
</script>
