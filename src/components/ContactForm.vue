<template>
    <div>
      <h2>Contact Us</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="form.name" required />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="form.email" required />
        </div>
        <div>
          <label for="message">Message:</label>
          <textarea id="message" v-model="form.message" required></textarea>
        </div>
        <button type="submit">Send</button>
      </form>
      <div v-if="successMessage">{{ successMessage }}</div>
      <div v-if="errorMessage">{{ errorMessage }}</div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          message: ''
        },
        successMessage: '',
        errorMessage: ''
      };
    },
    methods: {
      async submitForm() {
        try {
          const response = await fetch('http://localhost:3000/send-email', {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json'
            },
            body: JSON.stringify(this.form)
          });
          const data = await response.json();
          if (response.ok) {
            this.successMessage = data.message;
            this.errorMessage = '';
            this.form.name = '';
            this.form.email = '';
            this.form.message = '';
          } else {
            this.errorMessage = data.error;
            this.successMessage = '';
          }
        } catch (error) {
          this.errorMessage = 'An error occurred while sending the email.';
          this.successMessage = '';
        }
      }
    }
  };
  </script>
  
  <style scoped>
  form div {
    margin-bottom: 10px;
  }
  </style>
  