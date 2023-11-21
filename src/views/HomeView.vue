<script setup>
import { ref } from 'vue'
import snappyProcess from '../assets/icon-snappy-process.svg'
import peopleFirst from '../assets/icon-people-first.svg'
import affordablePrices from '../assets/icon-affordable-prices.svg'
import Footer from '../components/Footer-vue.vue'

const cards = ref([
  {
    id: 1,
    img: snappyProcess,
    title: 'Snappy Process',
    text: 'Our application process can be completed in minutes, not hours. Don’t get stuck filling in tedious forms.'
  },
  {
    id: 2,
    img: affordablePrices,
    title: 'Affordable Prices',
    text: 'We don’t want you worrying about high monthly costs. Our prices may be low, but we still offer the best coverage possible.'
  },
  {
    id: 3,
    img: peopleFirst,
    title: 'People First',
    text: 'Our plans aren’t full of conditions and clauses to prevent payouts. We make sure you’re covered when you need it.'
  }
])
</script>

<template>
  <main class="home-page">
    <!-- <img class="pattern-1" src="../assets/bg-pattern-intro-right-desktop.svg" alt="" /> -->
    <section class="home">
      <div class="home-text">
        <h3>Humanizing your insurance.</h3>
        <p>
          Get your life insurance coverage easier and faster. We blend our expertise and technology
          to help you find the plan that’s right for you. Ensure you and your loved ones are
          protected.
        </p>
        <button>VIEW PLANS</button>
      </div>
      <!-- <span>
      <img src="../assets/bg-pattern-intro-right-desktop.svg" alt="" />
      </span> -->
      <div class="home-image">
        <picture>
          <!-- For smaller screens (mobile) -->
          <source media="(max-width: 600px)" srcset="../assets/image-intro-mobile.jpg" />

          <!-- For larger screens (desktop) -->
          <source media="(min-width: 768px)" srcset="../assets/image-intro-desktop.jpg" />

          <!-- Default image in case the browser doesn't support <picture> -->
          <img src="../assets/image-intro-mobile.jpg" alt="Description of the image" />
        </picture>
        <!-- <img src="../assets/image-intro-desktop.jpg" alt="" /> -->
      </div>
    </section>
    <img class="pattern-2" src="../assets/bg-pattern-intro-left-desktop.svg" alt="" />

    <section class="page-two">
      <h2>We're different</h2>
      <div class="card-area">
        <div class="card" v-for="card in cards" :key="card.id">
          <img :src="card.img" alt="" />
          <h3>{{ card.title }}</h3>
          <p>{{ card.text }}</p>
        </div>
      </div>
    </section>
    <section>
      <div class="rect">
        <img class="pattern-3" src="../assets/bg-pattern-how-we-work-desktop.svg" alt="" />
        <div class="rect-content">
          <div>
            <h2>Find out more about how we work</h2>
          </div>
          <div>
            <button>HOW WE WORK</button>
          </div>
        </div>
      </div>
    </section>
    <footer>
      <Footer />
    </footer>
  </main>
</template>

<style scoped>
.home-page {
  background-color: hsl(256, 26%, 20%);
  height: 80vh;
}

.home {
  display: flex;
  justify-content: space-between;
  gap: 170px;
  align-items: flex-start;
  padding: 80px 180px;
  border: 1px solid white;
}

.home-text::before {
  content: '';
  position: absolute;
  width: 250px;
  height: 1px;
  background-color: hsl(0, 0%, 98%);
}

.home-text h3 {
  color: white;
  /* font-family: 'Karla', serif; */
  margin-top: 60px;
  font-size: 100px;
}

.home-text p {
  color: hsl(0, 0%, 98%);
  font-family: 'Karla', sans-serif;
  font-size: 22px;
  line-height: 1.3;
  margin-top: 20px;
}

.home-text button {
  margin-top: 30px;
  border: 1px solid hsl(0, 0%, 98%);
  outline: none;
  background-color: transparent;
  color: hsl(0, 0%, 98%);
  padding: 14px;
  font-size: 15px;
  width: 180px;
  cursor: pointer;
}

.pattern-1 {
  position: absolute;
  right: 0px;
  top: -12px;
  z-index: 1;
}

.pattern-2 {
  position: absolute;
  bottom: -280px;
}

.page-two {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
  gap: 100px;
  margin: 100px 170px;
}

.page-two::before {
  content: '';
  position: absolute;
  width: 250px;
  height: 1px;
  background-color: hsl(273, 4%, 51%);
}

.page-two h2 {
  margin: 70px 0 0;
  font-size: 70px;
  color: hsl(256, 26%, 20%);
}

.card-area {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}

.card {
  width: auto;
}

.card img,
h3,
p {
  margin-bottom: 30px;
}

.card h3 {
  font-size: 40px;
  color: hsl(256, 26%, 20%);
}

.card p {
  font-size: 25px;
  color: hsl(273, 4%, 51%);
}

.rect {
  margin: 0 170px;
  margin-bottom: 100px;
  border: 1px solid black;
  background-color: hsl(256, 26%, 20%);
}

.rect img {
  position: absolute;
  right: 170px;
  z-index: 0;
}

.rect-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 50px;
  margin: 50px 150px;
}

.rect-content h2 {
  font-size: 60px;
  color: hsl(0, 0%, 98%);
  padding-right: 450px;
}

.rect-content button {
  border: 1px solid hsl(0, 0%, 98%);
  padding: 16px;
  outline: none;
  background-color: transparent;
  color: hsl(0, 0%, 98%);
  width: 150px;
  font-size: 14px;
}

@media screen and (max-width: 600px) {
  .home-page {
    background-color: hsl(256, 26%, 20%);
    height: 650px;
    width: 100%;
    padding-bottom: 50px;
  }

  .home {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 0;
    align-items: center;
    padding: 0px 0;
  }

  .home-text::before {
    content: '';
    width: 0px;
    height: 0px;
  }
  .home-text {
    text-align: center;
    padding: 0 30px;
    /* margin: 60px 0; */
  }

  /* .home-text button {
    margin-bottom: 60px;
  } */

  .home-text > h3 {
    font-size: 80px;
    /* margin-top: 60px; */
  }

  .home-image img {
    width: 600px;
    height: 100%;
    object-fit: cover;
  }

  .page-two {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    gap: 80px;
    margin: 100px 80px;
  }

  .page-two::before {
    content: '';
    position: absolute;
    width: 250px;
    height: 1px;
    background-color: hsl(273, 4%, 51%);
  }

  .page-two h2 {
    text-align: center;
    font-size: 60px;
  }
  .card-area {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
    text-align: center;
  }

  .rect {
    margin: 0 30px;
    margin-bottom: 100px;
    border: 1px solid black;
    background-color: hsl(256, 26%, 20%);
  }

  .rect img {
    position: absolute;
    right: 170px;
    z-index: 0;
  }

  .rect-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 50px;
    margin: 100px 10px;
    text-align: center;
  }

  .rect-content h2 {
    font-size: 70px;
    color: hsl(0, 0%, 98%);
    padding-right: 10px;
  }
}
</style>
