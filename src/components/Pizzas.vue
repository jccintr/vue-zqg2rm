<template>
  <div  class="container">
    <input
      
      class="inputPesquisa"
      placeholder="Encontre a sua pizza"
      type="search"
      @input="pesquisa = $event.target.value"
    />
    
    
   <div class="pai">
    <div v-for="pizza in pizzasFiltrados" v-bind:key="pizza.Nome" class="cartao">
          
              <h4 class="nomeLivro">{{pizza.Nome}}</h4> 
     
    </div>
    </div>

   

</div>

      <p>Criado por Julio Cesar</p>
</template>


<script>


export default {
  name: 'Pizzas',
  

  data() {
    return {
      pizzas: [],
      pesquisa: '',
      
    };
  },

  methods: {
    async getPizzas() {
      try {
        const response = await fetch(
          'https://x8ki-letl-twmt.n7.xano.io/api:xR9a0v67/pizzas'
          
        );
        let responseJson = await response.json();
        this.pizzas = responseJson;
      } catch (error) {
        console.log(error);
      }
    },
  },
  

  computed: {
    pizzasFiltrados() {
    
      return this.pizzas.filter(pizza => pizza.Nome.toUpperCase().includes(this.pesquisa.toUpperCase()));
  
    },
  },

  created() {
    this.getPizzas();
  },
};
</script>

<style scoped>

.container {
  
  justify-content: center;
}

.inputPesquisa {
  width: 80%;
  margin-top: 10px;
  margin-bottom: 10px;
  height: 30px;
  border-radius: 5px;
  padding: 5px;
  
  
}
input:focus { 
    outline: none !important;
    border-color: orange;
  
}

.nomeLivro {
  padding-top: 5px;
  font-weight: bold;
  font-size: 18px;
}
.testamento {
  font-style: italic;
  font-size: 14px;
}
.textoInferior {
  font-size: 12px;
}
.bottomCard {
  display: flex;
  flex-direction: row;
  justify-content: space-around;

}

.pai {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  
}

.cartao {
  flex: 1 1 140px;
  margin:5px;
  border: solid;
  border-radius: 20px;
  background: orange;
  border-width: 2px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.4);
  
}

.cartao:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.4);
}






</style>
