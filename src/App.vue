<template>
<div>
<h1>To Do App</h1>
<Form @submited="addData"/>
<Card :todos="todos" @remove="removeTodo"/>
</div>
</template>

<script>
import Form from './components/Form'
import Card from './components/Card.vue'
export default {
  name: 'App',
  components: { Form,Card
  }, 

    data() {
    return {
      todos:[
        {date:'11/6/2021', 
        text:'this is some text',
          id:1}, 
      ]
    }
  }, 
  methods: {
    addData(d) {
      this.todos.push(d)
      console.log(this.todos)
    }, 
    removeTodo(data) {
        this.todos = this.todos.filter((item) => {
            return data.id !== item.id
        })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
