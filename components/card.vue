
<template>
  <nuxt-link :to="`/articles/${id}`">
    <article class="card">
      <h1 class="card_title">{{ title }}</h1>
      <p class="card_text">{{ body.content[0].content[0].value }}</p>
      <p class="card_date">{{ date }}</p>
    </article>
  </nuxt-link>
</template>
<script>
export default {
  props: {
    id: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    body: {
      type: String,
      default: ''
    },
    date: {
      type: String,
      default: ''
    }
  }
}
</script>
