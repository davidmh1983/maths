<template>
    <div>
        <div style="color:white; font-size:100px">
            {{numA}} + {{numB}} = <input style="width:150px; font-size:100px;" v-model="result"/>
        </div>
        
        <div @click="corregir">Corregir</div>
        <div>Siguiente</div>
        <blocks :num1="numA" :num2="numB"></blocks>
    </div>
</template>

<script>
    import blocks from './Blocks.vue' 
    export default {
        name: 'Sumas',
        components:{
            blocks
        },
        data() {
            return {
                numA: 3,
                numB: 4,
                result: 0,
                isCorrect : false
            }
        },
        methods: {
            corregir() {
                this.isCorrect = this.numA + this.numB === this.result ? true : false
            }
        }
    }
</script>

<style>

</style>