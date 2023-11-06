<template>
  <div
    class="flex justify-between py-2 px-2"
    :class="{ 'bg-green-600': this.todo.done }"
  >
    <h1 class="cursor-pointer" @click="toggleTodo">{{ todo.todo }}</h1>
    <button class="bg-red-600 py-1 px-2 rounded" @click="removeTodo">-</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todoprop", "todoindex"],
  data() {
    return {
      todo: this.todoprop,
    };
  },
  methods: {
    toggleTodo() {
      this.$emit("toggledone-index", this.todoindex);
    },
    removeTodo() {
      this.$emit("removetodo-index", this.todoindex);
    },
  },
};
</script>
