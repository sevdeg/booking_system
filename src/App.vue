<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/test">Test</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.animation-in {
   transform-origin: left;
   animation: in .6s ease-in-out;
}
.animation-out {
   transform-origin: bottom left;
   animation: out .6s ease-in-out;
}

</style>

<!--
<template>
    <div>
        <component v-bind:is="component"></component>
        <button v-on:click="component = 'form-en'">Show form one</button>
        <button v-on:click="component = 'form-two'">Show form two</button>
    </div>
</template>

<script>
import formEn from './components/formEn.vue'
import formTwo from './components/formTwo.vue'

export default {
  components: {
    'form-en': formEn,
    'form-two': formTwo
  },
  data () {
    return {
      component: 'form-two'
    }
  }
}
</script>-->
<!---<style lang="scss">
  @import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
  body {
    margin: 0;
    padding: 0;
  }
  #app {
    font-size: 1rem;
    color: #444;
    width: 100%;
    min-height: 100vh;
    overflow: hidden;
  }
</style>-->
<!--<script>
import Test from './components/Test.vue'
export default {
  name: 'App',
  components: {
    Test
  }
}
</script>
-->
