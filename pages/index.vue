<template>
  <div @click="handleClick()" class="container">
    <span>CLICK!</span>
  </div>
</template>

<script>
import Tone from "tone";

export default {
  data: function() {
    return {
      synth: ""
    };
  },
  mounted: function() {
    this.synth = new Tone.Synth().toMaster();
  },
  methods: {
    handleClick: function() {
      this.synth.triggerAttackRelease("C6", "8n");
    }
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  cursor: pointer;
}
</style>
