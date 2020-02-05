<template>
    <div style="width:1000px; display: flex; flex-direction:row;">
        <div style="widht:50px; height:50px; margin-right:0;" v-for="n in num1" v-bind:key="-n"></div>
        <div style="widht:50px; height:50px; margin-right:0;" v-for="n in num2" v-bind:key="n"></div>
    </div>
</template>

<script>
    export default {
        name: 'Blocks',
        props:{
            num1: Number,
            num2: Number
        },
        data() {
            return {
                
            }
        },
        methods: {
        }
    }
</script>

<style>

</style>