<template>
   <nb-container>
    <nb-header>
      <nb-left>
        <!-- <nb-button transparent>
          <nb-icon name="arrow-back" />
          <nb-text>Back</nb-text>
        </nb-button> -->
      </nb-left>
      <nb-body>
        <nb-title>COVID-Guide</nb-title>
      </nb-body>
      <nb-right/>
    </nb-header>
    <Form/>
  </nb-container>
  
</template>


<script>
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";

// // registering all native-base components to the global scope of the Vue
Vue.use(VueNativeBase);

import TodoItem from './components/TodoItem';
import Form from './components/Form';
export default {
  name: 'App',
  components: {
    TodoItem, 
    Form
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
