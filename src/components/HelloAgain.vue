<template>
  <div class="hello">    
    <div>
        <button v-on:click="counter++">Increase me </button>        
        <button v-on:click="counter--">Decrease me </button>        
        <button v-on:click="secondCounter++">Increase seconddd me </button>        
        <p>counter: {{counter}}</p>               
        <p>second counter: {{secondCounter}}</p>               
        <p>result: {{result()}}</p>               
        <p>result: {{output}}</p>               
    </div>    
  </div>
</template>

<script>
export default {
  name: 'HelloAgain',
  data () {
    return {      
      counter: 0,      
      secondCounter: 0,      
    };
  },
  computed: {
    output() {
      console.log('COMOUTED!!!!');
      return this.counter > 5 ? 'greater than 5' : 'Smaller than 5';
    }
  },
  watch: {
    counter() { //value
      var vm = this;
      setTimeout(()=>{
        vm.counter = 0;
      },2000)
    }
  },
  methods: {    
    result() {      
      console.log('re-CALCULATED!!!!');
      return this.counter > 5 ? 'greater than 5' : 'Smaller than 5';
    },    
  },  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
