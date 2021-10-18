<template>
  <ul>
      <li v-for="(email,index) in emails" :key='index'>{{email}}</li>
  </ul>
</template>

<script>
export default {
  name: 'list',
  props: {
    emails: Array
  }


}
</script>

<style lang='scss' scoped>

</style>