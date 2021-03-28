<template>
  <div id="app" class="container">
    <Header :day="brazil.date"/>
    <Statistics :vaccination="brazil"/>
    <Footer />
  </div>
</template>

<script>
  import axios from 'axios'
  import Header from '@/components/Header.vue'
  import Statistics from './components/Statistics.vue'
  import Footer from './components/Footer.vue'

  export default {
    name: 'App',
    components: {
      Header,
      Statistics,
        Footer
    },
    data(){
      return {
        vaccinations: Array,
        brazil: Array
      }
    },
    created(){
      axios.get('https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/vaccinations.json').then(data => {
        this.vaccinations  = data.data
        this.brazil = this.vaccinations.filter(this.brFilter)
        this.brazil = this.brazil[0].data
        this.brazil = this.brazil[this.brazil.length - 1]
      }).catch(err => console.log(err))
    },
    methods: {
      brFilter(value){
        return value.country == 'Brazil'
      }
    }
  }
</script>

<style>
.small-card {
  border-radius: 5px;
  cursor: pointer;
  padding: .25rem;
}
.small-card-green {
  background: rgba(40, 226, 40, 0.063);
}
.small-card-purple {
  background: rgba(90, 40, 226, 0.063);
}
body{
  background: #161625;
  margin: 0;
}
* {
  font-family: system-ui,-apple-system,BlinkMacSystemFont,Segoe UI, Helvetica Neue,Helvetica,Arial,sans-serif;
  color: #6c757d;
}
.container {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
}
</style>
