<template>
  <div class="conversor">
    <h2>{{moedaA}} Para {{moedaB}}</h2>
    <input class="pesq1" type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
    <input class="pesq2" type="button" value="Converter" v-on:click="converter">
    <h2>{{moedaB_value}}</h2>
  </div>
</template>

<script>
export default{
  name: "Conversor",
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0
    };
  },
  methods: {
    converter(){
      let de_para = `${this.moedaA}_${this.moedaB}`

      let url = `https://free.currconv.com/api/v7/convert?q=${de_para}&compact=y&apiKey=13c1211aed07855ca70b`

      fetch(url)
      .then(res => {
        return res.json()
      })
      .then(json => {
        let cotacao = json[de_para].val
        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
      })
    }
  }
}
</script>

<style scoped>
.conversor{
  background-color: #00FA9A;
  padding: 20px;
  max-width: 300px;
  min-width: 22em;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-radius: 4px;
}

.pesq1{
  background-color: #ecfffc;
  border: none;
  min-height: 25px;
  border-radius: 4px 0px 0px 4px;
}

.pesq2{                                                      border: none;
  min-height: 27px;
  border-radius: 0px 4px 4px 0px;

}

.pesq2{
  background-color: #0DB4FD;
  color: #2c3e50;
  font-weight: 400;
}
</style>
