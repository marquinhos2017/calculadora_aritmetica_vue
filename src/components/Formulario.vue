<script setup>
    const props = defineProps(['cadastraTarefa','tarefaTemp','trocarFiltro','editaTarefaTemp']);
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" required @change="props.editaTarefaTemp"
                    class="form-control" type="text" name="" placeholder="Digite primeiro numero" id="">
            </div>
            <div class="col">
                <input :value="props.tarefaTemp" required @change="props.editaTarefaTemp"
                    class="form-control" type="text" name="" placeholder="Digite segundo numero" id="">
            </div>
            <div class="col-md-2">
                <button class="btn btn-primary" type="submit">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control" name="" id="">
                    <option value="todas">Todas tarefas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>