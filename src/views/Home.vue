<template>
  <div class="home">
    <div class="hero">
      <h1 class="heading">Willkommen!</h1>
      <p class="sub-heading">Wir bringen IOTA ins Saarland.</p>
      <img alt="iota.saarland" class="iota-saarland-logo" src="../assets/logo.svg">
    </div>

    <div class="section section-background knowledge">
      <div class="container">
        <h2>Was ist IOTA?</h2>
        <p>IOTA ist eine revolutionäre Open-Source-Technologie und Kryptowährung. Sie wird gefördert und bereitgestellt von der IOTA Stiftung mit Hauptsitz in Berlin. Die IOTA-Technologie ermöglicht es Geräten des Internet of Things (IoT) dezentral und verschlüsselt zu kommunizieren.</p>
      </div>
    </div>

     <div class="section news">
      <div class="container">
        <div class="headline-wrapper">
          <h2>Was macht IOTA Saarland?</h2>
        </div>
        <div class="divider"></div>
        <FeatureList />  
      </div>
    </div>


    <div class="section section-background knowledge">
      <div class="container">
        <h2>Twitter</h2>
        <p>Aktuelle Infos gibt es auf unserem Twitter Account <a href="https://twitter.com/IotaSaar">@IotaSaar</a>.</p>
        <div class="twitter">
        <Timeline id="iotasaar" sourceType="profile" :options="{ tweetLimit: '3' }"/>
        </div>
      </div>
    </div>

    <div class="section news">
      <div class="container">
        <div class="headline-wrapper">
          <h2>Neuigkeiten von der IOTA Foundation</h2>
          <router-link to="/news" tag="button" class="el-button el-button--primary">Alle Neuigkeiten</router-link>
        </div>
        <div class="divider"></div>
        <LatestNews/>
      </div>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import LatestNews from "@/components/LatestNews.vue";
import FeatureList from "@/components/FeatureList.vue";
import { Timeline } from "vue-tweet-embed";

export default {
  name: "home",
  components: { LatestNews, FeatureList, Timeline }
};
</script>

<style lang="scss">
.twitter {
  margin: 0 auto;
  max-width: 400px;
}
.el-main {
  padding: 0px !important;
}
.home {
  text-align: center;
}
.hero {
  margin: 0 10px;
}
.section {
  padding: 80px 0;
  &-background {
    background-color: var(--light);
    p {
      max-width: 600px;
      margin: 15px auto 30px;
    }
    a {
      text-decoration: none;
    }
  }
  .headline-wrapper {
    padding: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
@media only screen and (max-width: 740px) {
  .hero {
    padding-top: 40px;
  }
  .headline-wrapper {
    flex-wrap: wrap;
    h2 {
      margin-bottom: 20px;
    }
  }
  .btn-social {
    margin-bottom: 5px !important;
  }
}

.iota-saarland-logo {
  max-width: 400px;
  max-height: 400px;
}
</style>