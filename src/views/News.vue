<template>
  <div class="news">
    <div class="hero">
      <div class="container">
        <h1 class="heading">Neuigkeiten von der IOTA Foundation</h1>
        <p class="subheading" >Übersetzt und Bereitgestellt von <a href="https://einfachIOTA.de" target="_blank">einfachIOTA.de</a>.</p>
        <div class="divider"></div>
      </div>
    </div>
    <PostList
      :posts="posts"
      :per_page="per_page"
      :current_page="current_page"
      :total="total"
       v-on:handleCurrentChange="handleCurrentChange"
    />
  </div>
</template>

<script>
import GhostContentAPI from "@tryghost/content-api";
import PostList from "@/components/PostList.vue";

const api = new GhostContentAPI({
  url: "https://ghost.einfachiota.de",
  key: process.env.VUE_APP_API_KEY,
  version: "v2"
});

export default {
  name: "news",
  components: {PostList},
  data() {
    return {
      posts: [],
      per_page: 12,
      current_page: 1,
      total: 1,
    };
  },
  methods: {
    loadData(page) {
      api.posts
        .browse({
          limit: 12,
          page: page,
          include: "tags,authors",
          filter: "tag:news"
        })
        .then(posts => {
          this.current_page = posts.meta.pagination.page
          this.total = posts.meta.pagination.total
          this.posts = posts;
          window.scrollTo(0,0);

        })
        .catch(err => {
          console.error(err);
        });
    },
    handleCurrentChange(val) {
        this.currentPage = val;
        this.loadData(val);

    }
  },
  created() {
    this.loadData(this.current_page);
  }
};
</script>

<style lang="scss" scoped>

.news {
  padding-bottom: 100px;
}

h1.heading {
  text-align: left !important;
}

.subheading {
    text-align: left;
}

</style>

