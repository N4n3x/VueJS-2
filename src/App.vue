<template>
  <div id="app">
    <card firstname="john" :age="42" />
    <counter />
    <a-form @custom-event="logEventTime" />
    <ul>
      <li v-for="(person, index) in people" :key="person.lastname" >
        <card
          v-if="index % 2 == 0"
          :firstname="person.firstname"
          :lastname="person.lastname"
        />
        <card
          v-else
          alternate
          :firstname="person.firstname"
          :lastname="person.lastname"
        />
      </li>
    </ul>
    
  </div>
</template>

<script>
import AForm from './components/AForm.vue'
import Card from './components/Card.vue'
import Counter from './components/Counter.vue'
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    Card,
    Counter,
    AForm
    
  },
  data(){
    return {
      people: [
        { firstname : "Alex", lastname : "Andre"},
        { firstname : "Jean", lastname : "Claud"},
        { firstname : "Aziz", lastname : "Ouz"},
      ]
    }
  },
  methods:{
      logEventTime(date){
        console.log('événement custom reçu à', date);
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
  margin-top: 60px;
}
</style>
