<template>
  <div>
    <!-- 第一种最原始的获取方式 -->
    <!-- <h3>{{ $store.state.count }}</h3> -->

    <!-- 第二种提供了getters的获取方式 -->
    <!-- <h3>{{ $store.getters.optCount }}</h3> -->

    <!-- 
        第三种获取方式通过 mapGetters的方式

        1. 按需引入mapGetters   

        import { mapGetters } from "vuex";

        2. 在computed中使用以下方式获取   

          computed: {
            // getters 返回的是一个数组
            ...mapGetters(["optCount"])
          }

     -->
    <h3> {{optCount}}</h3>
  </div>
</template>

<script>
// 按需引入 getters

import { mapGetters } from "vuex";
export default {
  data() {
    return {
      // count: 0
    };
  },
  computed: {
    // mapGetters 返回的是一个数组 数组里面的每一个元素都是一个方法
    ...mapGetters(["optCount"])
  }
};
</script>

<style lang="scss" scoped>
</style>
