<template>
  <div>
    <input type="text" v-model="inputText" />
    <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: ""
    };
  },
  methods: {
    addTodo() {
      const value = this.inputText;
      this.$emit("add", value);
      this.initForm();
    },
    initForm() {
      this.inputText = "";
    }
  }
};
</script>
