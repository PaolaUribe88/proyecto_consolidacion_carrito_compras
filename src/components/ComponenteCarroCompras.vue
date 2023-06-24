<template>
    <div id="ComponenteCarroCompras">
        <p>Este es el Carro Compras</p>
        <div class="card mb-3" v-for="(producto, index) in productos" v-bind:key="index">
            <div class="row g-0">
                <div class="col-md-4">
                    <div class="container">
                        <div class="row">
                            <div class="col-md-6">
                                <img v-bind:src="producto.imagenPolera" class="img-fluid rounded-start imagenes" alt="...">
                            </div>
                      
                            <div class="col-md-6">
                                <p>{{ producto.tituloPolera }}</p>
                                <p>{{ producto.descripcionPolera }}</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="container">
                        <div class="row">
                            <div class="col-md-4">
                                <button v-on:click.prevent="disminuir(index)">-</button>
                            </div>
                            <div class="col-md-4">
                              <input type="text" size="2" v-model=cantProduc[index]>
                            </div>
                            <div class="col-md-4">
                                <button v-on:click.prevent="aumentar(index)">+</button>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                <p>{{ producto.costoPolera }}</p>
                </div>
            </div>
        </div>
   

    </div>
</template>
<script>
export default{
      name: 'ComponenteCarroCompras',
      props:{
         productos:{
            type: Array,
            required: true,
         },
         cantProduc:{
            type: Array,
            required: true
         }
      },
      data: function(){
        return{
        }
      },
      methods: {
        aumentar: function(indiceAumentar){
            this.$emit('add',indiceAumentar);
        },
        disminuir: function(indiceDisminuir){
            this.$emit('reduce',indiceDisminuir);
        },
      },

}
  
</script>
<style scoped>
#ComponenteCarroCompras{
    background-color: blueviolet;
}
.imagenes{
    width: 50%;
}
</style>