<template>
    <div>
        <h1> Add Article Page </h1>
        <form>
            <div>
                <label for="title">Titre</label>
                <input id="title" v-model="article.title" type="text">
            </div>
            <div>
                <label for="content">Contenu</label>
                <textarea id="content" v-model="article.content"></textarea>
            </div>
            <div>
                <label for="author">Auteur</label>
                <input id="author" v-model="article.author" type="text">
            </div>
            <div>
                <label for="date">Date</label>
                <input id="date" v-model="article.date" type="date">
            </div>
            <div>
                <button type="submit" @click="create">Ajouter</button>
            </div>
        </form>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Article from '~/plugins/models/Article';

export default Vue.extend({
    name: 'AddArticlePage',
    data(): {article: Article} {
        return {
            article: new Article()
        }
    },
    methods: {
         create(e:any) {
            e.preventDefault();
            const data = {
                // make the id auto increment
                id: 1,
                author: this.author,
                title: this.title,
                content: this.content,
                date: this.date
            }
            // const res = await this.services.article.create(data);
            console.log(data);
        }
    },
})
</script>
  