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
                              <input type="text" size="2" v-model=cantidadProducto[index]>
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
         }
      },
      data: function(){
        return{
            cantidadProducto:[
                0,
                0,
                0
            ]
        }
      },
      methods: {
        aumentar: function(indiceAumentar){
            this.cantidadProducto[indiceAumentar]+=1;
        },
        disminuir: function(indiceDisminuir){
            
            if(this.cantidadProducto[indiceDisminuir]>0 ){
                this.cantidadProducto[indiceDisminuir]-=1;
            } else{
                this.cantidadProducto[indiceDisminuir]=0;
            }
        },

      }
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