<template>
  <div class="container">
    <div>
      <Logo />
      <line-chart-container />
      <h1 class="title">nuxt-fundamentals</h1>
      <div class="links">
       <nuxt-link v-for="post in posts" :to="{name: 'post-id', params:{id: post.id}}" :key="post.id" class="button--grey">
         {{post.title}}
       </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import LineChartContainer from '../components/LineChartContainer.vue';
import Logo from '../components/Logo'



export default {
  components:{
    Logo,
    LineChartContainer
  },
  head(){
    return {
      title: 'Home Page',
      meta: [
        {name: 'twitter:title', content: 'Nuxt Fundamental'},
        {name: 'twitter:description', content: 'A Nuxt.js test page'},
        {name: 'twitter:image', content: 'https://nuxtjs.org/logos/nuxt-icon-white.png'},
        {name: 'twitter:card', content: 'summary_large_image'},
      ]
    }
  },
  computed: {
    posts(){
      return this.$store.state.posts.all
    }
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
