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
$c-note: #c93a40;
$d-note: #f2cf01;
$e-note: #a0c238;
$f-note: #cc528b;
$g-note: #0074bf;
$a-note: #d16b16;
$b-note: #56a764;

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
    background: $c-note;
  }

  &:nth-child(8) {
    background: saturate($c-note, 8%);
  }

  &:nth-child(15) {
    background: saturate($c-note, 32%);
  }

  &:nth-child(2) {
    background: $d-note;
  }

  &:nth-child(9) {
    background: saturate($d-note, 8%);
  }

  &:nth-child(16) {
    background: saturate($d-note, 32%);
  }

  &:nth-child(3) {
    background: $e-note;
  }

  &:nth-child(10) {
    background: saturate($e-note, 8%);
  }

  &:nth-child(4) {
    background: $f-note;
  }

  &:nth-child(11) {
    background: saturate($f-note, 8%);
  }

  &:nth-child(5) {
    background: $g-note;
  }

  &:nth-child(12) {
    background: saturate($g-note, 8%);
  }

  &:nth-child(6) {
    background: $a-note;
  }

  &:nth-child(13) {
    background: saturate($a-note, 8%);
  }

  &:nth-child(7) {
    background: $b-note;
  }

  &:nth-child(14) {
    background: saturate($b-note, 8%);
  }
}
</style>
