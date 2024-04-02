<script setup>
import Head from '@/components/Head.vue';
import Presentation from '@/components/Presentation.vue';
import Foot from '@/components/Foot.vue';
import Creation from '@/components/Creation.vue';
import Contact from '@/components/Contact.vue';
</script>

<template>
  <header>
    <Head/>
  </header>

  <main>
    <Presentation/>
    <Creation/>
    <Contact/>

  </main>

  <footer>
    <Foot/>
  </footer>
</template>

<style>

</style>