<template>
<h3>Current To dos</h3>
<div class="container">
    <div  class="card" v-for="todo in todos">
        <h4>{{todo.text}}</h4>
        <p>Due Date: {{todo.date}} </p>
        <button @click="removeTodo(todo)">Compete Todo</button>
    </div>
  </div>
</template>

<script>

export default {
    props: ['todos'], 
    methods: {
      removeTodo(data) {
        // console.log(data)
        this.$emit('remove',data)
      }
    }
}
</script>

<style>
 .container {
  margin: 1rem;
  padding: 2rem 2rem;
  text-align: center;
     /* max-width: 700px; */
 }
 .card {
  display: inline-block;
  
  padding: 1rem 1rem;
  vertical-align: middle;
  margin: 30px;
}  


 .card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
  background: rgba(237, 237, 237, 0.701);
}

.card button {
  background:#084C61 ;
}

.card button:hover {
  background:#E3B505 ;
}

</style>