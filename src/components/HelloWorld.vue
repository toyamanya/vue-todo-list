<template>
  <div>
    <h1>{{ msg }}</h1>
    <!-- counter /-->
    <!--item-list /-->
    <todo-list />
  </div>
</template>

<script>
//import Counter from "./Counter.vue";
//import ItemList from "./ItemList.vue";
import TodoList from "./TodoList.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    //Counter,
    //ItemList
    TodoList
  }
};
</script>
