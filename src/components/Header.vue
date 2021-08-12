<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePg"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Cancel Add Task' : 'Add Task'"
      :color="showAddTask ? '' : 'green'"
    />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePg() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
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
