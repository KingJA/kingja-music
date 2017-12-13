<template>
  <div id="app">
    <h1>{{msg}}</h1>

    <span><input type="text" v-model="newTodo"><button @click="addTodo()">添加</button></span>
    <ul v-for="item in todos">
      <li><span>{{item.action}}</span><input type="checkbox" v-bind:checked="item.finished"></li>

    </ul>


  </div>
</template>

<script>
  export default {
    data() {
      return {
        msg: 'this is a todo list.',
        newTodo: '',
        todos: [{action: 'shopping', finished: false},
          {action: 'go sproting', finished: true},
          {action: 'play basketball', finished: false}
        ]
      }
    },
    methods: {
      addTodo: function () {
        this.todos.push({action: this.newTodo, finished: false})
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
