<template>
  <div>
    <todo-header></todo-header>
    <todo-input v-on:add="addTodoItem"></todo-input>
    <todo-list v-bind:todos="items"></todo-list>
  </div>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "@/components/TodoInput.vue"; // @가 무엇인지 다음시간에 알려주셔야 함
import TodoList from "./components/TodoList";

export default {
  data() {
    return {
      items: []
    };
  },
  methods: {
    fetchItems() {
      for (let i = 0; i < localStorage.length; i++) {
        const value = localStorage.key(i);
        this.items.push(value);
      }
    },
    addTodoItem(item) {
      this.items.push(item);
      localStorage.setItem(item, item);
    }
  },
  created() {
    this.fetchItems();
  },
  components: {
    'todo-header': TodoHeader,
    'todo-input': TodoInput,
    'todo-list': TodoList
  }
}
</script>

<style></style>
