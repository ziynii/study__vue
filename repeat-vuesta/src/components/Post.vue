<template>
  <div class="post">
    <div class="post-header">
      <div
        class="profile"
        :style="{ backgroundImage: `url(${postData.userImage})` }"
      ></div>
      <span class="profile-name"> {{ postData.name }} </span>
    </div>
    <div
      :class="postData.filter"
      class="post-body"
      :style="{ backgroundImage: `url(${postData.postImage})` }"
    ></div>
    <div class="post-content">
      <p>💗 {{ postData.likes }}</p>
      <p><strong>Yeeoni_</strong> {{ postData.content }}</p>
      <p class="date">{{ postData.date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
	props: {
		postData : Object,
	}
};
</script>

<style>
.post {
  width: 100%;
	margin-top: 24px;
}
.profile {
  background-image: url('https://placeimg.com/100/100/arch');
  width: 30px;
  height: 30px;
  background-size: 100%;
  border-radius: 50%;
  float: left;
}
.profile-name {
  display: block;
  float: left;
  padding-left: 10px;
  padding-top: 7px;
  font-size: 14px;
}
.post-header {
  height: 46px;
  padding: 10px;
}
.post-body {
  background-image: url('https://placeimg.com/640/480/animals');
  height: 450px;
  background-position: center;
  background-size: cover;
}
.post-content {
	margin-top: 8px;
  padding-left: 15px;
  padding-right: 15px;
  font-size: 14px;
}
.date {
  font-size: 11px;
  color: grey;
	margin-top: 6px;
}
</style>
