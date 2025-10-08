<template>
  <div>
    {{ result?.data.message }}
  </div>
</template>

<script setup lang="ts">
type Message = {
  data: {
    message: string
  }
}

const result = ref<Maybe<Message>>(null)

onMounted(async () => {
   try {
     result.value = await $fetch<Message>('http://localhost:3001/', {
       method: 'GET',
     })
   } catch (e) {
     console.error(e)
   }

   try {
     result.value = await $fetch<Message>('http://localhost:3001/strings/1', {
       method: 'GET',
     })
   } catch (e) {
     console.error(e)
   }
})
</script>
