<template>
  <div id="app">
    <List :emails='emailList'/>
  </div>
</template>

<script>
import List from './components/List.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    List
  },
  data() {
    return {
      emailList: [],
    }
  },
  beforeCreate() {
    
        for (let i=0; i<10; i++) {
          axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
            .then((response) => {
              this.emailList.push(response.data.response);
           })
        }
        console.log(this.emailList)
  }
}

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

 
</style>