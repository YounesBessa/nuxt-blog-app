<template>
  <div>
    <h1>Article n°{{ article.id }}</h1>

    <div>
      <h2> Titre: {{ article.title }}</h2>
      <p> {{ article.content }}</p>
      <span>Auteur: {{ article.author }}</span>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Article from '~/plugins/models/Article'

export default Vue.extend({
  name: 'ArticleDetailPage',
  async asyncData({ $axios, params }) {
    const id  = params.id
    const { data } = await $axios.$get(
      `http://localhost:4000/articles/get/single/article/${id}`
    )
    return {
      article: data.data[0],
    }
  },
  data(): { article: Article } {
    return {
      article: new Article(),
    }
  },
})
</script>
