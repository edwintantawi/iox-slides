---
layout: fact
---

<!-- <h1
      v-motion
      :duration="1000"
      :initial="{ scale: 0 }"
      :enter="{ scale: 1 }"
      :leave="{ scale: 0 }"
    >
      Daging 🍖
</h1> -->

<v-switch>
<template #0>
  <h1
    v-motion
    :duration="1000"
    :initial="{ scale: 0 }"
    :enter="{ scale: 1 }"
  >
    Daging 🍖
  </h1>
  </template>
  <template #1>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-1="{ scale: 1 }"
    >
      Wagyu 😋
    </h1>
  </template>
  <template #2-3>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-2="{ scale: 1 }"
    >
      A6 😳
    </h1>
  </template>
  <template #3>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-3="{ scale: 1 }"
    >
      ASIX 😂
    </h1>
  </template>
  <template #4>
    <h1 
      v-motion
      :duration="500"
      :initial="{ scale: 0 }"
      :click-4="{ scale: 1 }"
    >
      ASIK 😁
    </h1>
  </template>
</v-switch>
