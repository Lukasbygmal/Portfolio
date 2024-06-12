<template>
    <div class="main-container">
      <div class="content-container">
        <LayoutDescription></LayoutDescription>
      </div>
    </div>
  </template>
  
  <script>
  
  import LayoutDescription from './LayoutDescription.vue';
  
  export default {
    name: 'ProjectLayout',
    components: {
      LayoutDescription,
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
    background-color: #1AD9E5;
  }
  
  .content-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 20px; 
    flex-wrap: wrap;
  }
  
  
  @media (max-width: 768px) {
    
  
  }
  
  </style>
  