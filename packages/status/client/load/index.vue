<template>
  <k-status>
    <template #tooltip>
      <div class="load">
        <load-bar title="CPU" :rate="store.profile.cpu"/>
        <load-bar title="内存" :rate="store.profile.memory"/>
      </div>
    </template>
    CPU: {{ percentage(store.profile.cpu[1], 0) }}
    内存: {{ percentage(store.profile.memory[1], 0) }}
  </k-status>
</template>

<script setup lang="ts">

import LoadBar from './load-bar.vue'
import { store } from '@koishijs/client'
import { percentage } from './utils'

</script>

<style lang="scss" scoped>

.load {
  padding: 0.25rem 1rem;
}

</style>
