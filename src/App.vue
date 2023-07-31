<script>
  export default { //This object is the App that is being imported into the main.ts file createApp(*App*)
    data () {
      return {
        message: 'It works',
        counterTitle: 'Standard Counter',
        count: 0,
        incrementAmount: 4,
        listOfNumbers: [1,2,3,4]
      }
    },
    methods: {
      incrementCount(number, event) {
        this.count += this.incrementAmount
      }
    },
    computed: {
      displayTitle() {
        if (this.count > 20){
          return 'Long Counter'
        } else {
          return 'Standard Counter'
        }
      },
      optimizedIncrementAmount(){
        return this.displayTitle.length * this.incrementAmount
      }
    }
  }
</script>

<template>
  <p v-if="message.length % 2 === 0">Even: {{message.toUpperCase()}}</p>
  <p v-else>Odd: {{message}}</p>
  <ul>
    <li v-for="(number, index) in listOfNumbers" :key="`item-${index}`">{{ number }}</li>
  </ul>
  <hr>
  
  <h1>{{displayTitle}}</h1>
  <h3>optimized amount: {{optimizedIncrementAmount}}</h3> 
  <p>This optimized amount is dependent on 2 things, example of tool chaining. </p>
  <p>{{ count }}</p>
  <button v-on:click="incrementCount(10, $event)">Increment Count</button>
  <div>
    <label for="incrementCount">Increment by:</label>
    <input type="number" v-model="incrementAmount" />
  </div>
</template>
