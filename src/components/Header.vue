<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
    <!-- <Button text="Update Task" color="blue"/>
        <Button text="Delete Task" color="red"/> -->
  </header>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Header",
  // props: ['title']
  props: {
    title: {
      type: String,
    },
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      // if redirect .push
      if (this.$route.path === "/") {
        return true;
      }
      return false;
    },
  },
};
</script>

<style scoped>
/* scoped means only for this component */
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
