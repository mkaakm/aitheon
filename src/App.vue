<template>
  <div>
<!--  <div id="app">-->
    <router-view/>
<!--    <PageTitle />-->
    <page-title></page-title>
<!--    <PostList />-->
<!--  </div>-->
  </div>
</template>

<script>
// import PostList from '@/components/PostList.vue';
import PageTitle from '@/components/PageTitle.vue';

export default {
  name: 'app',
  components: {
    // PostList,
    PageTitle,
  },
};
</script>
<style>

</style>
