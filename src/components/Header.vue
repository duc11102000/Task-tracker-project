<template>
  <header>
    <h1>{{ head }}</h1>
    <Button @toggle-add-task="$emit('toggle-add-task')" text="Add task" color="black" v-show="homePage"></Button>
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "header",
  components: {
    Button,
},
  props: {
    head: {
      type: String,
      default: "Hello Vue !!!",
    },
  },

  computed: {
    homePage() {
      if(this.$route.path === '/') {
        return true
      } else {
        return false
      }
    }
  }
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
