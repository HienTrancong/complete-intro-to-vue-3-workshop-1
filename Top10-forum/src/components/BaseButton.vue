<script>
export default {
  props: {
    text: String,
    icon: String
  },
  data: () => ({}),

  computed: {}
}
</script>

<template>
  <button>{{ icon }}-{{ text }}</button>
</template>

<style></style>
