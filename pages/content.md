---
layout: cover
class: text-center
transition: view-transition
---

<style>
  .title {
    view-transition-name: title;
  }
  .image {
    view-transition-name: image;
  }
  .vertex-ai-title {
    view-transition-name: vertex-ai-title;
  }
</style>

# Build <i>AI-powered</i> apps <br/> with the <span class="gemini-text">Gemini API</span> using <span class="vertex-ai-title">Vertex AI</span> for <span class="title firebase-text">Firebase</span>

<p class="color-slate">
  Google I/O Extended Medan 2024
</p>

<section class="grid grid-cols-3 grid-items-center grid-justify-items-center mt-24 min-h-50">
  <v-click at="1">
    <img src="/gemini.svg" class="size-30"/>
  </v-click>

  <v-switch transition="true">
    <template #3><img src="/firebase-old.svg" class="size-50"/></template>
    <template #4-5>
      <img src="/firebase.svg" class="image size-50"/>
    </template>
  </v-switch>

  <v-click at="2">
    <img src="/vertex-ai.svg" class="size-30"/>
  </v-click>
</section>
