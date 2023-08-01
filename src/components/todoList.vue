<template>
    <input type="text" id="todoText" v-model="todoText">
        <button id="addBtn" @click="addTodo">Ekle</button>
        <button id="deleteBtn" @click="deleteTodo">Sil</button>
        <ul type="none" id="todoList">
          <li v-for="todo in todoList" :key="todo"> {{ todo }} </li>
        </ul>
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
      },
    }
    </script>
    
    <style>
    
    
    
    </style>