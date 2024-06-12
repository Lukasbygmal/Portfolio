<template>
  <div id="app">
    <header>
      <button class="title-button" @click="handleTitleClick">Lukas BM</button>
      <div class="button-group">
        <button @click="handleButtonClick('Projects')">Projects</button>
        <button @click="handleButtonClick('Contact')">Contact</button>
        <a href="/LukasBygdellMalmstig-CV.pdf" target="_blank">
          <button>CV</button>
        </a>
      </div>
    </header>
    <MainLayout />
  </div>
</template>

<script>
import MainLayout from './components/MainLayout.vue'

export default {
  name: 'App',
  components: {
    MainLayout
  },
  methods: {
    handleButtonClick(page) {
      console.log(`${page} button clicked`);
      // Add your navigation logic here
    },
    handleTitleClick() {
      console.log('Title button clicked');
      // Add your navigation logic here
    }
  }
}
</script>

<style>
html, body {
  margin: 0;
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 0;

  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  min-height: 100vh;
  width: 100%;
}

header {
  background-color: #333;
  padding: 10px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}

.title-button {
  font-size: 60px;
  font-weight: bold;
  background-color: transparent;
  color: gold;
  cursor: pointer;
  border: none;
  outline: none;
  padding: 0;
  margin: 5px;
}

.title-button:hover {
  color: goldenrod;
}

.button-group {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  margin: 5px;
}

.button-group button {
  border: none;
  background-color: #333;
  color: white;
  cursor: pointer;
  font-size: 34px;
  padding: 10px 20px;
  margin: 5px;
}

.button-group button:hover {
  color: goldenrod;
}

@media (max-width: 768px) {
  .title-button {
    font-size: 36px;
  }

  .button-group button {
    font-size: 24px;
  }
}
</style>
