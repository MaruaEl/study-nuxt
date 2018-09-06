<template>
  <section class="util__container">
    <component v-if="story.content.component" :key="story.content._uid" :blok="story.content" :is="story.content.component"/>
  </section>
</template>
<script>
import storyblokLivePreview from "@/mixins/storyblokLivePreview"

export default {
  mixins: [storyblokLivePreview],
  props: {
    blok: {
      type: "string",
      default: ""
    }
  },
  data() {
    return {
      story: {
        content: {}
      }
    }
  },
  asyncData(context) {
    let version =
      context.query._storyblok || context.isDev ? "draft" : "published"

    return context.app.$storyapi
      .get("cdn/stories/home", {
        version: version,
        cv: context.store.state.cacheVersion
      })
      .then(response => {
        return response.data
      })
      .catch(error => {
        context.error({
          statusCode: error.response.status,
          message: error.response.data
        })
      })
  }
}
</script>
<style>
.container {
  font-family: "Quicksand", "Source Sans Pro", apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  padding: 3.5rem;
}
</style>
