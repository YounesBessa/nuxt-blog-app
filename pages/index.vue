<template>
  <div class="page page-home">
      <h1 class="text-3xl font-bold">Accueil</h1>
      <div class="flex flex-row gap-2">
          <NuxtLink to="/article">Liste des articles</NuxtLink>
      </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'IndexPage',
})
</script>
