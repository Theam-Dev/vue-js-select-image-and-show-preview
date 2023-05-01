<template>
  <div class="viewimg">
    <img width="150" height="150" :src="url" class="preview" />
    <label class="label">
      <input type="file" @change="onFileChange" />
      <span>Select a file</span>
    </label>
  </div>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      url: 'http://placehold.it/150x150',
    }
  },
  methods: {
    onFileChange(e) {
      const file = e.target.files[0];
      this.url = URL.createObjectURL(file);
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
.viewimg {
  display: inline-grid;
}
label.label input[type="file"] {
  position: absolute;
  top: -1000px;
}
.label,
.preview {
  cursor: pointer;
  border: 1px solid #cccccc;
  border-radius: 5px;
  margin: 5px;
  background: #dddddd;
  display: inline-block;
}
.label{
  padding: 5px 15px;
}
</style>
