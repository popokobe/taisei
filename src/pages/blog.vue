<template>
    <div>
        <h1 v-for="post in posts" :key="post.id">{{ post.fields.title }}</h1>
    </div>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()

export default {
    async asyncData({ params }) {
    // 記事一覧を取得
    const entries = await client.getEntries({
      content_type: process.env.CTFL_CONTENT_TYPE_POST
    })
    return {
      posts: entries.items
    }
  },
  created () {
      console.log(this.posts);
  }
}
</script>