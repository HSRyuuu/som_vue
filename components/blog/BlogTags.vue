<template>
  <div class="sidebar">
    <h2>전체 게시글: {{ totalPostCount }}개</h2>
    <ul>
      <li v-for="tag in tagList" :key="tag.id">
        - {{ tag.tagName }} ({{ tag.tagCount }}개)
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  props: {
    accountName: {
      type: String,
      required: true
    }
  },
  data(){
    return {
      totalPostCount: 0,
      tagList: [],
    }
  },
  async fetch(){
    const response = await this.$axios.get(`/blog/${this.accountName}/tags`);
    
    this.totalPostCount = response.data.totalPostCount;
    this.tagList = response.data.tagList;
  }
}
</script>

<style scoped>
.container {
  display: flex;
}

.content {
  flex-grow: 1;
  padding: 20px;
  background-color: #fff;
}
</style>