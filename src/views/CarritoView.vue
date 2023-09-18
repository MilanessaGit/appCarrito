<template>
    <h1>{{ title }}</h1>
    <input type="text" v-model="title">
    <hr>
    <table border="1">
        <tr>
            <td>NOMBRE</td>
            <td>PRECIO</td>
            <td>ACTION</td>
        </tr>
        <tr v-for="prod in productos" :key="prod">
            <td>{{ prod.nombre }}</td>
            <td>{{ prod.precio }}</td>
            <td><button type="button" @click="addCarrito()">agregar</button></td>
        </tr>
    </table>

    <hr>
    <table border="1">
        <tr>
            <td>NOMBRE</td>
            <td>PRECIO</td>
            <td>ACTION</td>
        </tr>
        <tr v-for="car in carrito" :key="car">
            <td>{{ car.nombre }}</td>
            <td>{{ car.precio }}</td>
            <td><button type="button" @click="quitar()">quitar</button></td>
        </tr>
    </table>

</template>

<script>
    import { ref } from "vue"
    export default{
        // composicion api
        setup(){
            const title = ref("Mi Carrito de Compras")
            const productos = ref([{nombre: "teclado", precio: 150 },
                                    {nombre: "monitor", precio: 250 }]);
            const carrito = ref([])
            const addCarrito = (prod) => {

            }
                                    
            return { title, productos, addCarrito }
        }
    }
</script>
