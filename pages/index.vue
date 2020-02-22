<template>
  <div class="container">
    <div
      v-for="(note, index) in notes"
      :key="index"
      @mousedown.prevent="noteOn(note)"
      @touchstart.prevent="noteOn(note)"
      class="note"
      ontouchstart
    >{{note}}</div>
  </div>
</template>

<script>
import Tone from "tone";

export default {
  data: function() {
    return {
      synth: "",
      notes: [
        "C4",
        "D4",
        "E4",
        "F4",
        "G4",
        "A4",
        "B4",
        "C5",
        "D5",
        "E5",
        "F5",
        "G5",
        "A5",
        "B5",
        "C6",
        "D6"
      ]
    };
  },
  mounted: function() {
    this.synth = new Tone.Synth().toMaster();
  },
  methods: {
    noteOn: function(note) {
      this.synth.triggerAttackRelease(note, "8n");
    }
  }
};
</script>

<style lang="scss">
.container {
  height: 100vh;
  width: 100vw;
  display: grid;
  grid-template-rows: 1fr 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}

.note {
  border: 1px solid #fff;
  color: #fff;
  font-size: 3.6rem;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;

  &:hover {
    opacity: 0.9;
  }

  &:active {
    opacity: 0.8;
  }

  &:nth-child(1) {
    background: #c93a40;
  }

  &:nth-child(8) {
    background: saturate(#c93a40, 8%);
  }

  &:nth-child(15) {
    background: saturate(#c93a40, 32%);
  }

  &:nth-child(2) {
    background: #f2cf01;
  }

  &:nth-child(9) {
    background: saturate(#f2cf01, 8%);
  }

  &:nth-child(16) {
    background: saturate(#f2cf01, 32%);
  }

  &:nth-child(3) {
    background: #a0c238;
  }

  &:nth-child(10) {
    background: saturate(#a0c238, 8%);
  }

  &:nth-child(4) {
    background: #cc528b;
  }

  &:nth-child(11) {
    background: saturate(#cc528b, 8%);
  }

  &:nth-child(5) {
    background: #0074bf;
  }

  &:nth-child(12) {
    background: saturate(#0074bf, 8%);
  }

  &:nth-child(6) {
    background: #d16b16;
  }

  &:nth-child(13) {
    background: saturate(#d16b16, 8%);
  }

  &:nth-child(7) {
    background: #56a764;
  }

  &:nth-child(14) {
    background: saturate(#56a764, 8%);
  }
}
</style>
