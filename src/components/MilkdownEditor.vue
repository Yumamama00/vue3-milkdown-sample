<template>
  <VueEditor :editor="editor" />
</template>

<script setup lang="ts">
// core
import { VueEditor, useEditor } from "@milkdown/vue";
import { Editor, rootCtx, defaultValueCtx } from "@milkdown/core";
import { nord } from "@milkdown/theme-nord";
import { commonmark } from "@milkdown/preset-commonmark";

// plugin
import { emoji } from "@milkdown/plugin-emoji";
import { menu } from "@milkdown/plugin-menu";
import { slash } from "@milkdown/plugin-slash";
import { history } from "@milkdown/plugin-history";
import { prism } from "@milkdown/plugin-prism";
import { tooltip } from "@milkdown/plugin-tooltip";
import { indent } from "@milkdown/plugin-indent";
import { trailing } from "@milkdown/plugin-trailing";
import { upload } from "@milkdown/plugin-upload";
import { cursor } from "@milkdown/plugin-cursor";
import { clipboard } from "@milkdown/plugin-clipboard";

const { editor } = useEditor((root) =>
  Editor.make()
    .config((ctx) => {
      ctx.set(rootCtx, root);
      ctx.set(defaultValueCtx, "Milkdown + Vue3");
    })
    .use(nord)
    .use(emoji)
    .use(slash)
    .use(commonmark)
    .use(menu)
    .use(history)
    .use(prism)
    .use(tooltip)
    .use(indent)
    .use(trailing)
    .use(upload)
    .use(cursor)
    .use(clipboard)
);
</script>
