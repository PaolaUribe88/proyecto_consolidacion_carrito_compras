<template>
    <div id="ComponentePagoCompras">
        <p>RESUMEN COMPRA</p>
        <hr>
        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <p>Cantidad</p>
                </div>
                <div class="col-md-6">
                    <p>Valor</p>
                </div>
            </div>
        </div>
        <hr>
        <label for="envios">Envios:</label>

            <select name="envios" id="envios">
            <option value="express">Envio Express 5.000 </option>
            <option value="normal">Envio Normal 3.000</option>
            <option value="overnight">Envio Overnight 10.000</option>
            
            </select>
            <hr>
            <label for="descuentos">Codigo de Descuentos </label>
            <input type="text" id="descuentos" placeholder="ingresa tu codigo">
            <hr>
            <div class="container">
                <div class="row">
                    <div class="col-md-6">
                        <p>PRECIO TOTAL</p>
                    </div>
                    <div class="col-md-6">
                        <p>PRECIO</p>
                    </div>
                </div>

            </div>
            <button class="btn btn-danger">Realizar Compra</button>
            
            
            </div>
</template>
<script>
 export default{
    name:'ComponentePagoCompras',
    data: function(){

    },
    methods:{

    }
 }
</script>
<style scoped>
#ComponentePagoCompras{
    background-color: aquamarine;
}
</style>