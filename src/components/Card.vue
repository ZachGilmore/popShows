<template>
  <div class="card" style="width: 18rem">
    <img :src="`https://image.tmdb.org/t/p/w500${movieobj.poster_path}`" class="card-img-top">
    <div class="card-body">
      <h5 class="card-title">{{movieobj.name}}</h5>
      <p class="card-text">
        {{movieobj.overview}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props:['movieobj']
};
</script>