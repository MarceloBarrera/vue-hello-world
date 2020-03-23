<template>
  <div>    
    <div>
        <button v-on:click="counter++">Increase me </button>        
        <button v-on:click="counter--">Decrease me </button>        
        <button v-on:click="secondCounter++">Increase seconddd me </button>        
        <p>counter: {{counter}}</p>               
        <p>second counter: {{secondCounter}}</p>               
        <p>result: {{result()}}</p>               
        <p>result: {{output}}</p>               
    </div>  
    <div class="demo" :class="[color, {red: false} ]">
      pepepepepe
    </div>  
    <div class="demo" :style="{backgroundColor: color}"></div>
    <div class="demo" :style="myStyle"></div>
    <div class="demo" :style="[myStyle, {height: width + 'px'}]"></div>
    <hr>
    <input type="text" v-model="color">
    <input type="text" v-model="width">
  </div>
  
</template>

<script>
export default {
  name: 'HelloAgain',
  data () {
    return {      
      counter: 0,      
      secondCounter: 0,
      attachRed: false,
      color: 'gray',
      width: 100
    };
  },
  computed: {
    myStyle: function() {      
      return {
        backgroundColor: this.color,
        width: this.width + 'px'
      };
    },
    divClasses() {
      return {
        red: this.attachRed,
        blue: !this.attachRed
      }
    },
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
.demo {
  width: 100px;
  height: 100px;
  background-color: gray;
  display: inline-block;
  margin: 10px;
}
.demoA {
  background-color: gray;
}
.red {
  background-color: red;
}
.green {
  background-color: green;
}
.blue {
  background-color: blue;
}

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
