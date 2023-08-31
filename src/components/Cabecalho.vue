<script setup>
    const props = defineProps(['enderecodaImagem'])
</script>
<template>
    <header class="p-5 mb-4 mt-4 rounded-3">
        <div id="cabecalho">
            <h1>Minha Calculadora</h1>
            <img :src="props.enderecodaImagem" alt="">
        </div>
        <p>
            Escolha a Operação e Bons Calculos...
        </p>
    </header>
</template>
<style scoped>
img {
    max-width: 75px;
}

#cabecalho {
display: flex;
align-items: center;
justify-content: space-between;
}
</style>