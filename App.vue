<template>
   <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent>
          <nb-icon name="arrow-back" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Header</nb-title>
      </nb-body>
      <nb-right>
        <nb-button transparent>
          <nb-icon name="menu" />
        </nb-button>
      </nb-right>
    </nb-header>
    <todo-item
      class="text-container"
      v-for="todo in todos"
      :key="todo.text"
      :item="todo"
    />
  </nb-container>
  
</template>


<script>
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";

// // registering all native-base components to the global scope of the Vue
Vue.use(VueNativeBase);

import TodoItem from './components/TodoItem';
export default {
  name: 'App',
  components: {
    TodoItem, 
  },
  data: function() {
    return {
      message: "Hello World",
      todos: [
        { id: 1, text: "Learn JavaScript" },
        { id: 2, text: "Learn Vue" },
        { id: 3, text: "Build something awesome" }
      ]
    }
  },
  methods: {
    handleBtnPress: function() {
      alert('Btn Press');
    }
  }
}
</script>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
