<template>
  <div>
    <p>todoList</p>
    <!-- todoリストの表示 -->
    <div v-for="todo in todos" :key="todo.name">
      <div class="todo">
        <label :class="{ doneStyle: todo.isChecked }">
          <input type="checkbox" v-model="todo.isChecked" />
          {{ todo.name }}
        </label>
      </div>
    </div>
    <!-- Todoの追加-->
    <div>
      <label for>
        <input type="text" v-model="newTodoName" placeholder="add Todo" />
      </label>
      <button @click="addTodo">追加</button>
    </div>
    <!--todo完了で移動-->
    <div>
      テェックをつけたものを完了リストに移動
      <button @click="moveTodo">移動</button>
    </div>
    <!-- doneリストの表示 -->
    <div v-for="done in dones" :key="done.name">
      <div class="done">{{ done.name }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "todoList",
  data() {
    return {
      todos: [
        { name: "hoge", isChecked: false },
        { name: "huga", isChecked: true },
        { name: "nya", isChecked: false },
        { name: "pyo", isChecked: true }
      ],
      dones: [],
      newTodoName: ""
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ name: this.newTodoName, isChecked: false });
      this.newTodoName = "";
    },
    moveTodo() {
      //donesと結合
      this.dones = this.dones.concat(
        // donesを更新
        this.todos.filter(todo => todo.isChecked === true)
      );
      // todosを更新
      this.todos = this.todos.filter(todo => todo.isChecked === false);
    }
  }
};
</script>

<style>
.doneStyle {
  text-decoration: line-through;
}
</style>
