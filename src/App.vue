<template>
  <div id="app">
    <text-editor-control titleSelect="Розмір тексту"
                         type="fontSize"
                         :styleObject="fontSize"></text-editor-control>
    <text-editor-control titleSelect="Колір тексту"
                         type="forecolor"
                         :styleObject="color"></text-editor-control>
    <text-editor-control titleSelect="Колір фону"
                         type="backColor"
                         :styleObject="backgroundColor"></text-editor-control>
    <my-editor :content="text" @update="text = $event"></my-editor>
  </div>
</template>

<script>
  import Editor from "@/components/Editor";
  import TextEditorControl from "@/components/TextEditorControl";

  document.execCommand("defaultParagraphSeparator", false, "p");
  export default {
    name: 'App',
    data() {
      return {
        text: 'Hi My lovely little Pony',
        fontSize: {
          1: 'Малюсенький',
          2: 'Маленький',
          3: 'Нормальний',
          4: 'Більший',
          5: 'Великий',
          6: 'Дуже великий',
          7: 'Гіганський'
        },
        color: {
          '#f8bbd0': 'Рожевий',
          '#880e4f': 'Коричневий',
          '#ba68c8': 'Фіолетовий',
          '#f8bb00': 'Жовтий',
          white: 'Білий'
        },
        backgroundColor: {
          '#f8bbd0': 'Рожевий',
          '#880e4f': 'Коричневий',
          '#ba68c8': 'Фіолетовий',
          '#f8bb00': 'Жовтий',
          white: 'Білий'
        }
      }
    },
    components: {
      'my-editor': Editor,
      'text-editor-control': TextEditorControl
    }
  }
</script>

<style scoped>
</style>
