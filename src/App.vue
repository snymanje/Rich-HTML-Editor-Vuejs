<template>
   <div id="app">
     <vue-editor v-model="content" 
      :editorToolbar="customToolbar" 
      :editorOptions="editorSettings">
    </vue-editor>
   </div>
 </template>

 <script>
   import { VueEditor } from 'vue2-editor'
   import hljs from "highlight.js";
   import "highlight.js/styles/atom-one-dark.css";

   export default {

   components: {
      VueEditor
   },

   data() {
       return {
         content: '<h1>Some initial content</h1>',

         customToolbar: [
          ["bold", "italic", "underline", "strike"],
          ["blockquote", "code-block"],
          [{ header: 1 }, { header: 2 }],
          [{ list: "ordered" }, { list: "bullet" }],
          [{ script: "sub" }, { script: "super" }],
          [{ indent: "-1" }, { indent: "+1" }],
          [{ direction: "rtl" }],
          [{ size: ["small", false, "large", "huge"] }],
          [{ header: [1, 2, 3, 4, 5, 6, false] }],
          [{ font: [] }],
          [{ color: [] }, { background: [] }],
          [{ align: [] }],
          ["clean"],
          ["link", "image", "video"]
        ],
        editorSettings: {
        modules: {
          syntax: {
            highlight: text => hljs.highlightAuto(text).value
          }
        }
      }
       }
     }
   }
 </script>