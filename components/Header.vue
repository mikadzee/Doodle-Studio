<template>
  <header class="header font-text">
    <div class="burger-menu" v-if="!checkBurgerMenu" @click="checkBurgerMenu = !checkBurgerMenu">
      <div class="icon-menu">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
      </div>
    </div>
    
    <nav class="nav" v-if="checkBurgerMenu">
      <ul>
        <label class="logo-text">Doodle</label>
        <li><a href="#about">О нас</a></li>
        <li><a href="#services" class="services">Услуги</a></li>
        <li><a href="#project">Проекты</a></li>
        <li><a href="#blog">Блог</a></li>
      </ul>

      <div class="close" @click="checkBurgerMenu = !checkBurgerMenu">
        <div class="icon-close">
          <div class="line-close"></div>
        </div>
      </div>
    </nav>
  </header>
</template>

<style lang="less" scoped>
.header {
  position: fixed;
  top: 0px;
  right: 0px;
  z-index: 100;

  & .burger-menu {
    margin-top: 40px;
    margin-right: 70px;
    
    & .icon-menu {
      position: relative;
      width: 50px;
      height: 50px;
      cursor: pointer;
      display: flex;
      gap: 5px;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      border: 1px solid #ffffff;
      border-radius: 50px;

      & .line {
        width: 20px;
        height: 3px;
        background-color: #fff;
        transition: all 0.5s;
      }
    }
  }

  & .nav {
    padding: 80px 90px;
    position: absolute;
    right: 110%;
    top: 0px;
    background: #fff;
    border-radius: 50px;
    border: 1px solid #000;
    font-size: 24px;
    height: 100vh;
    
    & ul {
      display: flex;
      flex-direction: column;
      gap: 40px;
      text-align: center;

      & > label {
        color: #000;
        font-size: 40px;
      }

      & > li {
        & > a {
          color: #000;
          font-size: 24px;
        }
      }
    }

    & .close {
      margin: 30px auto;
      border: 1px solid #000;
      width: 40px;
      opacity: 80%;
      height: 40px;
      border-radius: 50px;
      cursor: pointer;
      position: relative;

      & .icon-close {
        position: absolute;
        top: 47%;
        left: 27%;
        transform: translate(-50%, -50%);
        animation: close-animation 4s infinite;

        & .line-close {
          width: 20px;
          height: 3px;
          transform: rotate(-50deg);
          background-color: #000;
          transition: all 0.5s;

          &::after {
            content: "";
            position: absolute;
            width: 20px;
            height: 3px;
            transform: rotate(90deg);
            background-color: #000;
            transition: all 0.5s;
          }
        }
      }
    }
  }

  & .contacts {
    margin-right: 50px;
  }
}

@keyframes close-animation {
  0% {
    transform: rotate(0deg);
  }
  40% {
    transform: rotate(-5deg);
  }
  60% {
    transform: rotate(5deg);
  }
  80% {
    transform: rotate(-5deg);
  }
  100% {
    transform: rotate(0deg);
    
  }
}
</style>


<script setup>
  let checkBurgerMenu = ref(false)
</script>