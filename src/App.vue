<template>

  <div>
    <div :key="i" v-for="(doc,i) of docs">
        {{doc.title}}
    </div>
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
      return this.data?.docs
    }
  },
  mounted(){
    axios.get('https://openlibrary.org/search.json?q=mr+fox').then(
      res=>this.data=res.data
    )
  }
}
</script>

