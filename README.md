# app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).





## Diretivas vue.js
```
v-show = "isso for igual aquilo, 1 === 1"
v-if = "se for verdadeiro, ele mostra  se for falso (nao mostra)"
v-else-if
v-else
```

## v-for
```
Estrutura: obj in array
           {{obj.name}}
```
## testes com v-else-if
```
  <div v-if="acessLevel === 'admin'">Usuário Admin</div>
  <div v-else-if="acessLevel === 'marketing'">Usuário Marketing</div>
  <div v-else>Usuário normal</div>
```

## v-bind
```
Da uma instrução para dizer que este atributo é dinamico
v-bind:<nome da propriedade>=""

pode ser simplificado, ao invés de usar (v-bind), pode usar somente o :, que ele reconhecerá
```

## data
```
data é uma função vai retornar um objeto e tudo que declarar dentro desse objeto, é chamado de objeto reativo (variaveis reativas)
```

## objeto
```
Podemos passar um objeto, as keys do objeto são as classes e o valor do objeto é oque determina é se vai ser aplicado ou não, também podemos passar uma array e dentro dele um objeto

Ex:
    <p :class="['text', {'text-home': isHome}]">
      Lorem ipsum dolor sit amet, etc
    </p>


    esse é uma classe normal
    styleClass: {'color': 'aqua', 'background-color': 'black'}
    
    mas também podemos botar como camelCase
    styleClass: {'color': 'aqua', backgroundColor: 'black'}
```

## Two-way data binding
```
v-model -> formulários

    <div>
      Two-way data binding
    </div>

    <input
        type="text"
        value="Jon Snow"

    >
```