<template>
  <div class="hello">
    
    <h1>{{ msg }}</h1>
     <p>VueJS is pretty cool - {{myName}} ({{age}})</p>
     <p>multi ({{age * 3}})</p>
     <p>random: {{randomNumber()}}</p>
      <div>
        <img v-bind:src="someImageUrl" style="width:100px;height:100px">
    </div>
     <div>
        <input v-bind:value="myName" type="text">
    </div>
    <div>
        <button v-on:click="increase(2, $event)">click me </button>
        <button v-on:click="counter++">click me direct javascript in template </button>
        <p>{{counter}}</p>
        <p>{{counter * 2 > 10 ? 'greater than 10': 'no greater than 10'}}</p>

        <p v-on:mousemove="updateCoordinates">
          Coordinates: {{x}} / {{y}}
          - <span v-on:mousemove.stop> DEAD SPOT </span>
        </p>
        <input type="text" v-on:keyup.enter="alertMe">
        <input type="text" v-model="myName">
        yeah: {{myName}}
    </div>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      myName: 'Marce',
      age: 55,
      someImageUrl:"http://placekitten.com/200/300",
      counter: 0,
      x:0,
      y:0,
    };
  },
  methods: {
    alertMe () {
      alert('pepepep');
    },
    randomNumber() {
      return Math.random(0,1);
    },
    increase(step, event) {
      this.counter += step + event.clientX;  
    },
    updateCoordinates: function (event) {
      this.x = event.clientX;
      this.y = event.clientY;
    }
  },
  props: {
    msg: String
  }
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
