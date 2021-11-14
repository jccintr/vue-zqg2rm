<template>
<div class="toolbar">
        <h1 class="titulo">Bíblia Sagrada</h1>
      </div>
   
  </div>
 
</template>

<script>
export default {
  name: 'Cabecalho',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.toolbar {
  
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
  display: flex;
  align-items: center;
  background-color: #329845;
  
  font-weight: 600;
}
.titulo {
  font-style: italic;
  margin: 20px;
}
</style>
