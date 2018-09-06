<template>
  <div v-editable="blok" class="util__flex-eq">
    {{ blok.name }}
  </div>
</template>
<script>
export default {
  props: {
    blok: {
      type: String,
      default: ""
    }
  }
}
</script>
