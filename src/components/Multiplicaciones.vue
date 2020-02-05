<template>
    <div>
        <label style="color:white;">Juega con las tablas</label>
        <Matrix :matrix="matrix"/>
    </div>
</template>

<script>
import Matrix from './Matrix.vue'
export default {
    name: 'Multiplicaciones',
    components: {
        Matrix
    },
    data() {
        return {
            matrix: []
        }
    },
    created() {
        this.poblarMatrix(10)
    },
        methods: {
            poblarMatrix(max) {
                for(var x=0; x<max; x++ ){
                    let auxArray = []
                    for(var y=0; y<max; y++ ){
                        auxArray[y] = (y + 1) * (x + 1)
                    }
                this.matrix[x] = auxArray
            }
        }
    }
}
</script>