<template>
    <div id="app" class="container">
      <InputForms @submit="onSubmit" msg="Aplication List"/>
      <OutputForm  msg="Complete List" v-bind="formData"/>
    </div>
</template>

<script>

import InputForms from './components/InputForms.vue'
import OutputForm from './components/OutputForms.vue'
export default {
  name: 'App',
  components: {
    InputForms,
    OutputForm
  },
  data(){
    return{
      formData:{}
    }
  },
  methods:{
    onSubmit(formData){
      this.formData=formData
    }
  }
}
</script>

<style>
body{
  margin: 0;
  background-image: linear-gradient(to top, #a8edea 0%, #fed6e3 100%);
}

.container{
  display: flex;
  justify-content: space-between;
}
</style>
