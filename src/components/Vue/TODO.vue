<script setup>

    import { ref } from 'vue';
    let tasks = ref([])
    let inputTask = ref('')

    function addTask() {
        if (inputTask.value.length != 0) {
            tasks.value.push(inputTask.value)
        }
        inputTask.value = ''
    }

</script>

<template>
    <section class="py-8 px-10 max-w-96 bg-slate-300 rounded shadow-sm mx-auto mt-10">
        <h1 class="text-center text-lg">Lista de tareas</h1>
        <div class="mt-4 mb-2">
            <input v-model="inputTask" class="px-2 w-4/5 outline-none">
            <button @click="addTask" class="w-1/5 bg-green-600 text-white font-bold text-center">+</button>
        </div>

        <div v-for="(homework, index) in tasks" class="bg-white/60 px-2">Tarea #{{ index+1 }} - {{homework}}</div>
    </section>
</template>