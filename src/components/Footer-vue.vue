<template>
  <div class="footer">
    <img src="../assets/bg-pattern-footer-desktop.svg" alt="" />
    <div class="footer-content">
      <div class="logo">
        <img src="../assets/logo.svg" alt="" />
      </div>
      <div class="socials">
        <img src="../assets/icon-facebook.svg" alt="" />
        <img src="../assets/icon-twitter.svg" alt="" />
        <img src="../assets/icon-pinterest.svg" alt="" />
        <img src="../assets/icon-instagram.svg" alt="" />
      </div>
    </div>
    <hr />
    <div class="footer-details">
      <div class="our-company">
        <h2>OUR COMPANY</h2>
        <div class="our-company-details">
          <p>HOW WE WORK</p>
          <p>WHY INSURE?</p>
          <p>CHECK PRICE</p>
          <p>REVIEWS</p>
        </div>
      </div>
      <div class="help-me">
        <h2>HELP ME</h2>
        <div class="help-me-details">
          <p>FAQ</p>
          <p>TERMS OF USE</p>
          <p>PRIVACY POLICY</p>
          <p>COOKIES</p>
        </div>
      </div>
      <div class="contact">
        <h2>CONTACT</h2>
        <div class="contact-details">
          <p>SALES</p>
          <p>SUPPORT</p>
          <p>LIVE CHAT</p>
        </div>
      </div>
      <div class="others">
        <h2>OTHERS</h2>
        <div class="others-details">
          <p>CAREERS</p>
          <p>PRESS</p>
          <p>LICENSES</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.footer {
  background-color: hsl(0, 0%, 98%);
  width: 100%;
  height: 450px;
  padding: 100px 250px;
}

.footer > img {
  position: absolute;
  top: 261%;
  left: 0px;
}

.footer-content {
  display: flex;
  justify-content: space-between;
}

.logo img {
  width: 100%;
  color: hsl(256, 26%, 20%);
}

hr {
  margin: 50px 0;
}
.footer-content .socials {
  display: flex;
  gap: 14px;
  cursor: pointer;
}

.footer-content .socials img {
  width: 70%;
  height: 100%;
}

.footer-details {
  display: flex;
  align-items: flex-start;
  gap: 100px;
}

.footer-details h2 {
  font-family: 'Karla', sans-serif;
  margin-bottom: 30px;
  color: hsl(216, 30%, 68%);
}

.footer-details p {
  color: hsl(256, 26%, 20%);
  font-size: 16px;
  margin-bottom: 15px;
  font-family: 'Karla', sans-serif;
}
@media screen and (max-width: 600px) {
  .footer {
    background-color: hsl(0, 0%, 98%);
    width: 100%;
    height: 930px;
    padding: 100px 250px;
  }
  .footer-content {
    display: flex;
    flex-direction: column;
    text-align: center;
  }
  /* 
  hr {
    width: 300px;
    text-align: center;
  } */
  .footer-details {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 30px;
    /* text-align: center; */
  }

  .footer-details h2 {
    font-size: 14px;
  }

  .footer-details p {
    font-size: 12px;
  }
}
</style>
