<script setup>
import { ref, onMounted } from 'vue'
import navList from '../data/nav.json'

// Define reactive variables
const hamburger = ref(null)
const navMenu = ref(null)
const navItems = ref(navList)

// Define event handlers
const toggleMenu = () => {
  hamburger.value.classList.toggle('active')
  navMenu.value.classList.toggle('active')
}

const closeMenu = () => {
  hamburger.value.classList.remove('active')
  navMenu.value.classList.remove('active')
}

// Register event listeners
const registerEventListeners = () => {
  hamburger.value.addEventListener('click', toggleMenu)

  navItems.value.forEach((navItem) => {
    navItem.addEventListener('click', closeMenu)
  })
}

// Lifecycle hook
onMounted(() => {
  registerEventListeners()
})
</script>

<template>
  <header>
    <nav class="navBar">
      <img class="navLogo" src="../assets/logo.svg" alt="" />
      <ul class="navMenu" ref="navMenu">
        <li class="navItem" v-for="item in navItems" :key="item.id" ref="navItems">
          {{ item.label }}
        </li>
      </ul>
      <div class="hamburger" ref="hamburger">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </nav>
  </header>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: purple;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  height: 100vh;
}

header {
  background-color: white;
  width: 100%;
  height: 70px;
  z-index: 1;
  box-shadow: 0px 1px 4px hsl(0, 0%, 98%);
}

.navBar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 23px 120px;
}

.navMenu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  list-style-type: none;
  color: hsl(273, 4%, 51%);
}

.navItem {
  font-family: 'Karla', sans-serif;
  cursor: pointer;
  font-weight: 700;
}

.navItem:nth-child(4) {
  border: 1px solid hsl(270, 9%, 17%);
  padding: 10px 16px;
  color: hsl(270, 9%, 17%);
}

.hamburger {
  display: none;
  cursor: pointer;
}

.bar {
  width: 30px;
  height: 1px;
  display: block;
  margin: 5px 0;
  background-color: hsl(270, 9%, 17%);
  font-weight: 700;
}

.navLogo {
  font-size: 1.3rem;
  font-weight: bold;
  text-decoration: none;
  color: black;
  padding-left: 60px;
}

@media screen and (max-width: 950px) {
  .navBar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 23px 30px;
  }
  .hamburger {
    display: block;
    border: 1px solid hsl(270, 9%, 17%);
    padding: 5px;
  }
  .hamburger.active .bar:nth-child(2) {
    transition: all 0.5s;
    opacity: 0;
  }
  .hamburger.active .bar:nth-child(1) {
    transition: all 0.5s;
    transform: translateY(6.5px) rotate(45deg);
  }
  .hamburger.active .bar:nth-child(3) {
    transition: all 0.5s;
    transform: translateY(-6.5px) rotate(-45deg);
  }

  .navMenu {
    position: absolute;
    top: 70px;
    left: -100%;
    gap: 0;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    background-color: hsl(270, 9%, 17%);
    box-shadow: 0px 1px 4px hsl(270, 9%, 17%);
    color: hsl(0, 0%, 98%);
    width: 100%;
    height: 200px;
    text-align: center;
    transition: all 0.5s;
    padding: 10px;
  }

  .navItem:nth-child(4) {
    border: 1px solid hsl(0, 0%, 98%);
    color: hsl(0, 0%, 98%);
    width: 250px;
  }

  .navMenu.active {
    left: 0;
  }
}
</style>
