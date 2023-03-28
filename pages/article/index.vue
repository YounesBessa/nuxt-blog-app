<template>
    <div>
        <h1> Liste des articles </h1>
            <NuxtLink to="/article/add">Ajouter un article</NuxtLink>
        <ul>
            <li v-for="article in articles" :key="article.id">
                <NuxtLink :to="'/article/'+article.id">
                    <span>{{ article.title }}, par <i>{{ article.author }}</i> </span> 
                </NuxtLink>         
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Article from '~/plugins/models/Article';

export default Vue.extend({
    name: 'ArticlePage',
    async asyncData({ $axios }) {
        const { data } = await $axios.$get("http://localhost:4000/articles/getArticle");
        return {
            articles: data.data
        }
    },
    data(): {articles: Article[]} {
        return {
            articles: []
        }
    }
})
</script>
  