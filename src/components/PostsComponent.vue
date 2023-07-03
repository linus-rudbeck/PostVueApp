<template>
  <div>
    <span class="posts" v-for="d in posts" :key="d">
      <span style="display: flex; flex-direction: column">
        <p><b>{{ d.title }} </b>| Date: {{ d.date }}</p> <br />
        <p class="blog-text">{{ d.content }}</p>
        <p class="blog-text" v-if="d.show">{{ d.moreContent }}</p>
      </span>
      
      <router-link
        :to="{ name: 'post', params: { id: d.id }}">
        Show Post
      </router-link>

  
    </span>
  </div>
</template>
<script>
import data from "@/data";
export default {
  data() {
    console.log(data);
    return {
      posts: data.posts
    }
  },
  mounted() {
    console.log(data);
  }
}
</script>
<style scoped>
.blog-text {
  max-width: 900px;
  align-self: center;
}

.posts {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 16px;
  border-bottom: 2px solid #42b9836e;
}

button {
  background-color: #42b983;
  color: #fff;
  border: none;
  font-weight: 600;
  border-radius: 3px;
  padding: 10px 25px;
  height: 40px;
  margin-top: 100px;
}
</style>