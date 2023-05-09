<template>

<div class="titulo"> EMIT </div> <br>
  <div>
    <BaseAlert
    v-if="showAlert"
    :variant="variant"
    @close="onClose"
    >
    {{ text }}
    </BaseAlert>
  </div>




<div class="titulo"> PROPS </div> <br>
  <div>
    <BaseAlert
    :variant="variant"
    >
    {{ text }}
    </BaseAlert>
  </div>


  <br><br>

    <div>
        <BaseCard />

    </div><br>

  <div class="titulo">SLOT</div><br>
  <div>
    <TheHeader>
      <template v-slot:title>
          Home
    </template>

      <template v-slot:description>
        <p>dasdsasdasd</p>
      </template>

    </TheHeader>
  </div>

  <br><br>

  <div>
    <div class="titulo">HOOKS</div><br>
    <div>
      <TheHeader v-if="showHeader"/>
      <h1>Hello World</h1> <br>
      <input v-model="name" type="text"> <br><br>
      <button @click="showHeader = !showHeader">
        Ativar e desativar header
      </button> <br><br>
      {{ name }}
</div>

    <br><br>

    <div class="titulo">WATCH</div><br>

    <div>

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

    <div class="titulo">EVENTOS</div><br>
    <div>

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
import TheHeader from './components/TheHeader.vue';
import BaseCard from './components/BaseCard.vue';
import BaseAlert from './components/BaseAlert.vue'



export default {
    name: "App",
    components: { TheHeader, BaseCard, BaseAlert},
    data() {
        return {
            name: "Jon Snow",
            showHeader: 'true',
            pageCount: 5,
            sports: "",
            newsletter: "",
            contract: [],
            styleClass: { "color": "aqua", "background-color": "black", "font-size": "20px" },
            isHome: false,
            classVar: "title",
            pClass: ["text", "text-home"],
            variant: 'success',
            text: 'Seu formulário foi enviado',
            showAlert: true
        };
    },
    beforeUpdate() {
      console.log('beforeUpdate');
    },
    updated(){
      console.log('updated');
    },
    // beforeCreate() {
    //     console.log("beforeCreate");
    //     console.log("Estado: ", this.name);
    //     console.log("DOM: ", this.$el);
    // },
    // created() {
    //     console.log("created");
    //     console.log("Estado: ", this.name);
    //     console.log("DOM: ", this.$el);
    // },
    // beforeMount() {
    //     console.log("beforeMount");
    //     console.log("Estado: ", this.name);
    //     console.log("DOM: ", this.$el);
    // },
    // mounted() {
    //     console.log("mounted");
    //     console.log("Estado: ", this.name);
    //     console.log("DOM: ", this.$el);
    // },
    // beforeUnmount() {
    //     console.log("beforeUnmount");
    // },
    // unmounted() {
    //     console.log("unmounted");
    // },
    watch: {
        name(vl) {
            if (vl.length >= 3) {
                this.saveUsername();
            }
        }
    },
    methods: {
        onClose(){
          this.showAlert = false
            console.log('on close');
        },
        saveUsername() {
            console.log(this.name);
        },
        onClick($evt) {
            console.log("click", $evt);
        },
        onMouseOver($evt) {
            console.log("Mouse over", $evt);
        },
        onMouseOut($evt) {
            console.log("mouse out", $evt);
        },
        onSubmit($evt) {
            console.log("submit", $evt);
        },
        onKeyUp($evt) {
            console.log("onKeyup", $evt);
        }
    },
}
</script>

<style>
.header{
  background: #000;
  color: #fff;
}
.titulo{
  font-size: 20px;
  color: red;
  font: bold;
}
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
