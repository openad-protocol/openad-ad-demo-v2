<template>
  <!---->
  <div class="Home MFlex">
    <ul>
      <li v-for="(item,index) in paths" :key="index">
        <van-button type="primary" @click="router.push(item.path)">
          {{ item.desc }}
        </van-button>
      </li>
    </ul>
  </div>
  <!---->
</template>

<script>
import { defineComponent, ref } from 'vue';
import { Button } from 'vant';
import { useRouter } from 'vue-router';
export default defineComponent({
  name: 'HomeIndex',
  components: {
    'van-button': Button,
  },
  setup(){
    const paths = ref([{ path: '/SinglePage/async', desc: 'load ad with async mode...' },
      { path: '/SinglePage/single', desc: 'load ad with single ad...' },
      { path: '/SinglePage/multi', desc: 'load ads with multi ads...' }]);

    const router = useRouter();

    return { router, paths };
  },
});
</script>
<style scoped lang="less">
@import "index.less";
</style>
