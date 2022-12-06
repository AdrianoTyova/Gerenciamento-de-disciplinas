<template>
<div>
    <h1 class="primary--text text-h4 text-center mt-5">Exercícios de Algebra (Método de Tyova)</h1>
    <div class="comp mx-auto mt-5">
        <v-select :items="items" item-value="valor" item-text="nome" v-model="operacao" label="Seleciona o que deseja calcular" solo></v-select>
    </div>

    <MatrizComum :operacao="operacao" />

</div>
</template>

    
    
<script>
import MatrizComum from '../components/matrizes/MatrizComum.vue'
export default {
    components: {
        MatrizComum
    },
    data() {
        return {
            items: [{
                    valor: 1,
                    nome: 'Adição de Matrizes'
                },
                {
                    valor: 2,
                    nome: 'Subtração de Matrizes'
                },
                {
                    valor: 3,
                    nome: 'Multiplicação de Matriz por nº real'
                },
                {
                    valor: 4,
                    nome: 'Metodo de Sarrus (Brevimente)'
                },
                {
                    valor: 5,
                    nome: 'Matriz oposta '
                },
            ],
            operacao: 0,
        }
    },

}
</script>
    
    
<style>
.pai {
    width: 800px;
}

.comp {
    width: 300px;
}

.op3 {
    transform: translateY(50px);
}

@media (max-width: 720px) {
    .pai {
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .sinal {
        margin-top: 10px;
    }

}

input {
    text-align: center;
}
</style>
