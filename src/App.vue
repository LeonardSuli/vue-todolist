<script>
export default{
  name: 'App',
  data(){
    return {
      newList:{
        text: '',
        done: false
      },
      todoList:[
        {
          text:'Birre',
          done: true
        },
        {
          text:'Salamelle',
          done: true
        },
        {
          text:'Hamburger',
          done: false
        },
        {
          text:'Spiedini',
          done: true
        },
        {
          text:'Pesce',
          done: false
        },
        {
          text:'Melanzane',
          done: false
        },
        {
          text:'Peperoni',
          done: true
        },
        {
          text:'Anguria',
          done: false
        },
        {
          text:'Melone',
          done: true
        },
      ]
    }
  },
  methods:{

    removeList(index){
      console.log('rimuovi', index);
      this.todoList.splice(index, 1)
    },

    addList(){
      console.log(this.newList.text);
      this.todoList.unshift(this.newList);
      this.newList = '';
    }
  }
}
</script>

<template>

  <h1>Grigliata</h1>

  <div>
    <input type="text" v-model="newList.text">
    <button @click="addList()">Aggiungi</button>
  </div>

  <ul v-if="todoList.length > 0">

    <li v-for="(list, index) in todoList">

      <span :style="{textDecoration: list.done ? 'line-through' : ''}">
        {{ list.text }}

        <i @click="removeList(index)" class="fa-regular fa-circle-xmark"></i>

      </span>

    </li>
  </ul>

  <ul v-else="todoList.length === 0">
    <p>Complimenti hai preso tutto. Buona grigliata!!!!</p>
  </ul>

</template>

<style>

</style>
