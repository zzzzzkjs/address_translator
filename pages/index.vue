<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">address_translator</h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub @@@@@@{{ name }}@@@@@@@@@@
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
@Component({
  components: {
    // Logo,
  },
})
export default class IndexPage extends Vue {
  name: string = 'hello-nuxt-ts-decorator';
  data() {
    return {
      title: '',
    };
  }
  created() {
    const qs = require('qs');
    // this.$axios
    //   .post(
    //     '/addrlink/addrEngApi.do',
    //     qs.stringify({
    //       currentPage: 1,
    //       countPerPage: 5,
    //       keyword: '서울역',
    //       resultType: 'json',
    //     })
    //   )
    //   .then((res) => {
    //     console.log('주소 조회 결과');
    //     console.log(`data: ${res}`);
    //   });

    this.$axios
      .post('/addrTrans/addrEng', {
        currentPage: 1,
        countPerPage: 5,
        keyword: '서울역',
        resultType: 'json',
      })
      .then((res) => {
        console.log('주소 조회 결과');
        console.log(`data: ${res}`);
      });
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
