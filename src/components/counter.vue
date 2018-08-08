<template>
  <div>
    <input type="button" value="减少" @click="remove">
    <input type="button" value="增加" @click="add">
    <br>
    <input type="text" v-model="$store.state.count">
  </div>
</template>

<script>
//按需引入 mapMutations
import { mapMutations } from "vuex";

export default {
  data() {
    return {
      // count: 0
    };
  },
  methods: {
    // add() {
    //   // 千万不要这么用，不符合 vuex 的设计理念
    //   // 第一种获取mutation里面的函数
    //   // this.$store.state.count++;

    //   // 第二种获取mutation里面的函数  this.$store.commit("increment")
    //   // this.$store.commit("increment");
    // },
    // remove() {
    //   // this.$store.commit("subtract", { c: 3, d: 1 });
    //   this.$store.commit("subtract");
    // }


    // 第三种获取store 里面定义的函数的方法     
    // 1. 按需引入 mapMutations

    // 2. 在methods里面使用 ...mapMutations获取  

    ...mapMutations({
      add: "increment", // 将 `this.add()` 映射为 `this.$store.commit('increment')`
      remove: "subtract"
    })
  },
  computed: {}
};
</script>

<style lang="scss" scoped>
</style>
