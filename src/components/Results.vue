<script setup>
    const props = defineProps(['numero1', 'numero2', 'result'])
</script>

<template>
    <div class="results">
        <footer class="pt-5 pb-1 mt-4 mb-3 bg-info bg-gradient text-center rounded-5">
            <h3>O resultado é:</h3>
            <h1 v-if="props.numero1 && props.numero2 != ''">{{ props.result }}</h1>
            <span v-else-if="props.numero1 || props.numero2 === ''">Você precisa digitar os dois valores</span>
        </footer>
    </div>
</template>


<style scoped>
h1 {
    margin-bottom: 50px;
}
h3 {
    color: aliceblue;
}
</style>