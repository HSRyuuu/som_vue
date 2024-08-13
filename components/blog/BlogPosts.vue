<template>
  <div class="post-list">
    <div v-for="post in postList" :key="post.postId" class="post-item" @click="goToPostDetail(post.postId)">
      <div class="post-container">
        <div class="section-a">
          <div class="thumbnail">
        <img :src="post.thumbnail" alt="Post Thumbnail" />
      </div>
        </div>
        <div class="section-b">
          <div class="post-content">
        <h2>제목: {{ post.title }}</h2>
        <p class="introduction">소개: {{ post.introduction }}</p>
        <div class="tags">
          <span v-for="tag in post.tags" :key="tag" class="tag">{{ tag }}</span>
        </div>
        <div class="meta">
          <span>Views: {{ post.views }}</span>
          <span>Likes: {{ post.likes }}</span>
          <span>Comments: {{ post.comments }}</span>
        </div>
      </div>
        </div>
      </div>
      
    
    </div>
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
      postList: []
    }
  },
  async fetch(){
    const response = await this.$axios.get(`/blog/${this.accountName}/posts`);
    
    this.postList = response.data.postList;
  },

  methods: {
    goToPostDetail(postId) {
      this.$router.push(`/blog/${this.accountName}/post/${postId}`);
    }
  },
  

}
</script>

<style scoped>
.post-container {
  display: flex;
  width: 100%;
}

.section-a {
  flex: 1;
  background-color: #FFFBEB; /* 예시 배경색 */
}

.section-b {
  flex: 4;
  background-color: #FEFCF3; /* 예시 배경색 */
}
.post-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.post-item {
  display: flex;
  flex-direction: column;
  width: calc(33.333% - 20px);
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  cursor: pointer;
}

.post-item:hover {
  transform: translateY(-5px);
}

.thumbnail img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.post-content {
  padding: 15px;
}

.post-content h2 {
  font-size: 1.5em;
  margin-bottom: 10px;
  color: #333;
}

.introduction {
  font-size: 1em;
  color: #666;
  margin-bottom: 10px;
}

.tags {
  margin-bottom: 10px;
}

.tag {
  background-color: #e0e0e0;
  color: #333;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 0.9em;
  margin-right: 5px;
  display: inline-block;
}

.meta {
  font-size: 0.9em;
  color: #999;
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}
</style>