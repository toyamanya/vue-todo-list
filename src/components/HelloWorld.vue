<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter />
    <item-list />
  </div>
</template>

<script>
import Counter from "./Counter.vue";
import ItemList from "./ItemList.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    Counter,
    ItemList
  }
};
</script>
