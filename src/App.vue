<template>
  <div id="app">
    <app-header></app-header>
    <div class="container py-8 mx-auto">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import './assets/css/app.css'
import AppHeader from './components/AppHeader'

export default {
  name: 'app',  
  
  components: {
    'app-header': AppHeader
  },

  data() {
    return {
      search: '',
    }
  },

  methods: {
    submitSearch() {
      this.$router.push(
        {
          name: 'search-result',
          query: {
            q: this.search
          }
        }
      );
    }
  }
}
</script>