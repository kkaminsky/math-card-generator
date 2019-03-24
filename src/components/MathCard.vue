<template>
  <table>
    <tr v-for="i in 2">
      <td v-for="j in 6">
        <table cellpadding="0" cellspacing="0" style="font-family:Times New Roman, serif;font-size: 14pt;" border="1">
          <thead>Вариант {{j}} </thead>
          <tbody v-for="n in 10" align="left">
          <tr>
            <td width="100">{{getRandomExpr()}}</td>
            <td width="30"></td>
          </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </table>

</template>

<script>
export default {
  data(){
    return{
      items:['+','-','*','/']
    }
  },
  methods:{
    randomInteger(min, max) {
      var rand = min + Math.random() * (max + 1 - min);
      rand = Math.floor(rand);
      return rand;
    },
    getRandomExpr(){
      let i = this.randomInteger(0,3)
      let item = this.items[i]
      if(item==='+'){
        return this.randomInteger(1,100)+"+"+this.randomInteger(1,40)
      }
      else if(item==='-'){
        let result = -1;
        let a = 1;
        let b = 2;
        while (result<0){
          a = this.randomInteger(1,100)
          b = this.randomInteger(1,100)
          result = a-b;
        }
        return a+"-"+b;
      }
      else if (item==='*'){
        return this.randomInteger(2,10)+"*"+this.randomInteger(2,10);
      }
      else{

        let a = this.randomInteger(2,10);
        let b = this.randomInteger(2,10);
        while (a*b===a){
          a = this.randomInteger(2,10);
          b = this.randomInteger(2,10);
        }
        return a*b +"/" + a;
      }

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
