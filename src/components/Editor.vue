<template>
  <div contenteditable="true" @input="update"></div>
</template>

<script>
  export default {
    name: 'my-editor',
    props:['content'],
    mounted: function() {
      this.$el.innerText = this.content;
    },
    methods:{
      update(event) {
        this.$emit('update', event.target.innerText);
      }
    }
  }
</script>

<style scoped>

</style>