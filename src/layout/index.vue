<template>
  <div :class="classObj" class="app-wrapper" :style="{'--current-color': theme}">
    <app-main />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { AppMain } from './components'
import ResizeMixin from './mixin/ResizeHandler'

export default {
  name: 'Layout',
  components: {
    AppMain,
  },
  mixins: [ResizeMixin],
  computed: {
    ...mapState({
      theme: state => state.settings.theme,
      device: state => state.app.device,
    }),
    classObj() {
      return {
        mobile: this.device === 'mobile'
      }
    },
  },
  methods: {
    
  }
}
</script>

<style lang="scss" scoped>
  @import "~@/assets/styles/mixin.scss";

  .app-wrapper {
    @include clearfix;
    position: relative;
    width: 100%;
  }
</style>
