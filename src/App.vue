<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
          <label class="mb-3">Template Name</label>
          <input class="form-control mb-3" type="text" v-model="template_name" />
        </div>
      </div>
      <div class="row">
        <div class="col">
          <label class="mb-3">Code</label>
          <MonacoEditor
            width="800"
            height="500"
            language="javascript"
            theme="vs-dark"
            :options="options"
            v-model="code"
            class="mb-3"
          ></MonacoEditor>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <button class="btn btn-primary" @click="submit">Submit</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
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
      code: "",
      template_name: "",
    }
  },
  methods: {
    onChange(value) {
      console.log(value);
    },
    submit() {
      let vm = this;
      axios.post('https://endpoint', {
        code: vm.code,
        template_name: vm.template_name
      })
        .then(response => {
          console.log(response)
        })
        .error(error => {
          console.log(error)
        })
    }
  }
}
</script>

<style>

</style>
