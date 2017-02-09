<template>
  <div id="app">
    <div>Song: {{song}}</div>
    <div>
      <audio ref="audio">
        <source v-bind:src="'/music/'+song"></source>
      </audio>
    </div>
    <div>
      <div><a href="#" v-on:click.prevent="change_song('avril_girlfriend.mp3')">avril_girlfriend.mp3</a></div>
      <div><a href="#" v-on:click.prevent="change_song('Linkin Park - Somewhere I Belong.mp3')">Linkin Park - Somewhere I Belong.mp3</a></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  created: function(){
    console.log("Create function called");
  },
  data () {
    return {
      song: "avril_girlfriend.mp3",
      songs: []
    }
  },
  methods: {
    "change_song": function(s){
      this.song = s;
      this.$refs.audio.load();
      this.$refs.audio.play();
    }
  }
}
</script>

<style>
</style>
