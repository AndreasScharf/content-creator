<template>
  <div id="app">
      <loginpage/>
      <div v-html="testtext">
      </div>

  </div>
</template>

<script>
import loginpage from './components/loginpage.vue'
import helloworld from '!vue-html-loader!./assets/startpage.html'

export default {
  name: 'App',
  components: {
      loginpage
  },
  methods:{
  },
  data(){
      return{
          testtext: helloworld,
          startpage_url: './assets/logo.png',
          items:[
              {id: 0, text:'Request 0', active:true},
              {id: 1, text:'Request 1', active:false},
              {id: 2, text:'Request 2', active:false},
              {id: 4, text:'Request 3', active:false},
          ]
      }
  }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    /*margin-top: 60px;*/
    font-size: 20pt;
}
.button, button{
    background-color: #42b983;
    color: white;
    border: 0;
    border-radius: 20pt;
    height: 40pt;
    padding: 10pt;
    width: auto;
    cursor: pointer;
}
loginpage{
  background-color: red;
}
iframe{
  width: 100%;
  height: auto;
}
</style>
