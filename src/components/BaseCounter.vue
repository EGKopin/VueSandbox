<script>
  export default {
    data: () => ({
      count: 0,
      counterTitle: 'Standard Counter',
      incrementAmount: 4
    }),
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
    },
    methods: {
      incrementCount(number, event) {
        this.count += this.incrementAmount
      }
    }
  };
</script>

<template>
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