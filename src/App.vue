<template>
  <wu-button type='primary' round='true' size='large' icon="wu-icon-add">默认按钮</wu-button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import WuButton from './components/button/WuButton.vue';
export default defineComponent({
  name: 'App',
  components: {
    WuButton
  }
})
</script>

<style lang='scss'>
@import './assets/css/mian.scss';
</style>
