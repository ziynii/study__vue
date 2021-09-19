<template>
  <header class="header">
    <ul class="header-btn-left">
      <li v-if="step != 0" @click="step > 0 ? step-- : 0">Cancel</li>
    </ul>
    <img src="./assets/logo.png" class="logo" alt="logo" />
    <ul class="header-btn-right">
      <li v-if="step == 1" @click="step++">Next</li>
      <li v-if="step == 2" @click="publish">Publish</li>
    </ul>
  </header>
  <Container :postData="postData" :step="step" :selectImage="selectImage" />
  <button v-if="step == 0" @click="more" class="more">더보기</button>
  <div class="footer">
    <ul class="footer-btn-plus">
      <input @input="upload" type="file" id="file" class="inputfile" />
      <label for="file" class="input-plus">+</label>
    </ul>
  </div>
</template>

<script>
import postData from './postData';
import Container from './components/Container.vue';
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      postData: postData,
      step: 0,
      selectImage: '',
    };
  },
  methods: {
    more() {
      axios
        .get('https://codingapple1.github.io/vue/more0.json')
        .then((result) => {
          this.postData.push(result.data);
        });
    },
    upload(e) {
      let file = e.target.files;
      let url = URL.createObjectURL(file[0]);
      this.selectImage = url;
      this.step++;
    },
  },
  components: {
    Container: Container,
  },
};
</script>

<style>
@import url(./app.css);
</style>
