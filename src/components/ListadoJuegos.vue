<template>
    <div class="container">
        <h1 class="title">Tienda 32 bites</h1>
        <h3 class="subtitle">Listado de Juegos</h3>
        <table class="table-juegos">
            <thead>
                <tr>
                    <th>Código</th>
                    <th>Nombre</th>
                    <th>Stock</th>
                    <th>Precio</th>
                    <th>Color</th>
                    <th>Acciones</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="juego in juegos" :key="juego.codigo">
                    <td>{{ juego.codigo }}</td>
                    <td>{{ juego.nombre }}</td>
                    <td>{{ juego.stock }}</td>
                    <td>{{ juego.precio }}</td>
                    <td>{{ juego.color }}</td>
                    <td><button @click="incrementarStock(juego.codigo)">+</button>
                        <button @click="disminuirStock(juego.codigo)">  - </button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import { mapState, mapActions } from 'vuex';

export default {
    computed: {
        ...mapState(['juegos']),
    },
    methods: {
        ...mapActions(['incrementarStock', 'disminuirStock']),
    },
}
</script>

<style scoped>

.container {
    margin: 0 auto;
    width: 80%;
    padding: 20px;
    margin-bottom: 20px;
    text-align: center;
    background-color: #FFFDB5;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.title {
    text-align: center;
    margin-bottom: 20px;
    color: #2E073F
}
.subtitle {
    font-weight: bold;
    text-align: center;
    margin-bottom: 20px;
    text-decoration: underline;
    color:#232020;
}

.table-juegos {
    width: 70%;
    border: 3px solid #624E88;
    margin: 0 auto;
    margin-bottom: 20px;
    color:#232020
}

.table-juegos th,
.table-juegos td {
    border: 1px solid #8967B3;
    padding: 8px;
    text-align: center;
    background: #FFF5E4;
}

button {
    background-color: #4c70af;
    color: white; 
    padding: 5px 10px;
    border: none; 
    border-radius: 25px;
    cursor: pointer;
    font-size: 16px; 
    margin-right: 5px; 
}
</style>
