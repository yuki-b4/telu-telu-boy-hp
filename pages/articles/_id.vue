<template>
  <section class="slug">
    <h1 class="slug_title">
      {{ post.fields.title }}
    </h1>
    <p class="slug_date">{{ post.sys.updatedAt }}</p>
    <div>
      {{ post.fields.body.content[0].content[0].value }}
    </div>
  </section>
</template>
<script>
  import { createClient } from '~/plugins/contentful.js'

  const client = createClient()
  export default {
    async asyncData({ params, payload }) {
      // IDをキーに記事を取得
      const entry = await client.getEntry(params.id)
      return {
        post: entry
      }
    },
    methods: {
      toHtmlString(obj) {
        return documentToHtmlString(obj)
      }
    }
  }
</script>
