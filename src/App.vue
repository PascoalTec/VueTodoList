<template>
  <div>

    <div>
      <button v-on:click="onClick()">
              Enviar
            </button>
    </div>

    <br>

    <div 
    @mouseover="onMouseOver()"
    @mouseout="onMouseOut()"
    >
      Mouse Over
    </div>

    <br><br>

    <div>

      <form 
        action="https:google.com"
        @submit="onSubmit"
      >
        <button type="submit">
          Submit
      </button>

      </form>

    </div>

    <div><br>
      Two-way data binding
      v-model -> formulários
    </div>

    <br>

    <div>
      <label>Nome</label><br>
    <input
        v-model="name"
        type="text"    
    > <br>
        {{ name }}

      <br>

      <div>
        <label>Sports</label><br>
        <select v-model="sports">
          <option value="">Escolha</option>
          <option value="futebol">Futebol</option>
          <option value="Skate">Skate</option>
          <option value="Tenis">Tenis</option>
        </select> <br>
        {{ sports }}
      </div>

      <br><br>
      <div>
        <label>Newsletter</label><br>
        <input
          v-model="newsletter"
          type="radio"  
          value="Sim"
        >Sim
        <input
          v-model="newsletter"
          type="radio"  
          value="Não"
        >Não
        <br>
        {{ newsletter }}

      </div>


      <div>
        <label>Contrato</label> <br>
        <input
            v-model="contract"
            type="checkbox"
            value ="Sim"
        > Aceita nossos termos <br>
        <input
            v-model="contract"
            type="checkbox"
            value="Não"
        > Não aceita os termos ?
        <br>
        {{ contract }}

      </div>



  </div>
    <h1 :class="{classVar: true, 'title-home': isHome}"> <br>
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
  


</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      name: '',
      sports: '',
      newsletter: '',
      contract: [],
      styleClass: {'color': 'aqua', 'background-color': 'black', 'font-size': '20px'},
      isHome: false,
      classVar: 'title',
      pClass: ['text', 'text-home']
        }
    },
    methods:{
      onClick() {
        console.log('click');
      },
      onMouseOver() {
        console.log('Mouse over');
      },
      onMouseOut() {
        console.log('mouse out');
      },
      onSubmit(){
        console.log('submit');
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
