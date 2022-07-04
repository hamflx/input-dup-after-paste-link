<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import StarterKit from '@tiptap/starter-kit'
import { Link } from '@tiptap/extension-link'
import { Editor } from '@tiptap/core'
import { onMounted } from 'vue';

onMounted(() => {
  new Editor({
    element: document.querySelector('.tiptap-editor'),
    extensions: [
      StarterKit,
      Link.configure({
        autolink: false,
        openOnClick: false,
        linkOnPaste: false
      })
    ],
    content: '',
  })
})
</script>

<template>
  <div class="container">
    <div class="tiptap-editor"></div>
    <div class="bug-description">
      <ol>
        <li>Copy http://localhost:3000/</li>
        <li>Click on the editor area</li>
        <li>Paste http://localhost:3000/</li>
        <li>Enter the full-angle character ","</li>
        <li>It will show two characters, if not, try again</li>
      </ol>
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 20px;
}

html,
body,
#app,
.container,
.tiptap-editor,
.ProseMirror {
  height: 100%;
  display: flow-root;
  box-sizing: border-box;
}

.container {
  display: flex;
}

.bug-description,
.tiptap-editor {
  flex: 1;
}

.ProseMirror {
  padding: 12px;
}
</style>
