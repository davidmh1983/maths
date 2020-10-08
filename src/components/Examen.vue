<template>
    <div>
        <label style="color:white;">EXAMEN</label>
        <div v-for="(a,index) in exam" 
            v-bind:key="index"
            style="display:flex; direction:row; margin-bottom: 10px;justify-content: center; margin: 5px auto; font-size: 24px"
        >
            <div style=" color:white;width: 100px;text-align:right">
                {{a.numberA}} x {{a.numberB}} = 
            </div>
            <input :id="index" v-model="results[index]" style="font-size:24px;width: 50px;"/>

        </div>

        <button class="corregir" @click="correct">Corregir</button>
        <div style="margin-top: 40px;">
            <label style="color:white;font-size: 40px;" v-if="showNota">Nota: {{nota}} / 10</label>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Examen',
    data() {
        return {
            results:[],
            exam: [],
            nota: 0,
            showNota: false
        }
    },
    created(){
        this.createExam()
    },
    methods:{
        correct() {
            this.nota = 0;
            for(var i=0; i<this.exam.length; i++){
                if(this.exam[i].result === parseInt(this.results[i])){
                    document.getElementById(i).style.backgroundColor = 'lightgreen'
                    this.nota ++;
                }else{
                    document.getElementById(i).style.backgroundColor = 'pink'
                }
            }
            this.showNota = true
        },
        createExam() {
            this.nota = 0;
            this.showNota = false
            for(var j=0; j<10; j++){
                let a = Math.floor(Math.random() * 8) + 2
                let b = Math.floor(Math.random() * 8) + 2
                this.exam[j] = {
                    'numberA' : a,
                    'numberB' : b,
                    'result': a * b
                }
            }
        }
    }
}
</script>
<style scoped>
.corregir {
    min-width: 150px;
    padding: 8px;
    background-color: white;
    color: black;
    margin-top: 5px;
    border: none;
    border-radius: 3px;
}
.corregir:hover {
  background-color: #333;
  color: white;
}
</style>