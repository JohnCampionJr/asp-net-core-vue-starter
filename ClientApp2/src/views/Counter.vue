<template>
  <div>
    <h1>Counter</h1>
    <p>This is a simple example of a Vue.js component test integrated with Vuex</p>
    <Counter />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import Counter from '@/components/Counter.vue'

@Component({
  components: { Counter }
})
export default class CounterView extends Vue {}
</script>
