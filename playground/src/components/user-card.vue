<script>
export default {
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
  emits: ["change-name"],
  methods: {
    tellParentChangeName() {
      this.$emit("change-name");
    },
  },
};
</script>

<template>
  <h1>User: {{ user.name }}</h1>
  <p>Favorite Food: {{ user.food }}</p>
  <button @click="tellParentChangeName" :class="$style.button">
    Change Name
  </button>
</template>

<style module>
.button {
  border: 10px solid green;
}
</style>
