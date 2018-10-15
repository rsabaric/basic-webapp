<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <p>Enter Number:
      <input v-model.number.lazy="num3" placeholder="first number"></p>
      <p>Enter Number:
      <input v-model.number.lazy="num4" placeholder="second number"></p>
      <p>Select Operator:
      <select v-model="selected">
       <option disabled value="">Please select one</option>
       <option>Plus</option>
       <option>Minus</option>
       <option>Multiplied By</option>
       <option>Divided By</option>
      </select></p?>
      <button v-on:click="testFunc">Calculate</button>
      <p v-if="testval != null"> {{ num1}} {{selected}} {{num2}} = {{testval}}</p>
    <h2>2 Things that are difficult in JavaScript</h2>
    <ol>
      <li>naming things</li>
      <li>recursion</li>
      <li>off-by-one errors</li>
    </ol>
    <h3>{{ msg2}}</h3>
    <button v-on:click="yesCounter">Yes</button>
    <button v-on:click="noCounter">No</button>
    <p>Total number of yes votes = {{yes}}</p>
    <p>Total number of no votes = {{ no }}</p>
    <button v-on:click="resetVote">Reset Poll</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'I like warm cookies and ice cream.',
      msg2: 'Quick Poll: Do you think this joke is funny?',
      num1: null,
      num2: null,
      num3: null,
      num4: null,
      yes: 0,
      no:0,
      testval: null
    }
  },
  methods: {
      yesCounter: function(){
      this.yes = this.yes +1;
          },
    noCounter: function(){
      this.no = this.no +1;
          },
    testFunc: function(){
        if (this.selected=="Minus"){
        this.testval = this.num3 - this.num4
        }
         if (this.selected=="Plus"){
        this.testval = this.num3 + this.num4
        }
         if (this.selected=="Multiplied By"){
        this.testval = this.num3 * this.num4
        }
         if (this.selected=="Divided By"){
        this.testval = this.num3 / this.num4
        }
        this.num1 = this.num3;
        this.num2 = this.num4;
    },
        resetVote: function(){
      this.yes = 0;
      this.no = 0;
          }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ol {
  list-style-type: decimal;
  width: 40%;
  margin: auto;
}

li {
  display: list-item;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

