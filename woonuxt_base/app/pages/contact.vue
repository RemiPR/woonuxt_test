<!-- pages/contact.vue -->
<template>
  <div class="flex items-center justify-center p-4 my-36">
    <div class="bg-white rounded-xl backdrop-blur-lg shadow-lg p-8 max-w-2xl w-full">
      <h1 class="text-4xl font-bold text-slate-700 mb-8 flex items-center">
        {{ $t('contact.title') }}
        <Icon name="lucide:sparkles" class="ml-2 text-yellow-400" />
      </h1>
      <form @submit.prevent="handleSubmit" class="space-y-6">
        <div class="space-y-2">
          <label for="name" class="text-slate-700 font-medium">{{ $t('contact.name') }}</label>
          <input
            v-model="formData.name"
            type="text"
            id="name"
            name="name"
            class="w-full px-4 py-2 rounded-md text-slate-700 placeholder-gray-300 border focus:outline-none focus:ring-2 focus:ring-blue-400 transition duration-300"
            placeholder="Your Name"
            required />
        </div>
        <div class="space-y-2">
          <label for="email" class="text-slate-700 font-medium">{{ $t('contact.email') }}</label>
          <input
            v-model="formData.email"
            type="email"
            id="email"
            name="email"
            class="w-full px-4 py-2 rounded-md bg-white bg-opacity-20 text-slate-700 border placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-400 transition duration-300"
            placeholder="your@email.com"
            required />
        </div>
        <div class="space-y-2">
          <label for="message" class="text-slate-700 font-medium">{{ $t('contact.message') }}</label>
          <textarea
            v-model="formData.message"
            id="message"
            name="message"
            rows="4"
            class="w-full px-4 py-2 rounded-md bg-white bg-opacity-20 text-slate-700 border placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-400 transition duration-300 resize-none"
            placeholder="Your message here..."
            required></textarea>
        </div>
        <button
          type="submit"
          class="w-full bg-gradient-to-r from-blue-300 via-blue-500 to-blue-300 text-slate-700 font-bold py-3 px-6 rounded-md hover:from-blue-500 hover:via-blue-500 hover:to-blue-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 flex items-center justify-center">
          {{ $t('contact.sendMessage') }}
          <Icon name="lucide:send" class="ml-2 h-5 w-5" />
        </button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const formData = ref({
  name: '',
  email: '',
  message: '',
});

const handleSubmit = () => {
  // Handle form submission here
  console.log('Form submitted:', formData.value);
  // Reset form after submission
  formData.value = { name: '', email: '', message: '' };
};
</script>

<style scoped>
/* Add any additional styles here if needed */
</style>
