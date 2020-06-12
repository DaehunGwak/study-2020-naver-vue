<template>
  <div>
    <ul>
      <li v-for="item in todos" v-model="todos">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["todos"],
  data() {
    return {
      items: []
    };
  }
};
</script>
