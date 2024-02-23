<template>
  <div class="header">
    <h1>FEED RYO YAMADA (#1 WAIFU)</h1>
    <p>a really badly made game to fulfill your (my) internal loneliness</p>
  </div>
  <div>
   <compliment></compliment>
   <feed></feed>
  </div>
</template>

<script setup>
import compliment from './components/icons/compliment.vue';
import feed from './components/icons/feed.vue';
</script>

<style style="scoped">
.header{
  font-size: 2rem;
  padding-bottom: 1.2rem;
}
h1{
  font-weight: bold;
}

</style>