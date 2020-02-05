<template>
    <div>
       <div v-for="(mat,index1) in matrix" v-bind:key="mat">
           <button 
           class="buttonNumber"
           v-for="(number,index2) in mat" 
           v-bind:id="index1+','+index2" 
           v-bind:key="index1+ ',' +index2" 
           :class="{'hideNumber': index1==0 || index2== 0}"
           :column="index1"
           :row="index2"
           @mouseover="changeColors(index2, index1, event)"
           >
           {{number}}</button>
       </div>
     
    </div>
</template>

<script>
  export default {
  name: 'Matrix',
  props: {
    matrix: Array
  },
  data() {
    return {
        showMultiplicaciones: false,
        allButtons: null,
        columns: [],
        rows: []
    }
  },
  methods: {
    multiplicar() {
      this.showMultiplicaciones = true
    },
    changeColors(row, column, event){
        if(event) {
            event.preventDefault()
        }
        var allButtons = document.querySelectorAll('.buttonNumber')
        for (var k= 0; k<allButtons.length; k++) {
            allButtons[k].style.backgroundColor = 'white';
            allButtons[k].style.color = 'black';
        }
        document.getElementById(`${column},${row}`).style.backgroundColor = 'black'
        document.getElementById(`${column},${row}`).style.color = 'white'
        this.columns = document.querySelectorAll(`[row="${row}"]`)
        this.rows = document.querySelectorAll(`[column="${column}"]`)
        for (var i= 0; i<column; i++) {
          if (parseInt(this.columns[i].attributes.row.value)<row+1) {
            this.columns[i].style.backgroundColor = 'pink';
            if(i>0){this.columns[i].style.color = 'rgba(0,0,0,0)'}
          }
        }
        for (var j= 0; j<row; j++) {
          if (parseInt(this.rows[j].attributes.column.value)<column+1) {
            this.rows[j].style.backgroundColor = 'pink';
            if(j>0){this.rows[j].style.color = 'rgba(0,0,0,0)'}
          }
        }

    }
  }
}
</script>
<style>
    .hideNumber {
        color: rgba(0,0,0,1)
    }
    .buttonNumber{
        width: 50px;
        height: 50px;
        color: rgba(0,0,0,1)
    }
    .buttonNumber:hover{
        background-color:pink;
    }
</style>