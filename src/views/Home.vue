<template>
  <v-container pa-0>
    <v-container class="text-center">
      <h1>Markdown Sorepponizer</h1>
      <p>{{ message }}</p>
    </v-container>

    <v-row>
      <v-col cols="12" sm="6" id="editor" class="col text_left">
        <CodeMirror v-model="text" width="600px" :options="cmOption" />
      </v-col>
      <v-col cols="12" sm="6" id="preview" class="col text_left">
        <textarea v-model="text" readonly />
      </v-col>
    </v-row>
  </v-container>
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
