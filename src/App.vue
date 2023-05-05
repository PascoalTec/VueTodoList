<template>
  <div>

    <div>
      WATCH
      <input
        v-model="name"   
        type="text"
      > <br>
      {{ name }}

      <br><br><br>
      <select v-model="pageCount">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option>
      </select> <br>
      {{ pageCount }}
    </div>

    <br><br>

    <div>
      EVENTOS
      <button @click.once="onClick()">
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
        @submit.prevent="onSubmit"
      >
      <input
        type="text"
        @keyup="onKeyUp"
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

</div>
  


</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      name: '',
      pageCount: 5,
      sports: '',
      newsletter: '',
      contract: [],
      styleClass: {'color': 'aqua', 'background-color': 'black', 'font-size': '20px'},
      isHome: false,
      classVar: 'title',
      pClass: ['text', 'text-home']
        }
    },
    watch:{
      name(vl){
        if(vl.length >= 3){
          this.saveUsername()
        }
      }
    },
    methods:{
      saveUsername(){
        console.log(this.name);
      },
      onClick($evt) {
        console.log('click', $evt);
      },
      onMouseOver($evt) {
        console.log('Mouse over', $evt);
      },
      onMouseOut($evt) {
        console.log('mouse out', $evt);
      },
      onSubmit($evt){
        console.log('submit', $evt);
      },
      onKeyUp($evt){
        console.log('onKeyup', $evt)
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px;
}
</style>
