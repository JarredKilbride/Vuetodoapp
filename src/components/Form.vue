<template>
<form @submit.prevent="handleSubmit">
    <h4 v-if="error">Feilds cann't be blank</h4>
    <label>Do date</label>
    <input type="date" v-model="date">
    <label>What is the to do?</label>
    <input type="text" v-model="text">

<div class="submit">
    <button>Add to do</button>
</div>
</form>

</template>

<script>
export default {
    data() {
        return {
            date: '', 
            text:'', 
            error:false
        }
    }, 
    methods: {
              randomId(){
        return Math.floor(Math.random() * 1000)
      },
         handleSubmit() {
             if(this.date && this.text){
             console.log(this.text)
             this.$emit('submited',{date: this.date,text:this.text,id:this.randomId()})
             this.error = false
             this.date = ''
             this.text = ''}
             else {
                 this.error = true
             }
    }
    }

}
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding:40px;
    border-radius: 10px;
}
label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: .6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input,select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}

input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0 ;
    position: relative;
    top: 2px;
}

.pill {
    display: inline-block;
    margin: 20px 10px 0;
    padding: 6px 12px;
    background: #eee;
    border-radius: 20px;
    font-size: 20px;
    letter-spacing: 1px;
    font-weight: bold;
    color: #777;
    cursor: pointer;
}

button {
    background: #DB504A; 
    border: 0;
    padding: 10px 20px;
    margin-top: 20px; 
    color: white;
    border-radius: 20px;
}

.submit {
    text-align: center
}

form h4 {
    color: red;
    text-align: center;
}
</style>