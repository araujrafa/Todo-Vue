<template>
  <div>
    <p>Tarefas completadas: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Tarefas pendetes: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <todo
      v-for="(todo, index) in todos"
      v-bind:todo="todo"
      :key="index">
    </todo>
  </div>
</template>

<script type="text/javascript">

import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  }
}

</script>
<style>

</style>
