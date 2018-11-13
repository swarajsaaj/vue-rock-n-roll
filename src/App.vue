<template>
  <div id="app">
    Welcome to Rock N Roll

    <BandsList> </BandsList>
  </div>
</template>

<script>
import BandsList from '@/components/BandsList.vue'

export default {
  name: 'app',
  components: {
    BandsList
  }

}
</script>

<style>

</style>
