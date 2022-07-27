<template>
  <div>
    {{docs}}
  </div>
</template>

<script>
  import axios from 'axios'


export default {
  name: 'App',
  data(){
      return {
        data:null
      }
  },
  computed:{
    docs(){
      return this.data?.docs.map(data=>data)
    }
  },
  mounted(){
    axios.get('https://openlibrary.org/search.json?q=mr+fox').then(
      res=>this.data=res.data
    )
  }
}
</script>

