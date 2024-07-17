---
layout: section
transition: view-transition
---

<style>
  .title {
    view-transition-name: title;
  }
  .image {
    view-transition-name: image;
  }
</style>

<h1 class="flex flex-items-center gap-6">
  <v-switch>
    <template #0-1>
      <img src="/firebase-old.svg" class="size-24"/>
    </template>
    <template #1>
      <img src="/firebase.svg" class="image size-24"
        v-motion
        :duration="1000"
        :initial="{ scale: 0 }"
        :click-1="{ scale: 1 }"/>
    </template>
  </v-switch>
  <span class="title">Firebase</span>
</h1>

---
layout: fact
---

<h1>
  <span class="gemini-text">Vertex AI</span> For 
</h1>
<h1 class="flex items-center justify-center gap-2">
  <img src="/firebase.svg" class="image size-24"/><span class="title firebase-text">Firebase</span>
</h1>
