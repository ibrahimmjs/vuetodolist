<template>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Quicksand&display=swap" rel="stylesheet">

<div class="mainDiv">
    <input type="text" id="todoText" placeholder="Eklemek istediğiniz ürünü girin" v-model="todoText">
    <button id="addBtn" @click="addTodo">Ekle</button>
    <button id="deleteBtn" @click="deleteTodo">Sil</button>
    <ul type="none" id="todoList">
      <li @click="liClick" v-for="todo in todoList" :key="todo"> {{ todo }} </li>
    </ul>
  </div>
    </template>
    
    <script>    
    export default {
      data() {
        return {
              todoText : null,
              todoList : [],
        };
      },
      methods: {
        addTodo(){
          this.todoList.push(this.todoText)
          this.todoText = ""
        },
        deleteTodo(){
          this.todoList.pop(this.todoText)
        },
        liClick(){
        let todoSelect = document.querySelector("#todoList")
        if(todoSelect.classList.contains("lineThrough")){
          todoSelect.classList.remove("lineThrough")
          return;
        }
        todoSelect.classList.add("lineThrough")
      }
      },
    }
    </script>