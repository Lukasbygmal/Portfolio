<template>
    <div class="social-button-container">
      <button @click="openUrl" class="social-button">
        <img :src="image" alt="Social Logo" class="social-logo" />
      </button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SocialButton',
    props: {
      url: {
        type: String,
        required: true,
      },
      image: {
        type: String,
        required: true,
      },
    },
    methods: {
      openUrl() {
        window.open(this.url, '_blank');
      },
    },
  };
  </script>
  
  <style scoped>
  .social-button-container {
    margin-top: 20px;
  }
  
  .social-button {
    background: none;
    border: none;
    cursor: pointer;
    padding: 10px;
  }
  
  .social-logo {
    width: 40px;
    height: 40px;
  }
  
  .social-button:hover .social-logo {
    transform: scale(1.1);
    transition: transform 0.2s ease-in-out;
  }
  </style>
  