<template>
  <div>
    <som-logo/> <!-- (3) -->
    <h1>메인페이지</h1>
    <div>{{ member }}</div>
  </div>
</template>

<script>
import SomLogo from '@/components/SomLogo.vue'; // (1)



export default {
  components: {
    SomLogo // (2)
  },
  
  

  data() {
    return {
      member: [],
      tags: [],
      posts:[],
    }
  },

  async fetch(){
    const response = await this.$axios.get('/blog/happyhsryu/posts');
    this.member = response.data;
  },
  
  

}
</script>

<style>

</style>