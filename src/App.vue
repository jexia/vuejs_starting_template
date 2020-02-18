<template>
  <div id="app">
    <!-- Create our layout for the HTML -->
    <div class="flex-container">
        <div class="row">
            <div class="flex-item">
              <!-- Include our custom elements with our custom attributes -->
              <img class="logo" alt="Jexia Logo" src="./assets/images/logo.png" />
            </div>
            <div class="flex-item">
              <Title title="Welcome to your Jexia app." subTitle="Build applications faster than ever. Serverless, simple, secure." />
            </div>
            <div class="flex-item">
              <!-- the "journey" object delcared below in the export is passed to our custom links parameter -->
              <ListSection title="Start your journey" :links="journey" />
            </div>
            <div class="flex-item">
              <ListSection title="Essential Links" :links="essentialLinks" />
            </div>
        </div>
    </div>
    <!-- A component with no custom attributes is called. (Guess what this includes...) -->
    <Particles/>
  </div>
</template>

<script>
// Import the different components
import Title from './components/Title.vue'
import ListSection from './components/ListSection.vue'
import Particles from './components/Particles.vue'

export default {
  name: 'App',

  // Declare the objects for our lists of links
  data: function () {
    return {
      journey: {
        'Sign-up': 'https://app.jexia.com/signup',
        'Take a tour': 'https://www.jexia.com/en/docs/getting-started/'
      },
      essentialLinks: {
        Docs: 'https://www.jexia.com/en/docs/',
        Support: 'https://www.jexia.com/en/contact/',
        Features: 'https://www.jexia.com/en/features/',
        Jobs: 'https://jexiacom.recruitee.com/',
        Pricing: 'https://www.jexia.com/en/pricing/',
        Twitter: 'https://twitter.com/JEXIACOM/',
        Github: 'https://github.com/jexia/',
        Facebook: 'https://www.facebook.com/JEXIACOM/'
      }
    }
  },
  // Include our imported components
  components: {
    Title,
    ListSection,
    Particles
  }
}
</script>

<style>
/* Declare our main styling, layout and body etc. */

/* Import Google font */
@import url('https://fonts.googleapis.com/css?family=Open+Sans:300,400|Roboto:400,700&display=swap');

/* Set global styles such as font size and family */
html,
body {
    height: 100%;
    font-size: 1.1em;
    color: #212121;
    font-family: 'Open Sans', Arial, Helvetica, sans-serif;
}

/* As we have created a mobile-first display, we should remove the function for desktop users to scroll
 * IF their screen is bigger:
 */
@media (min-width: 800px) and (min-height: 860px) {
    html,
    body {
        overflow: hidden;
    }
}

/* Add a margin to the whole body */
body {
    margin: 1em;
}

/* Start the styling for the flex box containers. This allows some cool layout affects. (And is what
 * fully centers the content)
 */
.flex-container {
    height: 100vh;
    width: 100%;
    padding: 0;
    margin: 0;
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    align-items: center;
    justify-content: center;
}

.row {
    width: auto;
    height: auto;
    max-height: 100vh;
}

.flex-item {
    padding: 5px;
    width: auto;
    height: auto;
    margin: 10px;
    line-height: auto;
    font-weight: bold;
    font-size: 1em;
    text-align: center;
}

/* Apply the styling for the logo to ensure it's not too big */
.logo {
    margin: .1em;
    height: auto;
    max-height: 10em;
}

/* Add a cool selection effect to change it from blue to a nice yellow, to match our theme. */
*::selection {
    background: #fff2a8;
}

*::-moz-selection {
    background: #fff2a8;
}

/* For the selection coloring we saw before to work nicely, we've removed the ability to select non-text elements */
body {
    -webkit-user-select: none;
    /* webkit (safari, chrome) browsers */
    -moz-user-select: none;
    /* mozilla browsers */
    -khtml-user-select: none;
    /* webkit (konqueror) browsers */
    -ms-user-select: none;
    /* IE10+ */
}

h1,
h2,
p {
    -webkit-user-select: text;
    /* webkit (safari, chrome) browsers */
    -moz-user-select: text;
    /* mozilla browsers */
    -khtml-user-select: text;
    /* webkit (konqueror) browsers */
    -ms-user-select: text;
    /* IE10+ */
}
</style>
