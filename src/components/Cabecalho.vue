<script setup>
const props = defineProps(['EnderecoDaImagem']);
</script>

<template>
    <header class="p-5 mb-4 mt-4 rounded-3">
            <div id="cabecalho">
                <h1>Minha Calculadora</h1>
                <img :src="props.EnderecoDaImagem" alt="">
            </div>
            <p>
                Escolha a Operação e Bons Calculos...
            </p>
        </header>
</template>

<style scoped>
header {
    background-color: rgb(10, 186, 218);
}
img {
    max-width: 100px;
}
#cabecalho {
display: flex;
align-items: center;
justify-content: space-between;
}
</style>