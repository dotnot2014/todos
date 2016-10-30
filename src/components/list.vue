<template>
  <section class="todoapp">
    <header class="header">
      <h1>Todos</h1>
      <input class="new-todo" autofocus autocomplete="off" placeholder="你今天的任务是？" v-model="newTodo" @keyup.enter="addTodo">
    </header>
    <section class="main">
      <input class="toggle-all" type="checkbox">
      <ul class="todo-list">
        <li class="todo" v-for="item in tasks">
          <div class="view">
            <input class="toggle" type="checkbox">
            <label @dblclick="editTodo">{{ item.task }}</label>
            <button class="destroy" @click="removeTodo(todo)"></button>
            <input class="edit" type="text">
          </div>
        </li>
      </ul>
    </section>
    <footer class="footer">
      <span class="todo-count">
          <strong>{{ remaining }}</strong> 剩余
      </span>
      <ul class="filters">
        <li><a href="#/all">所有</a></li>
        <li><a href="#/active">活动中</a></li>
        <li><a href="#/completed">已完成</a></li>
      </ul>
    </footer>
  </section>
</template>

<script>
export default {
  name: 'list',
  data () {
    return {
      msg: 'Todos-Vue',
      newTodo:'',
      remaining: 10,
      pluralize: 20,
      tasks:[]  
    }
  },
    methods: {
    addTodo: function (e) {
       var newtask = {}
       newtask.task = e.target.value
       this.tasks.push(newtask)
       this.newTodo = ''
    },
    editTodo: function(e){
      console.log(e)
    }
  }
}
</script>

<style scoped>
  @import 'list.css';
</style>