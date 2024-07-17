---
layout: fact
---

<v-switch>
  <template #1>
    <h1
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-1="{ scale: 1 }"
    >
      Hai...
    </h1>
  </template>
  <template #2>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-2="{ scale: 1 }"
    >
      Apa Kabar?
    </h1>
  </template>
  <template #3>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-3="{ scale: 1 }"
    >
      Bohong!!!
    </h1>
  </template>
</v-switch>

---
layout: image
image: "/sleepy-cat.gif"
---

<style>
  .slidev-layout {
    background-size: contain !important;
  }

  .light h1 {
   color:black;
  }
  .dark h1 {
    color: white;
  }
</style>

# Ngantuk berat

---
layout: fact
---

<v-switch>
 <template #0>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :enter="{ scale: 1 }"
    >
      Lanjut Makan 🤤
    </h1>
  </template>
 <template #1>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-1="{ scale: 1 }"
    >
      Daging 🍖
    </h1>
  </template>
  <template #2>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-2="{ scale: 1 }"
    >
      Wagyu 😋
    </h1>
  </template>
  <template #3>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-3="{ scale: 1 }"
    >
      A6 😳
    </h1>
  </template>
  <template #4>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-4="{ scale: 1 }"
    >
      ASIX 😂
    </h1>
  </template>
  <template #5>
    <h1 
      v-motion
      :duration="500"
      :initial="{ opacity: 0 }"
      :click-5="{ opacity: 1 }"
    >
      ASI<span class="color-slate opacity-10">X</span>K 😁
    </h1>
  </template>
</v-switch>

---
layout: fact
---

## Hi... I'm

<h1
  v-motion
  :duration="1000"
  :initial="{ opacity: 0 }"
  :enter="{ opacity: 1 }"
  class="gemini-text"
>
  Edwin Tantawi
</h1>

---
layout: statement
image: "/topremit.svg"
class: flex flex-col justify-center
---

<style>
  .light .st2{fill:#2E4865;}
  .dark .st2{fill:#FFFFFF !important;}
</style>

<h2>Web <span class="topremit-text">Front-End Engineer</span> At</h2>
<Topremit class="w-100 mx-auto mt-4"/>

---
layout: statement
---

<h2>Ex-1st Google Developer Student Clubs Lead 2023</h2>
<h1 class="mt-4 mikroskil-text">Universitas Mikroskil</h1>

---
layout: statement
---

# Love <span class="topremit-text">Frontend</span> & <span class="line-through color-slate">You</span> <span class="firebase-text">Cat</span> 🐈

<p class="text-slate">"Feel free to talk, discuss and learn together with me about frontend and cat memes"</p>
