<template>
<div>
  <fullscreen ref="fullscreen" @change="fullscreenChange">
    <div class="home" :style="styleBg" @click="changeToggle">
      {{styleText}}
    </div>
    <div type="button" @click="toggles" class="toogleBtn">{{toggleText}}</div>

  </fullscreen>
</div>
</template>

<script lang="js">
import { Vue } from 'vue-property-decorator';
import fullscreen from 'vue-fullscreen';

Vue.use(fullscreen);

export default Vue.extend({
  data: () => ({
    toggle: false,
    fullscreen: false,
  }),
  computed: {
    styleBg() {
      if (this.toggle) { return { backgroundColor: '#3C413D' }; }
      return { backgroundColor: '#37433a' };
    },
    styleText() {
      if (this.toggle) return '#3C413D';
      return '#37433a';
    },
    toggleText() {
      if (this.fullscreen) return 'Exit fullscreen';
      return 'Click fullscreen';
    },
  },
  methods: {
    changeToggle() {
      this.toggle = !this.toggle;
    },
    toggles() {
      this.$refs.fullscreen.toggle(); // recommended
    },
    fullscreenChange(fullscreens) {
      this.fullscreen = fullscreens;
    },
  },
});
</script>

<style lang="stylus">
.home {
  min-height 100vh;
  cursor pointer;
  display flex;
  justify-content center;
  align-items center;
  color black;
  position relative
}

.toogleBtn {
  background-color transparent
  outline none
  position absolute
  right 40px
  top 40px
  color black
  cursor pointer;
}
</style>
