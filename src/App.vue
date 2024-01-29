<script>
export default{
  name: 'App',
  data(){
    return {
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
  }
}
</script>

<template>

  <h1>Grigliata</h1>

  <ul>
    <li v-for="list in todoList">

      <span :style="{textDecoration: list.done ? 'line-through' : ''}">
        {{ list.text }}
      </span>

    </li>
  </ul>
  
</template>

<style>

</style>
