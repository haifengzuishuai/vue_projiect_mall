<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles" class="tab-control-item" :class="{active:index===currentIndex}" @click="tabClick(index)">
      <span>{{ item }}</span>
    </div>

  </div>

</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data() {
    return {
      currentIndex: 0
    }
  },
  methods:{
    tabClick(index){
      this.currentIndex=index;
      this.$emit('tabClicka',index)

    }
  }
}
</script>

<style scoped>
.tab-control {
  display: flex;
  text-align: center;
  font-size: 15px;
  background-color: #fff;
}

.tab-control-item span{
  padding: 5px;
}
.tab-control-item {
  height: 40px;
  flex: 1;
  line-height: 40px;
}
.active{
  color: var(--color-high-text);
}
.active span{
  border-bottom:3px solid var(--color-tint);
}
</style>