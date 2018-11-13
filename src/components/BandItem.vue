<template>
  <li @click="toggle">
    {{band.name}}

    <p v-show="open">
      {{band.songs | join}}
      <input type="text" placeholder="Add more songs..." @click.stop @keyup.enter="addSong" v-model="newSong"> 
    </p>

  </li>
</template>


<script>
export default {
  name: 'BandItem',
  data () {
    return {
      newSong: '',
      open: false
    }
  },
  props: {
    band: Object
  },
  filters: {
    join (arr) {
      return arr.join(', ')
    }
  },
  methods: {
    toggle () {
      this.open = !this.open
    },
    addSong () {
      this.band.songs.push(this.newSong)
      this.newSong = ''
    }
  }
}
</script>
