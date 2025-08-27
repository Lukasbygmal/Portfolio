<template>
  <div class="layout-description-title">

    5th Year Student at UU<br> Master's Programme in Computer<br> and Infromation Engineering
  </div>
  <div class="layout-description">
    Welcome to my portfolio site!<br>In my free time I enjoy working on coding projects, which you can explore in the
    projects section. <br> I'm especially interested in computer architecture, network, security and ML.
    <br>The languages/technologies I feel most comfortable with are:
  </div>
  <div class="technologies">
    C/C++ Python C# Java SQL JavaScript/TypeScript Flutter Vue.js Flask React
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
  margin: 5px auto;
  background-color: transparent;
  max-width: 70%;
}

.technologies {
  margin-top: auto;
  font-size: 28px;
  font-weight: bold;
  background-color: transparent;
  color: #BB4430;
}

@media (max-width: 768px) {
  .layout-description-title {
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