<template>
  <div class="text-center">
    <img src="@/assets/logo.png" alt="Vuetify.js" class="mb-5" />
    <HelloWorld
      quote="Welcome to Your ASP.NET Core + Vue.js + TypeScript App"
      author="brought to you by Software Ateliers"
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src

@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {}
</script>
