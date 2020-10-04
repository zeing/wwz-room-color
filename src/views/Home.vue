<template>
  <div class="home" :style="styleBg" @click="changeToggle">
  </div>
</template>

<script lang="js">
import { Vue } from 'vue-property-decorator';

export default Vue.extend({
  data: () => ({
    toggle: false,
  }),
  computed: {
    styleBg() {
      if (this.toggle) { return { backgroundColor: '#3C413D' }; }
      return { backgroundColor: '#37433a' };
    },
  },
  methods: {
    changeToggle() {
      this.toggle = !this.toggle;
    },
  },
});
</script>

<style lang="stylus">
.home {
  min-height :100vh;
}
</style>
