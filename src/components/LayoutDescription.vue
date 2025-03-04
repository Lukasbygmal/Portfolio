<template>
    <div class="layout-description-title">
      
      4th Year Student at UU<br> Master's Programme in Computer<br> and Infromation Engineering
    </div>
    <div class= "layout-description">
      Welcome to my portfolio site! I'm currently looking for a part-time or summer job. During my education I have worked with a wide variety of languages/technologies and 
      developed strong communication skills and the ability to collaborate effectively to achieve shared goals. In my free time I enjoy working on coding projects, which you can explore in the projects section.
      I look forward to new challenges where I can contribute with my knowledge and initiative to develop solutions to real problems! <br>
      The languages/technologies I feel most comfortable with are:
    </div>
    <div class="technologies">
      Python C/C++ Java Haskell SQL JavaScript/TypeScript Flutter Vue.js React 
    </div>
  </template>
  
  <script>
  export default {
    name: 'LayoutDescription'
  }
  </script>
  
  <style scoped>
  .layout-description-title {
    font-size: 48px;
    font-weight: bold;
    color: black;
    margin: 22px;
    background-color: transparent;
  }
  .layout-description {
    font-size: 24px;
    color: black;
    margin: 5px 80px;
    background-color: transparent
  }
  .technologies {
    margin-top: auto;
    font-size: 28px;
    font-weight: bold;
    background-color: transparent;
    color: #BB4430;
  }
  
  @media (max-width: 768px) {
  .layout-description-title{
    font-size: 24px;
    margin: 4px;
  }
  .layout-description {
    font-size: 18px;
    color: black;
    margin: 15px;
  }
  .technologies {
    margin-top: auto;
    font-size: 1.2em;
    font-weight: bold;
    background-color: transparent;
    color: #BB4430;
  }
}
  </style>
  