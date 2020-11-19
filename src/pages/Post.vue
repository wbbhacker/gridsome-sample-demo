<template>
  <Layout>
      <div>
        <h1>Post</h1>
        <ul>
          <li v-for="edge in $page.posts.edges" :key="edge.node.id">
            <g-link :to="edge.node.path">{{ edge.node.title }}</g-link>
            <!-- <a href="">{{ edge.node.title}}</a> -->
          </li>
          <!-- <div>{{ $page }}</div> -->
        </ul>
      </div>
  </Layout>
</template>
<page-query>
query{
  posts:allPost{
    edges{
      node{
        id
        title
        content
        path
      }
    }
	}
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Post'
  }
}
</script>
