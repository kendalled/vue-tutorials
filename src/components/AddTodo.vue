<template>
    <div id="addTodo">
        <form @submit="addTodo" v-if="showAddTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Item..." class="txtinput">
            <input type="submit" value="Submit" class="submit-button2">
        </form>
        
        <button v-if="!showAddTodo" v-on:click="show" class="submit-button">New Item</button>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    
    data() {
        return {
            showAddTodo: false,
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: 4,
                title: this.title,
                completed: false
            }
            // Send up to parent with emit
            this.$emit('add-todo', newTodo);

            this.title = '';
            this.showAddTodo = false;
        },
        show () {
            this.showAddTodo = !this.showAddTodo;
        }
    }
}
</script>

<style scoped>

.txtinput
{
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  font: 15px/1 'Open Sans', sans-serif;
  color: #333;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-right: 2rem;
  background-color: #ddd;
  border: none;
  padding: 10px 11px 11px 11px;
  border-radius: 3px;
  box-shadow: none;
  outline: none;
  margin: 0;
  box-sizing: border-box; 
}
.submit-button {
  font-size: 16px;
  text-decoration: none;
  background-color: #FFFFFF;
  color: #4c56d9;
  border: 1.5px solid #4c56d9;
  padding: 5px 15px 5px 15px;
  border-radius: 10px;
  box-shadow: 0px 2px #F1F1F1;
  cursor: pointer;
  margin-right: 1.5rem;
  transition: .5s ease;
}
.submit-button2 {
  font-size: 16px;
  text-decoration: none;
  background-color: #FFFFFF;
  color: #4c56d9;
  border: 1.5px solid #4c56d9;
  padding: 5px 15px 5px 15px;
  border-radius: 10px;
  box-shadow: 0px 2px #F1F1F1;
  cursor: pointer;
  margin-left: 2rem;
  transition: .5s ease;
}

.submit-button:hover, .submit-button2:hover {
  background-color: #4c56d9;
  color: #FFFFFF;
}
   
</style>

