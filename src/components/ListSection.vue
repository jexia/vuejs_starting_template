<template>
  <div>
    <h2>{{ title }}</h2>
    <ul>
      <!-- This is a for loop within vue, it takes our objects passed from App.vue and
      orders them by index: v-bind:key="index". This then allows us to use {{ var }} and
      loop through each entry within our object -->
      <li v-for="(url, urlTitle, index) in links" v-bind:key="index">
        <a :href="url" target="_blank">{{ urlTitle }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ListSection',
  props: {
    title: String,
    links: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* Set the styles for each text element */
h2 {
    margin-bottom: 1em;
    font-size: 1.75em;
    font-weight: 400;
    font-family: 'Roboto', Arial, Helvetica, sans-serif;
}

a {
    color: #f9b200;
    font-size: 1em;
    font-weight: 400;
}

/* Add styling to remove the normal list layout and replace it with a horizontal layout */
ul {
    margin: 0;
    padding: 0;
    font-size: 1em;
    width: 100%;
}

ul li {
    display: inline-block;
    vertical-align: top;
    width: auto;
    padding: 5px 10px;
}

ul li a {
    outline: none;
    display: block;
    text-align: center;
    width: auto;
}

ul li a:active,
ul li a:hover {
    color: #d89b00;
}
</style>
