<template>
  <div id="app">
    <HelloMarie/>
  </div>
</template>

<script>
import HelloMarie from './components/HelloMarie.vue'

export default {
  name: 'app',
  components: {
    HelloMarie
  }
}
</script>
<style>


* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}


html,body,div,svg{
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
</style>