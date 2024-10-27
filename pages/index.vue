<template>
  <main>
    <section class="main font-text" >
      <div class="about-head">
        <h1 class="logo-text">
          креатив студия для<br />мечтателей &<br />исполнителей
        </h1>

        <a href="#"><button class="discuss-project">Обсудить проект</button></a>

        <div class="contacts-block">
          <div class="contacts-icons" :style="{'width': checkContact ? '200px' : '0%'}">
            <img src="@/images/icon-telegram.png" alt="">
            <img src="@/images/icon-discord.png" alt="">
          </div>

          <div class="icon" @click="checkContact = !checkContact" >
            <div class="arrow" :style="{'transform': checkContact ? 'rotate(90deg)' : 'rotate(0deg)'}">
              <div class="wand"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="about-body">
        <div class="images">
          <img class="logo" src="@/images/main-logo.png" alt="">
          <img class="person" src="@/images/main-person.png" alt="">
        </div>

        <div class="about-block">
          <p class="sub-title">О нас</p>
          <h2 class="about-doodle-text logo-text">Мы - студия. помогаем своим клиентам раскрыть свой потенциал с помощью сочетания дизайна, маркетинга и стратегии. </h2>
          <p class="about-text">
            Как креативщики с более чем 5-летним опытом, мы тесно сотрудничаем со своими клиентами, чтобы предоставить широкий спектр творческих решений. Помимо того, что мы делаем великие вещи для своих клиентов, мы стремимся использовать свои навыки для достижения великой цели. Мы также посвящаем время изучению цифрового искусства, экспериментируя с типографикой, каллиграфией, движением, интерактивным 3D и генеративным искусственным интеллектом. Также мы представляем спектр разработки ваших сайтов, для вашего удобства
          </p>
          
          <a href="#services"><button class="our-services">Наши услуги</button></a>
        </div>

      </div>
      <div class="footer-image">
        <img src="@/images/main-background-footer.png" alt="">
      </div>
    </section>

    <section ref="portfolioSection" class="portfolio font-text">
      <h2 ref="titleRef" class="title logo-text">Наши проекты</h2>
      <div class="list-project">
        <IntersectionObserver  v-for="project in dataPortfolio">
          <div ref="projectRef" class="project" :style="{'left': positionCalculation()}">
            <div class="image">
              <img src="@/images/project-image.png" alt="">
            </div>
            <p>{{ project.name }}</p>
          </div>
        </IntersectionObserver>
      </div>

      <div class="footer-portfolio">
        <img src="@/images/portfolio-footer.png" alt="">
      </div>
    </section>

    <section class="work font-text">
      <img class="background" src="@/images/work-bg.png" />

      <h2 class="title-work logo-text">Как мы работаем?</h2>

      <div class="info-cards">
        <div class="cards">

          <div class="card">
            <h3 class="title-card logo-text">1) Знакомство с вашей компанией</h3>
            <p class="description">Проект начинается с семинара, чтобы согласовать вашу команду и наших экспертов, понять ваш бизнес, а также установить целии ожидания.</p>
          </div>
          
          <div class="card">
            <h3 class="title-card logo-text">2) стратегия и разработка</h3>
            <p class="description">Проект начинается с семинара, чтобы согласовать вашу команду и наших экспертов, понять ваш бизнес, а также установить целии ожидания.</p>
          </div>
          
          <div class="card">
            <h3 class="title-card logo-text">3) Результаты</h3>
            <p class="description">Мы построим пошаговую стратегию, которая сочетает в себе бесплатный и платный трафик, пользовательский опыт, анализ данных и тактики маркетинга роста для достижения ваших целей.</p>
          </div>
        </div>
        <button class="duscuss-project font-text">Обсудить проект</button>
      </div>


      <div class="work-footer">
        <img src="@/images/work-footer.png" alt="">
      </div>
    </section>


    <section class="contacts font-text">
      <div class="contacts-info">
        <div class="person">
          <img src="@/images/contacts-person.png" alt="">
        </div>

        <div class="contacts-text">
          <h2 class="title logo-text">Мы в соц сетях</h2>

          <div class="social">
            <h3 class="subtitle-social">Добро пожаловать</h3>
            <h2 class="title-social logo-text">Пространство, где креативность встречается с вдохновением!</h2>
            
            <p class="description">Здесь вы найдете статьи о последних трендах, советы по улучшению вашего пространства, а также за кулисами нашей работы. <br><br><br>Мы верим, что дизайн — это не только эстетика, но и способулучшить жизнь людей.</p>
            <a href="https://discord.gg/Y7jj7dm2S7"><button class="join">Присоеденется</button></a>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped lang="less">
  .main {
    padding-left: 70px;
    padding-right: 70px;
    padding-top: 240px;
    background-image: url("@/images/main-background.png");
    background-position: center;
    background-repeat: no-repeat;
    object-fit: cover;
    position: relative;
    background-size: cover;
    
    & .about-head {
      margin-bottom: 300px;
      position: relative;
      top: -50px;

      & h1 {
        text-align: right;
        font-size: 64px;
        color: #fff;
      }

      & .discuss-project {
        margin-top: 20px;
        position: absolute;
        width: 260px;
        height: 50px;
        border-radius: 100px;
        border: inset 3px solid #000;
        background: #FFDF00;
        font-size: 14px;
        text-transform: uppercase;
        right: 0px;
        cursor: pointer;
        font-weight: 550;
      }
      & .contacts-block {
        position: relative;

        & .icon {
          position: relative;
          cursor: pointer;
          & .arrow {
            border: 1px solid #fff;
            transition: all 0.5s;
            border-radius: 100%;
            width: 50px;
            position: absolute;
            height: 50px;
            right: 0px;
            bottom: -150px;
            // display: flex;
            // justify-content: center;
            // align-items: center;
            & .wand {
              width: 2px;
              position: absolute;
              left: 50%;
              top: 50%;
              transform: translate(-50%, -50%);
              height: 25px;
              background: #fff;
    
              &::before {
                content: "";
                position: absolute;
                bottom: -2px;
                right: 4px;
                border-radius: 50px;
                background: #fff;
                width: 1.9px;
                height: 13px;
                transform: rotate(-40deg);
              }
              &::after {
                content: "";
                position: absolute;
                bottom: -2px;
                left: 4px;
                border-radius: 50px;
                background: #fff;
                width: 1.9px;
                height: 13px;
                transform: rotate(40deg);
              }
            }
          }
        }

        & .contacts-icons {
          transition: all 0.5s;
          display: flex;
          justify-content: space-between;
          overflow: hidden;
          height: 100px;
          position: absolute;
          right: 52px;
          top: 100px;

          & > img:last-child {
            margin-right: 10px;
            width: 50px;
            height: 50px;
          }
          & > img:first-child {
            margin-left: 80px;
            width: 50px;
            height: 50px;
          }
        }
      }

      & .active {
        animation: arrow 1s infinite;
      }
      & .not-active {
        background-color: red;
      }
    }

    & .about-body {
      z-index: 10;
      text-transform: uppercase;
      position: relative;

      & .images {
        z-index: -1;
        top: -130%;
        left: 20%;
        position: absolute;
        width: 500px;

        & .logo {
          z-index: -2;
          position: absolute;
          left: -43%;
          top: -5%;
        }

        & .person {
          z-index: -4;
        }
      }

      & .about-block {
        padding: 80px 150px;
        background: #fff;
        border-radius: 50px;
        color: #000;

        & .sub-title {
          margin-bottom: 40px;
          font-size: 16px;
          opacity: 60%;
        }
  
        & .about-doodle-text {
          font-size: 34px;
        }

        & .about-text {
          margin-top: 10px;
          text-transform: none;
          font-size: 16px;
        }
  
        & .our-services {
          margin-top: 40px;
          width: 260px;
          height: 50px;
          font-size: 14px;
          background: #FFDF00;
          border: inset 3px solid #000;
          border-radius: 100px;
          cursor: pointer;
          font-weight: 550;
        }
      }
    }

    .footer-image {
      position: absolute;
      left: 0px;
      & > img {
        width: 100%;

      }
    }
  }

  .portfolio {
    padding-top: 100px;
    background-image: url("@/images/portfolio-bg.png");
    background-position: center;
    background-repeat: no-repeat;
    object-fit: cover;
    position: relative;
    z-index: -5;

    & .title {
      padding-top: 20px;
      text-align: center;
      position: sticky;
      top: 10px;
      left: 20%;
      font-size: 60px;
      color: #FFFFFF;
      opacity: 50%;
      text-transform: uppercase;
    }

    & .list-project {
      overflow: hidden;

      & .project {
        margin: 80px 0px;
        position: relative;
        left: 0px;
        cursor: pointer;
        & .image {
          
        }
        
        & p {
          color: #fff;
          text-transform: uppercase;
          font-size: 24px;
        }

        &:hover {
          opacity: 50%;
        }
      }

    }

    & .footer-portfolio {
      position: absolute;
      left: 0px;
      bottom: -6%;
      & > img {
        width: 100%;

      }
    }
  }

  .work { 
    position: relative;
    background: #292929;
    height: 200vh;
    z-index: -10;

    & .background {
      position: absolute;
      background-position: center;
      background-repeat: no-repeat;
      width: 100%;
      z-index: -50;
    }

    & .title-work {
      text-align: center;
      padding-top: 65px;
      font-size: 60px;
      z-index: -1;
      position: sticky;
      top: 10px;
      left: 20%;
      opacity: 50%;
      color: #fff;
    }

    & .info-cards {
      position: relative;
      & .cards {
        margin: 27% auto;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        gap: 20px;
        
        & .card {
          padding: 100px 50px;
          background: #fff;
          width: 380px;
          height: 150px;
          border-radius: 50px;
  
          & .title-card {
            margin-bottom: 30px;
            font-size: 28px;
          }
        }
      }

      & .duscuss-project {
        position: absolute;
        bottom: -30%;
        margin-left: 20px;
        border-radius: 100px;
        text-transform: uppercase;
        font-size: 14px;
        font-weight: bold;
        border: 2px solid #000;
        width: 260px;
        height: 50px;
        background: #FFDF00;
      }
    }

    & .work-footer {
      position: absolute;
      bottom: 0px;
      & > img {
        width: 100%;
      }
    }
  }

  .contacts {
    background: #000;
    background-image: url("@/images/contacts-bg.png");
    background-repeat: no-repeat;
    object-fit: cover;
    z-index: -4;

    & .contacts-info {
      padding: 100px 0px;
      position: relative;
      height: 140vh;
      display: flex;
      justify-content: space-around;
      
      & .person {
        z-index: 5;

        & > img {
          position: absolute;
          left: 1%;
          bottom: 0px;
          width: 700px;
        }
      }
      
      & .contacts-text {
        position: absolute;
        right: 0px;
        top: 25%;

        & .title {
          margin-right: 30px;
          text-transform: uppercase;
          text-align: right;
          color: #fff;
          font-size: 64px;
          font-weight: 500;
        }
        
        & .social {
          margin-right: 40px;
          margin-top: 30px;
          padding: 0px 90px;
          border-radius: 30px;
          background: #fff;
          width: 650px;

          & .title-social {
            font-size: 36px;
            text-transform: uppercase;
          }
          
          & .subtitle-social {
            padding: 40px 0px;
            font-size: 16px;
            font-weight: 400;
            text-transform: uppercase;
          }
          
          & .description {
            margin-top: 40px;
            font-size: 16px;
          }

          & .join {
            margin: 40px 0px;
            border-radius: 100px;
            text-transform: uppercase;
            font-size: 14px;
            font-weight: bold;
            border: 2px solid #000;
            width: 260px;
            height: 50px;
            background: #FFDF00;
          }
        }


      }
    }

  }

  @keyframes arrow {
    0% {
      transform: rotate(0deg);
    }
    100% {
      opacity: rotate(-55deg);
    }

  }
</style>

<script setup>

  let checkContact = ref(false);
  let dataPortfolio = ref([
    {id: 0,name: "EMINENCE", image: "project-image", Link: "#"},
    {id: 1,name: "ZAKA NAIL", image: "project-image", Link: "#"},
    {id: 2,name: "ChillMates", image: "project-image", Link: "#"},
    {id: 3,name: "SANAY LOX", image: "project-image", Link: "#"},
  ]);
  let projectRef = ref(null);


  function observeBlockVisibility() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
            // assign true when block is visible
          }
      });
    });

  }

  function positionCalculation() {
    return  Math.floor(Math.random() * 60) + '%';
  }
  
  onMounted(() => {
  })
</script>