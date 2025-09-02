<template>
  <section id="contact" class="bg-black/60 py-16">
    <div class="max-w-4xl mx-auto px-4 grid md:grid-cols-2 gap-10">
      <!-- Info -->
      <div data-aos="fade-right">
        <h2 class="text-3xl font-bold mb-4">Contact</h2>
        <p class="text-gray-300 mb-4">For bookings or collaborations:</p>
        <p class="text-gray-400">📧 {{ profile.email }}</p>
        <p class="text-gray-400">📱 {{ profile.phone }}</p>
      </div>

      <!-- Form -->
      <form @submit.prevent="submitForm" class="space-y-4" data-aos="fade-left">
        <input
          v-model="form.name"
          type="text"
          placeholder="Your Name"
          class="w-full px-4 py-3 rounded-xl bg-gray-800 border border-gray-700 focus:border-pink-500"
        />
        <input
          v-model="form.email"
          type="email"
          placeholder="Your Email"
          class="w-full px-4 py-3 rounded-xl bg-gray-800 border border-gray-700 focus:border-pink-500"
        />
        <textarea
          v-model="form.message"
          placeholder="Your Message"
          rows="4"
          class="w-full px-4 py-3 rounded-xl bg-gray-800 border border-gray-700 focus:border-pink-500"
        ></textarea>
        <button
          type="submit"
          class="w-full px-5 py-3 rounded-xl bg-pink-600 hover:bg-pink-500 font-semibold"
        >
          Send
        </button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: "WebContact",
  props: {
    profile: { type: Object, required: true },
  },
  data() {
    return {
      form: { name: "", email: "", message: "" },
    };
  },
  methods: {
    submitForm() {
      alert(`Message sent by ${this.form.name}!`);
      this.form = { name: "", email: "", message: "" };
    },
  },
};
</script>
