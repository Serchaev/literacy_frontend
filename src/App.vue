<script>
export default {
  data(){
    return {
      result: 0
    }
  },
  methods: {
    updateResult(data) {
      this.result = data;
    }
  },
}
</script>

<template>
  <!--<nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>-->
  <router-view :result="result" @updateResult="updateResult"/>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Inter, sans-serif;
  font-style: normal;
}
</style>
