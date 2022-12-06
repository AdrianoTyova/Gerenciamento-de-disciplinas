<template>
<div>
    <div v-if="operacao">
        <div v-if="operacao === 4">
            <h2 class="primary--text text-h3 text-center mt-5">Brevimente...</h2>
        </div>
        <div v-else>
            <h1 class="primary--text text-h6 text-center" v-for="item in items" :key="item.valor">
                <div v-if="operacao === item.valor">{{ item.nome }}</div>
            </h1>
            <div class="d-flex mx-auto justify-center mt-5">
                <div class="d-flex mx-auto justify-space-between mt-5 pai">
                    <div v-if="operacao !== 5">
                        <v-card width="200px" elevation="5" class="pa-3" v-if="operacao !== 3">
                            <v-row v-for="mat, index1 in matriz01" :key="index1">
                                <v-col cols="4" sm="4" md="4" v-for="mat, index2 in matriz01[index1]" :key="index2">
                                    <v-text-field v-model="matriz01[index1][index2]" label="" type="number"></v-text-field>
                                </v-col>
                            </v-row>
                        </v-card>
                    </div>
                    <v-card width="75px" height="75px" elevation="1" class="pa-3 d-flex justify-center align-center op3" v-if="operacao === 3">
                        <v-text-field v-model="matriz01[0][0]" label="" type="number"></v-text-field>
                    </v-card>
                    <v-card width="50px" elevation="0" class="sinal pa-3 d-flex align-center justify-center">
                        <div class="text-h4" v-if="operacao === 1">
                            +
                        </div>
                        <div class="text-h4" v-if="operacao === 2">
                            -
                        </div>
                        <div class="text-h5" v-if="operacao === 3">
                            X
                        </div>
                    </v-card>
                    <v-card width="200px" elevation="5" class="pa-3">
                        <v-row v-for="m, linha in matriz02" :key="linha">
                            <v-col cols="4" sm="4" md="4" v-for="m, coluna in matriz02[linha]" :key="coluna">
                                <v-text-field v-model="matriz02[linha][coluna]" label="" type="number"></v-text-field>
                            </v-col>
                        </v-row>
                    </v-card>
                    <v-card width="50px" elevation="0" class="sinal pa-3 d-flex align-center justify-center">
                        <div class="text-h4">
                            =
                        </div>
                    </v-card>
                    <v-card width="200px" elevation="5" class="pa-2">
                        <v-row v-for="m, linha in matriz02" :key="linha">
                            <v-col cols="4" sm="4" md="4" v-for="m, coluna in matriz02[linha]" :key="coluna">
                                <div>
                                    {{ resultado(linha, coluna) }}
                                </div>
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
    props: ["operacao"],
    data() {
        return {
            matriz01: [
                ["", "", ""],
                ["", "", ""]
            ],
            matriz02: [
                ["", "", ""],
                ["", "", ""]
            ]
        }
    },
    
    methods: {
        resultado(index1, index2) {
            // Verificar se os valores estão preenchidos

            if (this.matriz02[index1][index2] != "") {
                // Matriz Oposta
                if (this.operacao === 5) {
                    var novo = parseInt(parseInt(this.matriz02[index1][index2])) * (-1)
                    return novo
                }
                    // Multiplicação de um Matriz com um número real
                if (this.operacao === 3) {
                    var novo = parseInt(parseInt(this.matriz01[0][0]) * parseInt(this.matriz02[index1][index2]))
                    return novo
                }
            }
            if (this.matriz01[index1][index2] === "" || this.matriz02[index1][index2] === "") {
                var novo = ""
                return ""
            }
         
            switch (this.operacao) {

                // Adição de Matrizes
                case 1:
                    var novo = parseInt(parseInt(this.matriz01[index1][index2]) + parseInt(parseInt(this.matriz02[index1][index2])))
                    break

                    // Subtração de Matrizes
                case 2:
                    var novo = parseInt(parseInt(this.matriz01[index1][index2]) - parseInt(parseInt(this.matriz02[index1][index2])))
                    break

                    // Sem nehuma opção
                default:
                    var novo = ""
                    break
            }

            // const novoVa = this.matrizR.map(u => [...u, 2 = 3])
            // this.matrizR[index1][index2] = 5
            return novo
        }
    },

}
</script>
