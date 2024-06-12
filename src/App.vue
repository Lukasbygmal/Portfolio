<template>
  <div id="app">
    <header>
      <button class="title-button" @click="handleButtonClick('mainLayout')">Lukas BM</button>
      <div class="menu-toggle" @click="toggleMenu">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
      </div>
      <div class="button-group" :class="{ 'show-menu': isMenuOpen }">
        <button @click="handleButtonClick('projectLayout')">Projects</button>
        <button @click="handleButtonClick('contactLayout')">Contact</button>
        <a href="/LukasBygdellMalmstig-CV.pdf" target="_blank" @click="closeMenu">
          <button>CV</button>
        </a>
      </div>
    </header>
    <div class="content">
      <MainLayout id="mainLayout" />
      <ProjectLayout id="projectLayout" />
      <ContactLayout id="contactLayout" />
    </div>
  </div>
</template>

<script>
import MainLayout from './components/MainLayout.vue'
import ProjectLayout from './components/ProjectLayout.vue'
import ContactLayout from './components/ContactLayout.vue'

export default {
  name: 'App',
  components: {
    MainLayout,
    ProjectLayout,
    ContactLayout
  },
  data() {
  return {
    isMenuOpen: false
  };
},
  methods: {
    handleButtonClick(id) {
      this.scrollTo(id);
      this.closeMenu();
    },
    scrollTo(id) {
      const element = document.getElementById(id);
      if (element) {
        element.scrollIntoView({ behavior: "smooth", block: "start" });
      }
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
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
  color: black;
  margin-top: 0;

  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-color: transparent;

  min-height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
}

header {
  position: fixed; /* Set header to fixed position */
  top: 0; /* Align header to the top of the viewport */
  left: 0; /* Align header to the left of the viewport */
  right: 0; /* Align header to the right of the viewport */
  background-color: #231F20;
  padding: 10px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  z-index: 1000; /* Ensure header stays above other content */
}

.title-button {
  font-size: 60px;
  font-weight: bold;
  background-color: transparent;
  color: white;
  cursor: pointer;
  border: none;
  outline: none;
  padding: 0;
  margin: 5px;
}

.title-button:hover {
  color: #808080;
}

.button-group {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  margin: 5px;
}

.button-group button {
  border: none;
  background-color: transparent;
  color: white;
  cursor: pointer;
  font-size: 34px;
  padding: 10px 20px;
  margin: 5px;
}

.button-group button:hover {
  color: #808080;
}

.content {
  flex: 1;
  display: flex;
  flex-direction: column; 
  overflow-y: auto;
}

.MainLayout,
.ProjectLayout,
.ContactLayout {
  flex: 1;
  min-height: 100vh;
  min-width: 0;
}
.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  height: 24px;
  width: 30px;
  cursor: pointer;
  padding: 10px;
}

.menu-toggle .line {
  width: 100%;
  height: 2px;
  background-color: white;
}

@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .button-group {
    display: none;
    flex-direction: column;
    background-color: rgba(51, 51, 51, 0.8);
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
  }

  .button-group.show-menu {
    display: flex;
  }

  .title-button {
    font-size: 36px;
  }

  .button-group button {
    width: 100%;
    padding: 10px 20px;
  }
}
</style>
