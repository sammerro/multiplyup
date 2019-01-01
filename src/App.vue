<template>
  <div class="container">

    <header class="header">
      
        <div class="logo">
          <svg class="logo__svg" width="100%" height="100%" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
          <title>Logo MultiplyUp - asterisk</title>
          <g clip-path="url(#clip0)">
          <circle cx="50" cy="50" r="50" fill="var(--primary-color)"/>
          <path d="M42.4057 53.033L21.194 46.6293L24.4662 36.0237L45.6724 43.9743L45.1258 19.7847L55.8835 19.823L55.0929 44.3595L76.0032 36.6995L79.1994 47.3985L57.5908 53.72L71.4447 72.8241L62.7025 79.4024L49.6966 59.1059L36.97 78.8185L28.2038 72.3888L42.4057 53.033Z" fill="var(--secondary-color)"/>
          <path d="M42.4057 53.033L43.212 53.6246L44.0485 52.4844L42.6947 52.0757L42.4057 53.033ZM21.194 46.6293L20.2385 46.3345L19.9418 47.2958L20.905 47.5866L21.194 46.6293ZM24.4662 36.0237L24.8173 35.0873L23.8235 34.7148L23.5106 35.7289L24.4662 36.0237ZM45.6724 43.9743L45.3213 44.9107L46.7055 45.4296L46.6721 43.9517L45.6724 43.9743ZM45.1258 19.7847L45.1293 18.7847L44.1028 18.7811L44.126 19.8073L45.1258 19.7847ZM55.8835 19.823L56.883 19.8553L56.9161 18.8267L55.8871 18.8231L55.8835 19.823ZM55.0929 44.3595L54.0935 44.3272L54.0457 45.808L55.4369 45.2984L55.0929 44.3595ZM76.0032 36.6995L76.9613 36.4133L76.6571 35.395L75.6592 35.7606L76.0032 36.6995ZM79.1994 47.3985L79.4802 48.3583L80.4455 48.0759L80.1576 47.1122L79.1994 47.3985ZM57.5908 53.72L57.3101 52.7602L55.9484 53.1585L56.7813 54.307L57.5908 53.72ZM71.4447 72.8241L72.046 73.6232L72.8311 73.0325L72.2543 72.2371L71.4447 72.8241ZM62.7025 79.4024L61.8605 79.9419L62.4422 80.8497L63.3038 80.2015L62.7025 79.4024ZM49.6966 59.1059L50.5386 58.5664L49.6997 57.2574L48.8565 58.5635L49.6966 59.1059ZM36.97 78.8185L36.3786 79.6249L37.2345 80.2526L37.8102 79.3609L36.97 78.8185ZM28.2038 72.3888L27.3976 71.7972L26.8059 72.6036L27.6124 73.1952L28.2038 72.3888ZM42.6947 52.0757L21.483 45.672L20.905 47.5866L42.1167 53.9904L42.6947 52.0757ZM22.1496 46.9241L25.4217 36.3185L23.5106 35.7289L20.2385 46.3345L22.1496 46.9241ZM24.1151 36.9601L45.3213 44.9107L46.0234 43.038L24.8173 35.0873L24.1151 36.9601ZM46.6721 43.9517L46.1255 19.7621L44.126 19.8073L44.6726 43.9969L46.6721 43.9517ZM45.1222 20.7847L55.8799 20.823L55.8871 18.8231L45.1293 18.7847L45.1222 20.7847ZM54.884 19.7908L54.0935 44.3272L56.0924 44.3917L56.883 19.8553L54.884 19.7908ZM55.4369 45.2984L76.3471 37.6385L75.6592 35.7606L54.749 43.4205L55.4369 45.2984ZM75.045 36.9858L78.2413 47.6847L80.1576 47.1122L76.9613 36.4133L75.045 36.9858ZM78.9187 46.4387L57.3101 52.7602L57.8716 54.6797L79.4802 48.3583L78.9187 46.4387ZM56.7813 54.307L70.6352 73.4112L72.2543 72.2371L58.4004 53.1329L56.7813 54.307ZM70.8435 72.0251L62.1012 78.6034L63.3038 80.2015L72.046 73.6232L70.8435 72.0251ZM63.5445 78.8629L50.5386 58.5664L48.8546 59.6455L61.8605 79.9419L63.5445 78.8629ZM48.8565 58.5635L36.1299 78.2761L37.8102 79.3609L50.5367 59.6483L48.8565 58.5635ZM37.5615 78.0122L28.7953 71.5825L27.6124 73.1952L36.3786 79.6249L37.5615 78.0122ZM29.0101 72.9804L43.212 53.6246L41.5994 52.4415L27.3976 71.7972L29.0101 72.9804Z" fill="var(--logo-border-color)"/>
          </g>
          <defs>
          <clipPath id="clip0">
          <rect width="100" height="100"/>
          </clipPath>
          </defs>
        </svg>
        </div>

        <div class="title">
        <h1 class="title__main">
          MultiplyUP
        </h1>
       
      <p class="title__sub">
        App for improving and training your multiplying ability.
      </p>
      </div> 
    </header>

    <main class="main">
      <div class="game-container">
        <component :is="tileNow" @nexted="tileNow='app-question'" @answerChosen="answerChosen" :ifGoodAnswer="ifGoodAnswer">

        </component>  
      </div>
    </main>

  <footer class="footer">
    <p class="footer__text">
    <a href="#" onclick="localStorage.setItem('mode', (localStorage.getItem('mode') || 'light') === 'light' ? 'bright' : 'light'); localStorage.getItem('mode') === 'light' ? document.querySelector('body').classList.add('light') : document.querySelector('body').classList.remove('light')" title="Dark/bright mode">🌓 Light/dark</a>
    </p>
    <p class="footer__text">
     <a href="https://github.com/sammerro">Click and see my other works!</a> 
    </p>
  </footer>
  
  </div>
