  <template>
  <div id="app">
    <Header @createTodo="createTodo" />
    <Todos :todos="todos" />
  </div>
</template>

<script>

import Header from './components/Header';
import Todos from './components/Todos';

let todos = [
  {
    id: 1,
    name: 'Do stuff',
    done: false
  },
  {
    id: 2,
    name: 'Work!',
    done: false
  },
  {
    id: 3,
    name: 'Study',
    done: false
  },
  {
    id: 4,
    name: 'Relax',
    done: false
  },      
];

export default {
  name: 'app',
  components: {
    Header,
    Todos
  },
  data: function() {
    return {
      todos: todos
    }
  },
  methods: {
    createTodo(todo) {

      let todoObj = {
        id: this.todos.length + 1,
        name: todo,
        done: false
      }
      
      this.todos.push(todoObj);
    }
  }
}
</script>

<style lang="scss" >
  body {
    font-family: Arial, Helvetica, sans-serif;
      margin: 0;
      padding: 0;
      background: #F3F3F3;

      #app {
        padding: 15px;
      }
  }
</style>