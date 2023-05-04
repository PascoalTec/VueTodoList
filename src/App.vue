<template>
  <div>

    <div>
      Two-way data binding
    </div>
    
    <br>

    <input
        v-model="name"
        type="text"

    >

    <h1 :class="{classVar: true, 'title-home': isHome}">
      Curso Vue 3
    </h1>

    <p :class="pClass">
      Lorem ipsum dolor sit amet, etc
    </p>

    <p :style="styleClass">
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. 
    </p>

    <div v-for="(obj, index) in todos"
         :key="obj.id"
         class="todos-item"
    >
    <img
        :src="obj.imgSrc"
    >
     {{ index }} - {{ obj.title }}
    </div>

</div>
  

  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      name: '',
      styleClass: {'color': 'aqua', 'background-color': 'black', 'font-size': '20px'},
      isHome: false,
      classVar: 'title',
      pClass: ['text', 'text-home'],
      todos: [
  {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false,
    "imgSrc":'https://via.placeholder.com/150'
  },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": false,
    "imgSrc":'https://via.placeholder.com/150'
  },
  {
    "userId": 1,
    "id": 3,
    "title": "fugiat veniam minus",
    "completed": false
  },
  {
    "userId": 1,
    "id": 4,
    "title": "et porro tempora",
    "completed": true
  },
  {
    "userId": 1,
    "id": 5,
    "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
    "completed": false
  }
]
      }
    }
  }
</script>

<style>
.title{
  font-size: 20px;
  color: blue;
}
.title-home{
  font-size: 40px;
  color: green;
}
.text{
  color: orange;
}
.text-home{
  color: #42b983
}
.todos-item{
  background-color: #000;
  margin: 0 0 0 0;
  padding:3px;
  color: #fff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px;
}
</style>
