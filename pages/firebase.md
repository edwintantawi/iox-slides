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
layout: section
transition: view-transition
---

# <span class="title firebase-text">Firebase</span> Accelerate The Development With Managed Infrastructure That Can _Scale Globally_, Powered By <span class="vertex-ai-text">Google Cloud</span>

---
layout: section
transition: view-transition
---

# <span class="title firebase-text">Firebase</span> Let Developer Focus On What Matters Most And _Get To Market Quickly_

---
layout: fact
transition: view-transition
---

<style>
  .title {
    view-transition-name: title;
  }
  .title-vertex-ai-1 {
    view-transition-name: title-vertex-ai-1;
  }
  .title-vertex-ai-2 {
    view-transition-name: title-vertex-ai-2;
  }
</style>

<h1>
  <span class="relative"><span class="title-vertex-ai-1 vertex-ai-text">Vertex AI</span> <span class="title-vertex-ai-2 vertex-ai-text absolute left-0">Vertex AI</span></span> For 
</h1>
<h1 class="flex items-center justify-center gap-2">
  <img src="/firebase.svg" class="image size-24"/><span class="title title-firebase firebase-text">Firebase</span>
</h1>

---
layout: section
transition: view-transition
---

# Calls to the <span class="title-vertex-ai-1 vertex-ai-text">Vertex AI</span> Gemini API directly from your app using the <span class="title-vertex-ai-2 vertex-ai-text">Vertex AI</span> for <span class="title firebase-text">Firebase</span> SDKs.

---
layout: section
transition: view-transition
---

# Allow Us To Call The <span class="title-vertex-ai-1 vertex-ai-text">Vertex AI</span> <span class="gemini-text">Gemini API</span> Directly From Our Apps, _Removing The Need To Set Up A Backend_ With <span class="title title-firebase firebase-text">Firebase</span>

---
layout: statement
---

# <span class="title-vertex-ai-1 gemini-text">Vertex AI</span> For <span class="title firebase-text">Firebase</span><br/> Is In Preview!

<p class="text-slate">which means that the product is not subject to any SLA or deprecation policy<br/>and could change in backwards-incompatible ways.</p>
