<template>
  <div class="home">
    <h1>Markdown Sorepponizer</h1>
    <p>{{ message }}</p>

    <div id="editor" class="col text_left">
      <CodeMirror v-model="text" width="600px" :options="cmOption" />
    </div>
    <div id="preview" class="col text_left">
      <textarea v-model="text" readonly />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { codemirror } from "vue-codemirror";
import "codemirror/lib/codemirror.css";
import "codemirror/mode/markdown/markdown";
import "codemirror/theme/monokai.css";

export default {
  name: "home",
  components: {
    CodeMirror: codemirror
  },
  data() {
    return {
      text: "",
      message: "いうほどそれっぽいか？",
      // この辺をユーザが任意で設定できるユーティリティを提供する
      cmOption: {
        connect: "align",
        mode: "text/markdown",
        theme: "monokai",
        lineWrapping: true,
        lineNumbers: true,
        autoFocus: true,
        collapseIdentical: false,
        highlightDifferences: true
      }
    };
  }
};
</script>
