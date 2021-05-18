<template>
  <div class="recommend">
    <div v-for="item in recommends" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{ item.title }}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeRecommdView",
  props: {
    recommends: {
      type: Array,
      default() {
        return [];
      }
    }
  }
}
</script>

<style scoped>
.recommend {
  display: flex;
  flex-flow: row nowrap;
  margin: 1rem 0;
  padding: 0 0 20px;
  border-bottom: 8px solid #eee;
}

.recommend a {
  flex: 1;
  text-align: center;
}

.recommend img {
  width: 80%;
  margin: 0 auto .5rem;
}

.recommend-item {
  flex: 1;
  width: 100%;
}

</style>