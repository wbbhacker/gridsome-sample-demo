<template>
  <Layout>
      <div>
        <h1>Post</h1>
        <ul>
          <li v-for="post in posts" :key="post.id">
            <!-- <g-link to="/">{{ edge.node.title }}</g-link> -->
            <a href="/">{{ post.title}}</a>
          </li>
          <!-- <div>{{ $page }}</div> -->
        </ul>
      </div>
  </Layout>
</template>
<script>

import axios from 'axios'
export default {
  metaInfo: {
    title: 'Post'
  },
  data(){
    return {
      posts:[]
    }
  },
  async created(){
    const {data} = await await axios.get('http://jsonplaceholder.typicode.com/posts')
    this.posts = data
  }
}
</script>
