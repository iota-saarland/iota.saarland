<template>
  <div class="row">
    <FeatureCard :feature="feature" v-for="feature in  features" v-bind:key="feature.id"/>
  </div>
</template>

<script>

import FeatureCard from '@/components/FeatureCard.vue'


export default {
  name: "latestNews",
  components: {
    FeatureCard
  },
  data() {
    return {
      features: [
          {
              id: 1,
              title: "Meetups",
              description: "Wir veranstalten Meetups verteilt im ganzen Saarland.",
              image: "../assets/meetups.jpg"
          },
          {
              id: 2,
              title: "Workshops",
              description: "Wir geben Workshops um den Einstieg in IOTA zu erleichtern.",
              image: "workshops.jpg"
          },
          {
              id: 3,
              title: "Netzwerken",
              description: "Wir sind Teil eines großen Netzwerkes mit Experten aus vielen verschiedenen Bereichen",
              image: "netzwerk.jpg"
          },
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
  .row {
    display: flex;
    justify-content: space-between;
    flex-wrap: nowrap;
    margin: 30px -25px 0;
  }
  @media only screen and (max-width: 920px) {
    .row {
      flex-wrap: wrap;
    }
  }
</style>