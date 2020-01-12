<template>
  <div class="container">
    <div @mousedown="onMousedown('C4')" class="key">C4</div>
    <div @mousedown="onMousedown('D4')" class="key">D4</div>
    <div @mousedown="onMousedown('E4')" class="key">E4</div>
    <div @mousedown="onMousedown('F4')" class="key">F4</div>
    <div @mousedown="onMousedown('G4')" class="key">G4</div>
    <div @mousedown="onMousedown('A4')" class="key">A4</div>
    <div @mousedown="onMousedown('B4')" class="key">B4</div>
    <div @mousedown="onMousedown('C5')" class="key">C5</div>
    <div @mousedown="onMousedown('D5')" class="key">D5</div>
    <div @mousedown="onMousedown('E5')" class="key">E5</div>
    <div @mousedown="onMousedown('F5')" class="key">F5</div>
    <div @mousedown="onMousedown('G5')" class="key">G5</div>
    <div @mousedown="onMousedown('A5')" class="key">A5</div>
    <div @mousedown="onMousedown('B5')" class="key">B5</div>
    <div @mousedown="onMousedown('C6')" class="key">C6</div>
    <div @mousedown="onMousedown('D6')" class="key">D6</div>
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
    onMousedown: function(note) {
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

  @media screen and (max-width: 425px) {
  }
}

.key {
  border: 1px solid #fff;
  color: #fff;
  font-size: 3.6rem;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;

  &:nth-child(1) {
    background: #c93a40;
  }

  &:nth-child(8) {
    background: saturate(#c93a40, 4%);
  }

  &:nth-child(15) {
    background: saturate(#c93a40, 16%);
  }

  &:nth-child(2) {
    background: #f2cf01;
  }

  &:nth-child(9) {
    background: saturate(#f2cf01, 4%);
  }

  &:nth-child(16) {
    background: saturate(#f2cf01, 16%);
  }

  &:nth-child(3) {
    background: #a0c238;
  }

  &:nth-child(10) {
    background: saturate(#a0c238, 4%);
  }

  &:nth-child(4) {
    background: #cc528b;
  }

  &:nth-child(11) {
    background: saturate(#cc528b, 4%);
  }

  &:nth-child(5) {
    background: #0074bf;
  }

  &:nth-child(12) {
    background: saturate(#0074bf, 4%);
  }

  &:nth-child(6) {
    background: #d16b16;
  }

  &:nth-child(13) {
    background: saturate(#d16b16, 4%);
  }

  &:nth-child(7) {
    background: #56a764;
  }

  &:nth-child(14) {
    background: saturate(#56a764, 4%);
  }
}
</style>
