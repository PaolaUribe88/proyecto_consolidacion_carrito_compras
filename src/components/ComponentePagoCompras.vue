<template>
    <div id="ComponentePagoCompras">
        <p>RESUMEN COMPRA</p>
        <hr>
        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <p>{{ cantidadDeItem }} articulos</p>
                </div>
                <div class="col-md-6">
                    <p>${{ calcularTotal }}</p>
                </div>
            </div>
        </div>
        <hr>
        <label for="envios">Envios:</label>

            <select name="envios" v-on:change="costoEnvio" id="envios">
            <option value="5000">Envio Express 5.000 </option>
            <option value="3000">Envio Normal 3.000</option>
            <option value="10000">Envio Overnight 10.000</option>
            </select>

            <hr>
            <label for="descuentos">Codigo de Descuentos </label>
            <input type="text" id="descuentos" placeholder="ingresa tu codigo" v-model="codigoDescuento">
            <br>
            {{ evaluarCodigo }}
            <hr>
            <div class="container">
                <div class="row">
                    <div class="col-md-6">
                        <p>PRECIO TOTAL</p>
                    </div>
                    <div class="col-md-6">
                        <p>{{ calcularCostoFinal }}</p>
                    </div>
                </div>

            </div>
            <button class="btn btn-danger" v-on:click="aprobar" id="botoncito">Realizar Compra</button>
            
            
            </div>
</template>
<script>
 export default{
    name:'ComponentePagoCompras',
    props:{
        cantProducDos: {
            type: Array,
            required: true,
        },
        pagoTotal: {
            type: Array,
            required: true,
        }
    },
    data: function(){
        return {
            pagoEnvio: 5000,
            codigoDescuento: '',
            desc: 0,
            costoFinal: 0,
            subTotal: 0,
            contadorClicks: 0,
        }
    },
    methods:{
        costoEnvio: function() {
            this.pagoEnvio = document.getElementById('envios').value;
        },

        aprobar: function() {
            this.contadorClicks++;
            if (this.contadorClicks == 1) {
                let boton = document.getElementById('botoncito');
                boton.style.backgroundColor = 'orange';
                boton.style.color= 'white';
                boton.innerText= '¿Estas seguro?';
            } else if (this.contadorClicks == 2) {
                let boton = document.getElementById('botoncito');
                boton.style.backgroundColor = 'blue';
                boton.style.color= 'white';
                boton.innerText= '¡OK!';
                this.contadorClicks = 0;
            } 
        }
    },
    computed: {
        cantidadDeItem: function() {
            let total = this.cantProducDos.reduce((accumulator, currentValue) =>{ 
                return accumulator + currentValue;
            },0);
            return total;
        },

        calcularTotal: function() {
            this.subTotal = this.pagoTotal.reduce((accumulator, currentValue) =>{ 
                return accumulator + currentValue;
            },0);
            return this.subTotal;
        },

        evaluarCodigo: function() {
            if (this.codigoDescuento == 'JQUERY2222') {
                let laCaja = document.getElementById('descuentos');
                laCaja.style.backgroundColor = 'green';
                this.desc = 20000;
                return 'CODIGO ACEPTADO';
            }
        },

        calcularCostoFinal: function() {
            this.costoFinal = this.subTotal + this.pagoEnvio - this.desc;
            return this.costoFinal;
        }
    }
 }
</script>
<style scoped>
#ComponentePagoCompras{
    background-color: aquamarine;
}
</style>