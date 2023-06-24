<template>


  <div id="appVue">
    <div id="ContenedorPadre" class="container">
      <div class="row">
        <div class="col-md-8">
          <ComponenteCarroCompras
          v-bind:productos="datosPoleras"/>
        </div>
        <div class="col-md-4">
          <ComponentePagoCompras/>
        </div>

      </div>
    </div>

  </div>
 
</template>

<script>

import ComponenteCarroCompras from './components/ComponenteCarroCompras.vue';
import ComponentePagoCompras from './components/ComponentePagoCompras.vue';
export default {
  name: 'App',
  components: {
    ComponenteCarroCompras,
    ComponentePagoCompras
},
data: function(){
  return{
    datosPoleras:[
      {
        imagenPolera:'https://img.ltwebstatic.com/images3_pi/2021/07/14/1626253120804ef2570850c1535ccf0a3109685e91_thumbnail_600x.jpg',
        tituloPolera:'Polera',
        descripcionPolera:'Color Burdeo',
        costoPolera:'44000',

      },
      {
        imagenPolera:'https://http2.mlstatic.com/D_NQ_NP_728241-MLC48760900622_012022-O.webp',
        tituloPolera:'Polera',
        descripcionPolera:'Color Gris',
        costoPolera:'40000',
      },
      {
        imagenPolera:'https://http2.mlstatic.com/D_NQ_NP_2X_842564-MLC54004192531_022023-F.webp',
        tituloPolera:'Polera',
        descripcionPolera:'Color Negro',
        costoPolera:'45000',
      },
    ],
  }
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
