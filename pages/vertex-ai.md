---
layout: section
transition: view-transition
---

<style>
  .title {
    view-transition-name: title;
  }
</style>

<h1 class="flex flex-items-center gap-2">
  <img src="/vertex-ai.svg" class="size-24"/>
  <span class="title">Vertex AI</span>
</h1>

---
layout: section
---

<h1><span class="title vertex-ai-text">Vertex AI</span> is a Fully-Managed, Unified AI Development Platform For Building And Using
  <v-switch>
    <template #0 >
    <span>
      Generative AI
    </span>
    </template>
    <template #1 >
    <h1 v-motion
      :duration="800"
      :initial="{ opacity: 0 }"
      :click-1="{ opacity: 1 }">
    <span class="gemini-text">
      Gemini AI
    </span>
    </h1>
    </template>
  </v-switch>
</h1>

---
layout: section
class: text-center
---

<h2 class="text-slate mb-2">Bruhhh Dealing With Frontend Is Already Very Annoying...</h2>

# Now, I Don't Want To Deal With Servers Anymore 😣
