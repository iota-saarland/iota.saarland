<template>
  <div class="footer">
    <div class="row">
      <div class="footer-main">
        <router-link to="/" class="footer-logo" exact-active-class="active">
          <img alt="einfachIOTA" class="logo" src="../assets/logo.svg">
        </router-link>
        <p>Wir bringen IOTA ins Saarland.</p>
        <p>Unsere Aufgabe ist es, IOTA Technologien im Saarland vorzustellen, Veranstaltungen zu organsieren und das IOTA Netwertk weiter auszubauen. </p>
      </div>
      <div class="footer-main">
        <h4>Mehr</h4>
        <div class="divider"></div>

        <router-link to="/" class="footer-main-link">Startseite</router-link>
      </div>
      <div class="footer-main">
        <h4>Partner</h4>
        <div class="divider"></div>
        <a href="https://einfachIOTA.de/" target="_blank" class="footer-main-link">einfachIOTA</a>
      </div>
      <div class="footer-main">
        <h4>IOTA</h4>
        <div class="divider"></div>
        <a href="https://www.iota.org" target="_blank" class="footer-main-link">Offizielle Webseite</a>
        <a href="https://ecosystem.iota.org" target="_blank" class="footer-main-link">Ökosystem</a>
        <a href="https://blog.iota.org" target="_blank" class="footer-main-link">Blog</a>
      </div>
    </div>
    <div class="row footer-bottom">
      <div class="footer-bottom-col">© iota.saarland</div>
      <div class="footer-bottom-col">
        <a href="https://twitter.com/IOTASaar" target="_blank" class="footer-main-link">Twitter (@IotaSaar)</a>
      </div>
      <div class="footer-bottom-col">
        <router-link to="imprint" class="footer-main-link">Impressum</router-link>
        <router-link to="privacy" class="footer-main-link">Datenschutz</router-link>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.footer {
  background-color: var(--white);
  width: 100%;
  padding: 50px 50px 0;
  box-sizing: border-box;
  text-align: center;
  border-top: 5px solid var(--primary);
  color: var(--dark);
  .row {
    display: flex;
    justify-content: space-between;
  }
  .footer-main {
    text-align: left;
    width: 25%;
    margin-right: 50px;
    margin-bottom: 50px;
    &:last-child {
      margin-right: 0;
    }
    .logo {
      height: 40px;
    }
    h4 {
      font-size: 20px;
      line-height: 1;
      margin-bottom: 15px;
    }
    .divider {
      width: 50px;
      margin: 15px 0;
    }
    .footer-main-link {
      display: block;
      color: var(--dark);
      margin: 0;
      line-height: 2;
      font-size: 16px;
      text-decoration: none;
      transition: color 200ms ease-in-out;
      &:hover {
        color: var(--primary);
      }
    }
  }
  .footer-bottom {
    padding: 15px 50px;
    margin: 0 -50px;
    border-top: 0.5px solid rgba(0, 0, 0, 0.25);
    color: rgba(0, 0, 0, 0.75);
    .footer-bottom-col {
      .footer-main-link {
        margin: 0 10px;
        &:first-child {
          margin-left: 0;
        }
        &:last-child {
          margin-right: 0;
        }
      }
    }
    .footer-main-link {
      color: rgba(0, 0, 0, 0.75);
      text-decoration: none;
      transition: color 200ms ease-in-out;
      &:hover {
        color: var(--primary);
      }
    }
  }
}
@media only screen and (max-width: 992px) {
  .footer {
    .row {
      flex-wrap: wrap;
      .footer-main {
        width: calc(50% - 50px);
        &:nth-child(even) {
          margin-right: 0;
        }
      }
    }
    .row.footer-bottom {
      .footer-bottom-col {
        width: 50%;
        &:first-child {
          text-align: left;
        }
        &:nth-child(2) {
          text-align: right;
        }
        &:nth-child(3) {
          width: 100%;
          text-align: left;
          margin-top: 10px;
        }
      }
    }
  }
}
@media only screen and (max-width: 624px) {
  .footer {
    .row {
      flex-wrap: wrap;
      .footer-main {
        width: 100%;
        margin-right: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
      }
    }
    .row.footer-bottom {
      .footer-bottom-col {
        width: 100%;
        &:first-child {
          text-align: center;
        }
        &:nth-child(2) {
          text-align: center;
          margin-top: 10px;
        }
        &:nth-child(3) {
          text-align: center;
          margin-top: 10px;
        }
      }
    }
  }
}
@media only screen and (max-width: 360px) {
  .footer {
    padding: 30px 30px 0;
    .row.footer-bottom {
      margin: 0 -30px;
      padding: 15px 30px;
    }
  }
}
</style>