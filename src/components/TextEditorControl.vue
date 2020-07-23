<template>
  <select @input="changeText">
    <option selected>{{titleSelect}}</option>
    <option
      v-for="(value, key) in styleObject"
      :value="key"
      :key="key"
    >
      {{value}}
    </option>
  </select>
</template>

<script>
  export default {
    name: "text-editor-control",
    props: ['titleSelect', 'type', 'styleObject'],
    methods:{
      changeText(event) {
        document.execCommand(this.type, false, event.target.value);
      }
    }
  }
</script>

<style scoped>

</style>