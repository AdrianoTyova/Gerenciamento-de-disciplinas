<template>
<div>
    <h1 class="primary--text text-h4 text-center mt-5">Exercícios de Algebra (Método de Tyova)</h1>
    <div class="comp mx-auto mt-5">
        <v-select :items="items" item-value="valor" item-text="nome" v-model="operacao" label="Seleciona o que deseja calcular" solo></v-select>
    </div>
    <div v-if="operacao">
        <div v-if="operacao === 4">
            <h2 class="primary--text text-h3 text-center mt-5">Brevimente...</h2>
        </div>
        <div v-else>
            <h1 class="primary--text text-h6 text-center" v-if="operacao === 1">Adição de Matrizes</h1>
            <h1 class="primary--text text-h6 text-center" v-if="operacao === 2">Subtração de Matrizes</h1>

            <div class="d-flex mx-auto justify-center mt-5">
                <div class="d-flex mx-auto justify-space-between mt-5 pai">
                    <v-card width="200px" elevation="5" class="pa-3">
                        <v-row>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n11" label="" type="number"></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n12" label="" type="number"></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n13" label="" type="number"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n21" label="" type="number"></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n22" label="" type="number"></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz2.n23" label="" type="number"></v-text-field>
                            </v-col>
                        </v-row>
                    </v-card>
                    <v-card width="50px" elevation="0" class="sinal pa-3 d-flex align-center justify-center">
                        <div class="text-h4">
                            =
                        </div>
                    </v-card>
                    <v-card width="200px" elevation="5" class="pa-3">
                        <v-row>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N11" label="" type="number" disabled></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N12" label="" type="number" disabled></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N13" label="" type="number" disabled></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N21" label="" type="number" disabled></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N22" label="" type="number" disabled></v-text-field>
                            </v-col>
                            <v-col cols="4" sm="4" md="4">
                                <v-text-field v-model="matriz3N23" label="" type="number" disabled></v-text-field>
                            </v-col>
                        </v-row>
                    </v-card>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
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
                    nome: 'Multiplicação de Matriz por nº real (Brevimente)'
                },
                {
                    valor: 4,
                    nome: 'Metodo de Sarrus (Brevimente)'
                },
                {
                    valor: 5,
                    nome: 'Matriz oposta'
                },
            ],
            operacao: 0,

            matriz2: {
                n11: "",
                n12: "",
                n13: "",
                n21: "",
                n22: "",
                n23: "",
            },
        }
    },
    computed: {
        matriz3N11() {
            if (this.matriz2.n11 === "") {
                var novo = ""
            } else {
                if (this.operacao === 5) {
                    var novo = (parseInt(this.matriz2.n11)) * (-1)
                }
            }
            return novo
        },
        matriz3N12() {
            if (this.matriz2.n12 === "") {
                var novo = ""
            } else {
                if (this.operacao === 5) {
                    var novo = parseInt(parseInt(this.matriz2.n12)) * (-1)
                }
            }
            return novo
        },
        matriz3N13() {
            if (tthis.matriz2.n13 === "") {
                var novo = ""
            } else {
                
                    if (this.operacao === 5) {
                        var novo = parseInt(parseInt(this.matriz2.n13)) * (-1)

                }

            }
            return novo
        },
        matriz3N21() {
            if (this.matriz2.n21 === "") {
                var novo = ""
            } else {
                
                    if (this.operacao === 5) {
                        var novo = parseInt(parseInt(this.matriz2.n21)) * (-1)

                    
                }

            }
            return novo
        },
        matriz3N22() {
            if (this.matriz2.n22 === "") {
                var novo = ""
            } else {
               
                    if (this.operacao === 5) {
                        var novo = parseInt(parseInt(this.matriz2.n22)) * (-1)

                    
                }

            }
            return novo
        },
        matriz3N23() {
            if (this.matriz2.n23 === "") {
                var novo = ""
            } else {
               
                    if (this.operacao === 5) {
                        var novo = parseInt(parseInt(this.matriz2.n23)) * (-1)

                    }
                

            }
            return novo
        }
    }

}
</script>

<style>
.pai {
    width: 500px;
}

.comp {
    width: 300px;
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
</style>
