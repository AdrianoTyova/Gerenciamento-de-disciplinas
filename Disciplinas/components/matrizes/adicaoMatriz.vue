<template>
<div>

    <v-card width="200px" elevation="5" class="pa-3">
        <v-row>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N11" label=""></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N12" label=""></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N13" label=""></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N21" label=""></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N22" label=""></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="matriz3N23" label=""></v-text-field>
            </v-col>
        </v-row>
    </v-card>

</div>
</template>

<script>
export default {
    data() {
        return {
            items: ['Adição de Matrizes', 'Subtração de Matrizes', 'Mutiplicação de Por Matriz'],
            matriz1: {
                n11: "",
                n12: "",
                n13: "",
                n21: "",
                n22: "",
                n23: "",
            },
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
            if (this.matriz1.n11 != "" && this.matriz2.n11 != "") {
                var novo = parseInt(parseInt(this.matriz1.n11) + parseInt(this.matriz2.n11))
            } else {
                var novo = ""
            }
            return novo
        },
        matriz3N12() {
            if (this.matriz1.n12 != "" && this.matriz2.n12 != "") {
                var novo = parseInt(parseInt(this.matriz1.n12) + parseInt(this.matriz2.n12))
            } else {
                var novo = ""
            }
            return novo
        },
        matriz3N13() {
            if (this.matriz1.n13 != "" && this.matriz2.n13 != "") {
                var novo = parseInt(parseInt(this.matriz1.n13) + parseInt(this.matriz2.n13))
            } else {
                var novo = ""
            }
            return novo
        },
        matriz3N21() {
            if (this.matriz1.n21 != "" && this.matriz2.n21 != "") {
                var novo = parseInt(parseInt(this.matriz1.n21) + parseInt(this.matriz2.n21))
            } else {
                var novo = ""
            }
            return novo
        },
        matriz3N22() {
            if (this.matriz1.n22 != "" && this.matriz2.n22 != "") {
                var novo = parseInt(parseInt(this.matriz1.n22) + parseInt(this.matriz2.n22))
            } else {
                var novo = ""
            }
            return novo
        },
        matriz3N23() {
            if (this.matriz1.n23 != "" && this.matriz2.n23 != "") {
                var novo = parseInt(parseInt(this.matriz1.n23) + parseInt(this.matriz2.n23))
            } else {
                var novo = ""
            }
            return novo
        }
    }

}
</script>

<style>
.pai {
    width: 800px;
}

.comp {
    width: 300px;
}
</style>
