<template>
  <div>
    <!-- Include our props by using double braces to include the value of the variable -->
    <h1>{{ title }}</h1>
    <p>{{ subTitle }}</p>
  </div>
</template>

<script>
export default {
  name: 'Title',

  // Declare our props, in other words our custom attributes.

  props: {
    title: String,
    subTitle: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* Set the styles for each text element */
h1 {
    margin-bottom: 0;
    font-size: 3em;
    line-height: 1;
    font-weight: 700;
    font-family: 'Roboto', Arial, Helvetica, sans-serif;
}
p {
    font-size: 1em;
    font-weight: 400;
}
</style>
