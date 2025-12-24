<template>
  <container>
    <div class="info">
      {{ currentUser?.username }}
    </div>
    <div>
      collectors
    </div>
  </container>
</template>

<script setup lang="ts">
import { useUserStore } from '@/store/user'

const { currentUser } = storeToRefs(useUserStore())
</script>

<style scoped lang="scss">

</style>
