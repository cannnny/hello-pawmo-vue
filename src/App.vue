<script setup>
import { ref } from "vue";

const classToggle = () => {
  const active = ref(true);
  active.value = !active.value;
  return active, classToggle;
};
</script>

<template>
  <header>
    <div className="header-inner">
      <div className="header-left">
        <p>Pawmo</p>
      </div>
      <div className="header-right"></div>
    </div>
  </header>

  <main>
    <div className="main-img">
      <img :src="active ? '/pawmo1.png' : '/pawmo2.png'" alt="" />
    </div>
    <div className="message-wrapper">
      <div className="message">
        <p onClick="{classToggle}">Hi!</p>
        <p onClick="{classToggle}">Hello Pawmo!</p>
      </div>
    </div>
  </main>
  <footer>
    <div className="footer-inner">
      <div className="footer-left"></div>
      <div className="footer-right">
        <div className="msgbox"></div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans:wght@500&display=swap");

* {
  max-width: 768px;
  font-family: "Noto Sans", sans-serif;
}

header {
  display: flex;
  align-items: flex-end;
  width: 100%;
  height: 80px;
  background-color: #d8d8d8;
}

.header-inner {
  display: flex;
  align-items: center;
  width: 100%;
  height: 60px;
}

.header-left {
  display: flex;
  justify-content: center;
  margin-right: auto;
}

.menu-icons {
  margin-left: 5px;
}

p {
  margin-left: 10px;
  color: #4b4b4b;
  font-size: 23px;
}

.header-right {
  display: flex;
  justify-content: flex-end;
  margin-right: 10px;
}

.menu-icons {
  margin: 7px;
}

main {
  background-color: #ffffff;
}

.main-img {
  margin: 40px 0;
}

.message-wrapper {
  display: flex;
  align-items: center;
  opacity: 0.8;
  height: 250px;
  background-color: #e7e7e7;
}

.message {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  width: 100%;
}
.message p {
  display: inline-block;
  position: relative;
  max-width: 250px;
  margin: 20px;
  padding: 8px 10px;
  border-radius: 14px;
  box-shadow: 3px 5px 0 0 #25b33f;
  background-color: #30e852;
  font-size: 18px;
}

.message p:after {
  position: absolute;
  top: 3px;
  right: -19px;
  transform: rotate(-35deg);
  border: 8px solid transparent;
  border-left: 18px solid #30e852;
  content: "";

  -webkit-transform: rotate(-35deg);
}

.message p:active {
  position: relative;
  top: 3px;
  left: 5px;
  box-shadow: none;
  background-color: #25b33f;
}

.message p:active:after {
  position: absolute;
  top: 3px;
  right: -19px;
  transform: rotate(-35deg);
  border: 8px solid transparent;
  border-left: 18px solid #25b33f;
  content: "";

  -webkit-transform: rotate(-35deg);
}

footer {
  display: flex;
  align-items: center;
  width: 100%;
  height: 75px;
  background-color: #d8d8d8;
}

.footer-inner {
  display: flex;
  align-items: center;
  width: 100%;
}

.footer-left {
  display: flex;
  justify-content: center;
  margin-right: auto;
  margin-left: 3px;
}

.menu-icons {
  margin: 7px;
}

.footer-right {
  display: flex;
  justify-content: flex-end;
  margin-right: 5px;
}

.msgbox {
  position: relative;
  width: 185px;
  height: 50px;
  border-radius: 9999px;
  background-color: #b5b5b5;
}

.smile {
  position: absolute;
  right: 0;
}

.menu-icons {
  margin: 7px;
}
</style>
