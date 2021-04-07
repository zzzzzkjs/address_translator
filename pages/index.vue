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
// Component Class - 컴포넌트를 클래스로 만들경우 장점
// 1. computed, methods 그리고 data를 따로 나눠서 선언하지 않아도 된다.
// 2. 함수 선언 시 매번 ,로 구분 지어주지 않아도 된다.
// 3. 자동완성 기능을 쉽게 사용할 수 있다.

// import Vue from 'vue'
import { Component, Vue } from 'nuxt-property-decorator'
// import Logo from '~/components/Logo.vue'
// TODO: 컴포넌트 선언 없는데 Logo컴포넌트가 불러와짐..(nuxt라서 가능한건지 확인해볼것)

@Component({
  components: {
    // Logo,
  },
})
export default class IndexPage extends Vue {
  name: string = 'hello-nuxt-ts-decorator'
}
// export default Vue.extend({})
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
