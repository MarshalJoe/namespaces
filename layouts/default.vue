<script>
import Footer from '~/components/Footer.vue';

export default {
    components: {
        Footer,
    }
}
</script>


<template>
  <div>
    <nuxt/>
    <Footer/>
  </div>
</template>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button-clear {
  border: 1px solid #36454f;
  color:#36454f;
  border-radius: 3px;
  padding: 3px 5px 3px 5px;
}

.button-clear:hover {
  color:white;
  background-color:#36454f;
  text-decoration: none; 
}
</style>
