<template>
  <div>
    <div class="blog-header">
      <div class="profile">
        <img v-if="member.profileImage" :src="member.profileImage" alt="Profile Image" class="profile-image"  />
        <img v-else src="https://via.placeholder.com/150" alt="Default Profile" class="profile-image"  />

        <div class="blog-info">
          <h1 class="blog-name">{{ member.blogName }}</h1>
          <p class="nickname">@{{ member.nickname }}</p>
          <p class="introduction">{{ member.introduction }}</p>
          <div class="follow-info">
            <span>Followers: {{ member.followerCount }}</span>
            <span>Following: {{ member.followingCount }}</span>
          </div>
          <button class="follow-btn" :class="followStatusClass">{{ followStatusText }}</button>
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
  data() {
    return {
      member: {
        blogName: '',
        profileImage: '',
        nickname: '',
        introduction: '',
        followerCount: 0,
        followingCount: 0,
        followStatus: 'NOT_LOGGED_IN'
      },
    }
  },

  async fetch() {
    const response = await this.$axios.get(`/blog/${this.accountName}/member`);
    this.member = response.data;
  },
  
  computed: {
    // css class를 선택
    followStatusClass() {
      return this.member.followStatus === 'FOLLOWING' ? 'following' : '';
    },
    // 텍스트를 선택
    followStatusText() {
      return this.member.followStatus === 'FOLLOWING' ? 'Unfollow' : 'Follow';
    }
  },
  
}
</script>

<style>
.blog-header {
  display: flex;
  align-items: center;
  padding: 20px;
  background-color: #FFFBEB;
  border-bottom: 1px solid #ddd;
}

.profile {
  display: flex;
  align-items: center;
}

.profile-image {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  margin-right: 20px;
}

.blog-info {
  display: flex;
  flex-direction: column;
}

.blog-name {
  font-size: 24px;
  margin: 0;
}

.nickname {
  font-size: 16px;
  color: #888;
  margin: 5px 0;
}

.introduction {
  font-size: 20px;
  margin: 10px 0;
  font-weight: bold;
  
}

.follow-info {
  display: flex;
  gap: 15px;
  font-size: 14px;
  margin-bottom: 15px;
}

.follow-btn {
  padding: 10px 20px;
  background-color: #007bff;
  border: none;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

.follow-btn.following {
  background-color: #6c757d;
}

.follow-btn:not(:hover) {
  opacity: 0.8;
}

</style>
