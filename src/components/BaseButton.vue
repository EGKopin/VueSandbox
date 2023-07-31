<script>
  export default {
    props: {
      text: String,
      icon: String,
    },
  };
</script>

<template>
  <button>
    <!-- {{ icon }} - {{ text }} -->
    <slot>Submit</slot>
    </button>
</template>