</template>

<script>
import AppResult from './components/AppResult.vue';
import AppQuestion from './components/AppQuestion.vue';

export default {
  data() {
    return {
      tileNow: 'app-result',
      ifGoodAnswer: true
    }
  },
  components: {AppResult, AppQuestion},
  methods: {
    answerChosen(ifCorrect) {
      if (ifCorrect ) {
        this.ifGoodAnswer = true;
      } else {
        this.ifGoodAnswer = false;
      }
        this.tileNow = 'app-result';
    }
  }
}
</script>

<style lang="scss">

@import './styles/normalize.css';
//upper stylesheet (normalize) have beeen slightly modified by me - mainly margins
@import url('https://fonts.googleapis.com/css?family=Roboto');

:root {
  box-sizing: border-box;
  font-size: calc( 16px + (20 - 16) * ( (100vmin - 300px) / ( 900 - 300) ));
  --primary-color: #92b470;
  --secondary-color: #70b4b4;
  --logo-border-color: rgb(90, 90, 90);
  --third-color:#2f4b4b;
  --text-color-main: #eee;
  --text-color-second: #aaa;
  --bg-color:#222;
  --bg-color-second: #555;

  --btn-color: #0c642e;
  --btn-color-hover:#073f1d;
  --btn-color-active:  #053116;

  --error-text-color: rgb(226, 146, 146);
  --success-text-color:  rgb(166, 224, 143);
}

*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

body{
  font-family: Roboto, Helevetica, Arial, sans-serif;
}

.container {
  display: flex;
  flex-flow: column nowrap;
  min-height: 100vh;
  color: var(--text-color-main);
  background: var(--bg-color);
}
//mods dark and light

.light {
  --primary-color: #88dbdb;
  --secondary-color:#aed389;
  --third-color:#b5e6a6;
  --text-color-main: #222;
  --text-color-second: #666;
  --bg-color:#eee;
  --bg-color-second: #bbb;

  --error-text-color: rgb(77, 16, 16);
  --success-text-color:  rgb(29, 70, 12);

  --btn-color: #91dbad;
  --btn-color-hover:#80b495;
  --btn-color-active:  #397a52;
}
//mods --end
.header {
  background-color:var(--third-color);
  //css locks
  padding: calc( 6px + (20 - 6) * ( (100vmin - 300px) / ( 900 - 300) ));
  display: flex;
  align-items: center;
  flex-flow: row nowrap;
  flex: 0 0 auto;
    .logo {
      width: 4em;
      height: 4em;
      margin-right:.5em;
      flex-shrink: 0;
    }
    @media (min-width: 1000px) {
      .logo:hover {
        animation: rotate .5s infinite linear;
      }
    }
   .title {
        flex-shrink: 1;
        line-height: 1.3;
      &__main {
        font-weight: 300;
        letter-spacing: .2em;
      }
      &__sub {
        font-size: .8em;
        font-weight: 300;
        color: var(--text-color-second);
      }
  }
}

.main {
  flex: 1 1 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  .game-container {
    border: 1px solid var(--third-color);
    width: 100vw;
    align-self: stretch;
  }
  @media (min-height: 600px) {
    .game-container {
      align-self: center;
      height: 26.4em;
      
    }
  }

  @media (min-width: 450px) {
    .game-container {
      width: calc( 450px + (558 - 450) * ( (100vw - 450px) / ( 700 - 450) ));
    }
  }
    @media (min-width: 700px) {
    .game-container {
      width: 29.9em;
    }
  }
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: .8em;
  flex: 0 0 2.5em;
  color: var(--text-color-second);
  padding-right: 1em;
  padding-left: 1em;
    &__text {
      a {
        text-decoration: none;
        color: inherit;
        transition: all .15s;
      }
      a:hover {
        color: var(--text-color-main);
      }
    }
  }

/* .rotating {
  animation: rotate 1s infinite linear;
} */

.btn {
  color: var(--text-color-main);
  background-color:var(--btn-color);
  border: .1em solid var(--text-color-main);
  border-radius: .2em;
  padding: .5em 1.5em;
  cursor: pointer;
  transition: all .15s;
}
.btn:hover {
  background-color:var(--btn-color-hover);
}
.btn:active {
  background-color:var(--btn-color-active);
}

.darken {
      background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5));
}

@keyframes rotate {
  from {
    transform: rotate3d(0, 0, 0, 360deg);
  }

  to {
   transform: rotate3d(0, 0, 1, 360deg);
  }
}

</style>

