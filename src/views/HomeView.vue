<script lang="ts" setup>
import { defineCustomElement } from "vue";

import MyLabel from "./MyLabel.ce.vue";

customElements.define("my-label", defineCustomElement(MyLabel));



</script>

<template>
  <main>
    <my-label text="test" :count="5" :extra-settings="{ name: 'john' }"></my-label> 
  </main>
</template>
<style lang="scss">

</style>
