<template>
  <div>
    <div>
      <blog-member :account-name="accountName"></blog-member>
      <div class="blog-container">
        <div class="section-a">
            <blog-tags></blog-tags>
        </div>
        <div class="section-b">
          <blog-posts></blog-posts>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import BlogMember from '@/components/blog/BlogMember.vue';
import BlogTags from '@/components/blog/BlogTags.vue';
import BlogPosts from '@/components/blog/BlogPosts.vue';

export default {

  components: {
    BlogMember,
    BlogTags,
    BlogPosts,
  },
  
  data() {
      return {
        accountName: 'happyhsryu',
      }
    },


}
</script>

<style>
.blog-container {
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
</style>