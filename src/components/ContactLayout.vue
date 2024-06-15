<template>
    <div class="main-container">
      <div class="content-container">
        <div class="contact-title">
          <h1>Kontakta mig</h1>
        </div>
        <div class="contact-email">
          Email: Lukasbygmal@gmail.com <br> eller   formuläret nedan 
        </div>
        <ContactForm/> 
      </div>
    </div>
  </template>
  
  <script>
  import ContactForm from './ContactForm.vue';
  
  export default {
    name: 'ContactLayout',
    components: {
      ContactForm,
    }
  }
  </script>
  
  <style scoped>
  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    justify-content: center;
    min-height: 100vh;
    background-color: #BB4430;
  }
  
  .content-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 20px; 
    flex-wrap: wrap;
  }
  .contact-title {
    margin-bottom: 5px;
  }
  
  .contact-title h1 {
    color: #FFFFFF;
    font-size: 60px;
    text-transform: uppercase;
    letter-spacing: 2px;
  }

  .contact-email {
    color:#FFFFFF;
    font-size: 22px;
    margin-bottom: 20px;
    line-height: 1.5em;
  }
 
  @media (max-width: 768px) {
    .contact-title h1 {
    font-size: 40px;
  }
  .contact-email {
    font-size: 16px;
  }
    
  }
  
  </style>
  