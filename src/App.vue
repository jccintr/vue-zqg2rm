<template>


    <Cabecalho /> 
    <Pizzas /> 
    

  
</template>

<script>
import Cabecalho from './components/Cabecalho.vue';
import Pizzas from './components/Pizzas.vue';




export default {
  name: 'App',
  components: {
   
    Cabecalho,
    Pizzas,
   
    

  },
  data() {
    return {
    
    }
  },
  methods: {

   
  },
  

   created() {
    
      

  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

  </style>