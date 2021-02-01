<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
          <label>Template Name</label>
          <input class="form-control" type="text" />
        </div>
      </div>
      <div class="row">
        <div class="col">
          <label>Code</label>
          <MonacoEditor
            width="800"
            height="500"
            language="javascript"
            :options="options"
            v-model="code"
          ></MonacoEditor>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import MonacoEditor from 'monaco-editor-vue';
export default {
  name: 'App',
  components: {
    // HelloWorld
    MonacoEditor
  },
  data() {
    return {
      options: {
        //Monaco Editor Options
      },
      code: ""
    }
  },
  methods: {
    onChange(value) {
      console.log(value);
    }
  }
}
</script>

<style>

</style>
