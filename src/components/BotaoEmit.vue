<template>
  <div>
      <button class="btn btn-success" @click="$emit('mudandoGo')">Mudar texto</button>
  </div>
</template>

<script>
export default {
    name: 'BotaoEmit',
    emits: ['mudandoGo']
}
</script>

<style>

</style>