<template>
  <div class="EventInfo" :class="{ hidden, 'full-width': isHome }">
    <a href="https://ej2.syncfusion.com/vue/documentation/Grid/getting-started.html" target="_blank" rel="noopener" style="color: black;">Grid</a>      
  </div>
</template>

<script>
const dateUntil = new Date('2018-11-11')

export default {
  data() {
    return { hidden: true }
  },
  computed: {
    isHome() {
      return this.$route.path === '/'
    }
  },
  mounted() {
    if (Date.now() <= dateUntil) {
      this.hidden = false
    }
  }
}
</script>

<style lang="scss" scoped>
/* See https://davidwalsh.name/css-slide */
.EventInfo {
  overflow: hidden;
  text-align: center;
  padding: 10px;
  background-color: #f9f9f9;
  opacity: 1;
  transition-property: all;
  transition-duration: 0.5s;
  padding-right: 60px;
  @media (min-width: 992px) {
    padding-left: 300px;
  }
  &.full-width {
    padding-left: 10px;
    padding-right: 10px;
  }
  &.hidden {
    visibility: hidden;
    opacity: 0;
  }
  a {
    color: #fff;
    font-weight: 600;
  }
}
</style>
