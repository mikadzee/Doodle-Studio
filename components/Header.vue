<template>
  <header class="header font-text">
    <div class="logo">
      <h2 class="logo-text">Doodle</h2>
    </div>

    <nav class="nav">
      <ul>
        <li><a href="#about">О нас</a></li>
        <li><a href="#services" class="services">Услуги</a></li>
        <li><a href="#project">Проекты</a></li>
        <li><a href="#blog">Блог</a></li>
      </ul>
    </nav>

    <div class="contacts">
      <p><a href="#contacts">Контакты</a></p>
    </div>
  </header>
</template>

<style lang="less" scoped>
  .header {
    padding: 50px 0px;
    background-color: transparent;
    z-index: 10; 
    display: flex;
    align-items: center;
    color: #fff;
    text-transform: uppercase;
    width: 100%;
    position: absolute; 
    top: 0;
    left: 0;
    
    & .logo {
      margin-right: auto;
      margin-left: 50px;

      & .logo-text {
        font-size: 36px;
      }
    }

    & .nav {
      margin-right: auto;

      & > ul {
        display: flex;
        align-items: center;
        gap: 30px;

        & > li {
          font-size: 16px;

          & > a {
            font-size: 14px;
            color: #fff;
          }
        }
        & .services {
          margin-right: 300px;
        }
      }
    }

    & .contacts {
      margin-right: 50px;
    }
  }
</style>