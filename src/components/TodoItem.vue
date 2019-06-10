<template>
    <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
       
        <input type="checkbox" v-on:change="markComplete" class="check-small">
             <p>
                {{todo.title}}
                <button @click="$emit('del-todo', todo.id)" class="delete-button">Delete</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
   
    .todo-item {
        background: #fff;
        padding: 1rem;
        border-bottom: 2px #ccc solid;
        max-width: 25rem;
        margin: 1rem auto;
        border-radius: 12px;
    }

    .is-complete {
        text-decoration: line-through;
    }

    
.delete-button {
  font-size: 16px;
  text-decoration: none;
  background-color: #FFFFFF;
  color: #d94c4c;
  border: 1.5px solid #d94c4c;
  padding: 5px 15px 5px 15px;
  border-radius: 10px;
  box-shadow: 0px 2px #F1F1F1;
  cursor: pointer;
  margin-right: 20px;
  transition: .5s ease;
  float: right;
}

.delete-button:hover {
  background-color: #d94c4c;
  color: #FFFFFF;
}
   .check-small {
    cursor: pointer;
    appearance: none;
    position: relative;
    display: block;
    width: 51px;
    height: 31px;
    border-radius: 15px;
    background-color: #ddd;
    border: none;
    transition: 0.4s ease;
    float: left;
    margin-top: .75rem;
}
.check-small:before {
  content: "";
  z-index: 100;
  display: block;
  width: 47px;
  height: 27px;
  position: absolute;
  right: 2px;
  top: 2px;
  border-radius: 15px;
  background-color: white;
  transition: 0.4s ease;
}
.check-small:after {
  content: "";
  z-index: 200;
  position: absolute;
  left: 2px;
  top: 2px;
  width: 27px;
  height: 27px;
  background-color: white;
  border-radius: 29px;
  box-shadow: 0px 0px 4px rgba(0, 0, 0, .35), 0px 4px 5px rgba(0, 0, 0, .15);
  transition: 0.4s ease;
}
.check-small:hover:after {
  padding-left: 5px;
}
.check-small:focus {
  outline: none;
  box-shadow: 0 0 8px #007aff;
}
.check-small:checked {
  background-color: #4cd964;
}
.check-small:checked:before {
  width: 12px;
  height: 0px;
  top: 15px;
  right: 15px;
}
.check-small:checked:after {
  left: 22px;
}
.check-small:checked:hover:after {
  margin-left: -5px;
}


</style>
