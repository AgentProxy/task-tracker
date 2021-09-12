<template>
  <header>
    <h1><router-link to="/">{{ title }}</router-link></h1>
    <Button v-show="isHomePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask? 'Close' : 'Add Task'" :color="showAddTask? 'red' : 'green'" />
  </header>
</template>

<script>
import Button from "./Button";
export default {
  name: "Header",
  props: {
    showAddTask: Boolean,
    title: String,
  },
  computed: {
    isHomePage() {
      return this.$route.path === '/';
    }
  },
  components: {
    Button,
  },
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