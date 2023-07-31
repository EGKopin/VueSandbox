<script>
  export default {
    props: {
      user: {
        type: Object,
        required: true,
        default: 'Something'
      },
    },
    emits: ['change-name'] 
  };
</script>

<template>
<h3>User: {{ user.name }}</h3>
<h4>Fav Food: {{ user.food }}</h4>
<button @click="$emit('change-name')">Change Name</button>
</template>