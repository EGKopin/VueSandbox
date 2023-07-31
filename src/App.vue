<script>
  import BaseCounter from './components/BaseCounter.vue'
  import UserCard from './components/UserCard.vue'
  import BaseButton from './components/BaseButton.vue'

  export default {
    components: {
      BaseCounter,
      UserCard,
    BaseButton
,
    },
    data () {
      return {
        userData: {
          name: 'Etana',
          food: 'Pie'
        },
        message: 'It works',
        listOfNumbers: [1,2,3,4]
      }
    },
    methods: {
      changeName() {
        this.userData.name = "Meow"
      },
    }
  }
</script>

<template>
  <!-- <BaseButton 
    text="Hi"
    icon="arrow"
  /> -->
  <BaseButton>{{ userData.name }} - or text</BaseButton>
  <BaseCounter />
  <UserCard 
    :user="userData"
    v-on:change-name="changeName"
  />
  <p v-if="message.length % 2 === 0">Even: {{message.toUpperCase()}}</p>
  <p v-else>Odd: {{message}}</p>
  <ul>
    <li v-for="(number, index) in listOfNumbers" :key="`item-${index}`">{{ number }}</li>
  </ul>
  <hr>
</template>
