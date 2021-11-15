<template>
  <div>
    <input type="text" v-model="enterTxt"  @keyup.enter="addToDos()" >
    <button :disabled="enterTxt.length <= 0" @click="addToDos()">Add ToDo</button>
    <ul>
      <div v-if="todos.length === 0">No To Do Actions avialable</div>
      <li v-for="(todo, index) in todos"
    :key="index">{{todo}} <button @click="removeToDo(index)">X</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enterTxt: '',
      todos: []
    }
  },
  methods: {
    addToDos() {
      console.log(this.enterTxt);
      this.todos.push(this.enterTxt);
      this.enterTxt ='';
    },
    removeToDo(idx) {
      return this.todos.splice(idx, 1)
    }
  }
}
</script>

<style scoped>
ul{
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
  padding: 10px;

}
</style>