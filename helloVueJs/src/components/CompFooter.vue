<template>
  <footer>
    <h1>{{ title }}</h1>
  </footer>
</template>

<script>
export default {
  name: "comp-footer",
  props: {
    title:{
        type: String,
        default: 'Value Default'
    }
  },
  data() {
    return {
    };
  }
};
</script>

<style></style>
