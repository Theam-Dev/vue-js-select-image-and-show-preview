<template>
   <input type="file" @change="onFileChange" />
  <div id="preview">
    <img v-if="url" :src="url" width="80"/>
  </div>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      url: null,
    }
  },
  methods: {
    onFileChange (e) {
      const file = e.target.files [0];
      this.url = URL.createObjectURL (file);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
