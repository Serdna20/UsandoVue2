<script setup>
    import { ref } from 'vue'
    let msg = ref('Soy un tooltip')
    let checked = ref(false)
    let data = ["hola", "mundo", "bonito"]



    let filtered = data.filter((word) => word.includes('o'))

    // COMENTARIO PICKED INDEX
    // let pickedIndex = ref(0)
</script>

<!-- This isn't a div -->
<!-- Use : para llamar a una variable del script setup -->
<template>
    <!-- COMENTARIO #PICKED INDEX -->
    <!-- <input type="number" v-model="pickedIndex"> -->
    <input 
    id="hola" 
    type="text" 
    class="border"
    :class="{'border-red-500':checked}"
    v-model="msg">
    <div :title="msg">
        {{ msg }}
    </div>
    <label for="check">Seleccionado {{checked}}</label>
    <input type="checkbox" v-model="checked">
    <ul>
        <li v-for="(text, index) in data" :key="index" >{{index}}{{ text }}</li>
        <li v-for="(text, index) in filtered" :key="index">{{ text }}</li>
        <!-- COMENTARIO #PICKED INDEX -->
        <!-- <h1>{{ data[pickedIndex] }}</h1> -->
    </ul>
</template>