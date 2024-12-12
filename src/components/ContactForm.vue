<template>
  <div class="form-container">
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="name"></label>
        <input type="text" id="name" v-model="form.name" placeholder="Name" required />
      </div>
      <div class="form-group">
        <label for="email"></label>
        <input type="email" id="email" v-model="form.email" placeholder="Email" required />
      </div>
      <div class="form-group">
        <label for="message"></label>
        <textarea id="message" v-model="form.message" placeholder="Message" required></textarea>
      </div>
      <button type="submit">Send</button>
    </form>
    <div v-if="successMessage" class="success-message">{{ successMessage }}</div>
    <div v-if="errorMessage" class="error-message">{{ errorMessage }}</div>
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
        const response = await fetch('https://formspree.io/f/xnqeebwp', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify(this.form)
        });

        if (response.ok) {
          this.successMessage = 'Thank you for your message!';
          this.errorMessage = '';
          this.form.name = '';
          this.form.email = '';
          this.form.message = '';
        } else {
          this.errorMessage = 'Något gick fel. Försök igen senare.';
          this.successMessage = '';
        }
      } catch (error) {
        console.error('Error submitting form:', error);
        this.errorMessage = 'Något gick fel. Försök igen senare.';
        this.successMessage = '';
      }
    }
  }
};
</script>

<style scoped>
.form-container {
  width: 100%;
  max-width: 500px;
  margin: 10px auto;
  padding: 0 10px;
  box-sizing: border-box;
  overflow: hidden;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 10px;
  font-size: 1.2em;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #231F20; 
  border-width: 2px;
  box-shadow: 0 0 10px rgba(49, 49, 50, 0.5);
}

.form-group textarea {
  resize: vertical;
  height: 150px;
}

button {
  padding: 10px 20px;
  font-size: 1.2em;
  color: #fff;
  background-color: #231F20;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: black;
}



.success-message {
  color: green;
  margin-top: 20px;
}

.error-message {
  color: red;
  margin-top: 20px;
}

::placeholder {
  font-size: 1.3em;
  color: #808080;
}

@media (max-width: 768px) {
  .form-container {
    padding: 0 10px;
  }
  .form-group input,
  .form-group textarea {
    font-size: 1em; 
  }
  
}
.success-message {
color: black; 
  font-weight: bold;
}

.error-message {
  color: black; 
  font-weight: bold;
}
</style>
