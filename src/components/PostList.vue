<template>
  <div>
    <h2>{{ title }}</h2>
    <div class="post-list-wrapper">
<!--      <a href="#" v-bind:key="post.id" class="card" v-for="post in posts">-->
<!--        <h3 class="card-title">{{ post.title }}</h3>-->
<!--        <p class="card-description">{{ post.body }}</p>-->
<!--      </a>-->
      <router-link
        :to="{path: `/posts/${post.id}`}">
        <h3 class="card-title">{{ post.title }}</h3>
        <p class="card-description">{{ post.body }}</p>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Posts List',
      posts: [],
    };
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((json) => {
        this.posts = json;
      });
  },
};
</script>

<style>
.post-list-wrapper {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 20px;
  max-width: 1140px;
  margin: 0 auto;
  flex-wrap: wrap;
  padding-top: 12px;
}

.card {
  box-shadow: rgba(0, 0, 0, 0.117647) 0px 1px 6px, rgba(0, 0, 0, 0.117647) 0px 1px 4px;
  transition: .15s all ease-in-out;
  text-decoration: none;
  padding: 12px;
  color: #03A9F4;
  font-family: Arial, sans-serif;
}

.card:hover {
  transform: scale(1.1);
}

.card-title {
  font-size: 24px;
  text-align: center;
  margin-bottom: 15px;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.card-description {
  font-size: 12px;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

</style>
