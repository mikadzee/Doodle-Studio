<template>
  <footer class="footer font-text">
    <div class="info">
      <div class="contacts">
        <div class="logo logo-text"><h2>Doodle</h2></div>
        <div class="icons">
          <a href=""><img src="@/assets/images/icon-telegram.png" alt=""></a>
          <a href=""><img src="@/assets/images/icon-discord.png" alt=""></a>
        </div>
        <p class="description">© Copyright DOODLE 2024</p>
      </div>

      <nav class="nav">
        <ul>
          <li><a href="#about">О нас</a></li>
          <li><a href="#services">Услуги</a></li>
          <li><a href="#project">Проекты</a></li>
          <li><a href="#blog">Блог</a></li>
        </ul>
      </nav>

      <div class="connect">
        <div class="email">
          <img src="../assets/images/icon-email.png" alt="">
          <p class="logo-text">doodleteam@mail.ru</p>
        </div>

        <div class="services">
          <div><p>Наши услуги</p></div>
          <div><p>Обсудить проект</p></div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="less" scoped>
  .footer {
    padding: 50px 0px;
    color: #fff;
    text-transform: uppercase;
    position: relative;
    
    & .info {
      display: flex;
      gap: 60px;
      justify-content: center;
      color: #000;

      & .contacts {

        & .logo {
          margin-bottom: 10px;
          
          & > h2 {
            font-size: 36px;
            font-weight: 400;

          }
        }

        & .icons {
          margin-bottom: 40px;
          & > a {
            margin-right: 20px;
          }
        }

        & .description {
          font-size: 14px;
        }
      }

      & .nav {

        & > ul {
        
          & > li {
            margin-top: 30px;
            & > a {
              color: #000;
              font-weight: 600;
            }
          }
          & > li:first-child {
            margin-top: 0px;
            & > a {
              color: #000;
              
            }
          }
        }
      }
      & .connect {
        padding: 20px 40px;
        border: 3px solid #000;
        border-radius: 20px;

        & .email {
          margin: 10px 0px;
          display: flex;
          justify-content: center;
          align-items: center;
          gap: 5px;
          
          & > p {
            font-size: 32px;
            font-weight: 400;
          }
          & > img {
            width: 20px;
          }
        }

        & .services {
          display: flex;
          justify-content: space-around;
          
          & > div {
            padding: 10px 20px;
            border: 3px solid #000;
            border-radius: 30px;
            font-size: 16px;
            font-weight: 600;

          }
        }
      }
    }
  }
</style>