<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
  data() {
    return {
    };
  },
  methods: {
  }
}
</script>

<style scoped>
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>