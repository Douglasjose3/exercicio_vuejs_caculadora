<script setup>
    const props = defineProps(['numero1', 'operacao', 'numero2'])
</script>

<template>
    <div class="container">
        <form class="operation">
            <div class="row bg-secondary bg-gradient p-5 rounded-5">
                <div class="col-md-4">
                    <input @keyup="props.numero1" class="form-control" type="number"
                        placeholder="Digite o primeiro valor" required>
                </div>

                <div class="col-md-4">
                    <select @change="props.operacao" class="form-select input-group">
                        <option>Escolha a Função Aritmética</option>
                        <option value="somar">Somar</option>
                        <option value="subtrair">Subtrair</option>
                        <option value="multiplicar">Multiplicar</option>
                        <option value="dividir">Dividir</option>
                    </select>
                </div>

                <div class="col-md-4">
                    <input @keyup="props.numero2" class="form-control" type="number"
                        placeholder="Digite o segundo valor" required>
                </div>
            </div>
        </form>
    </div>
</template>


<style scoped>
input {
    background-color: #cacfd4;
    color: rgb(0, 0, 0);
}
</style>