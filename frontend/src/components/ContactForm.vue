<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-100 py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-md w-full space-y-8">
      <div>
        <h2 class="mt-6 text-center text-3xl font-extrabold text-gray-900">Contact Us</h2>
        <p class="mt-2 text-center text-sm text-gray-600">
          We'd love to hear from you!
        </p>
      </div>
      <form @submit.prevent="submitForm" class="mt-8 space-y-6">
        <div class="rounded-md shadow-sm -space-y-px">
          <div>
            <label for="name" class="sr-only">Name</label>
            <input type="text" v-model="form.name" id="name" required
              class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-t-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm"
              placeholder="Name">
          </div>
          <div>
            <label for="email" class="sr-only">Email</label>
            <input type="email" v-model="form.email" id="email" required
              class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm"
              placeholder="Email">
          </div>
          <div>
            <label for="message" class="sr-only">Message</label>
            <textarea v-model="form.message" id="message" required
              class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-b-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm"
              placeholder="Message"></textarea>
          </div>
        </div>
        <div>
          <button type="submit"
            class="group relative w-full flex justify-center py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
            Send
          </button>
        </div>
      </form>
      <p v-if="successMessage" class="mt-2 text-center text-sm text-green-600">
        {{ successMessage }}
      </p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: '',
      },
      successMessage: '',
    };
  },
  methods: {
    async submitForm() {
      try {
        await axios.post('http://localhost:3000/api/contact', this.form);
        this.successMessage = 'Your message has been sent!';
        this.form = { name: '', email: '', message: '' };
      } catch (error) {
        console.error('Error sending message:', error);
      }
    },
  },
};
</script>
