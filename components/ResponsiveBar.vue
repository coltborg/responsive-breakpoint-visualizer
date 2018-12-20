<template>
  <div class="text-black text-2xl">Responsive Bar - {{ windowSize }}</div>
</template>

<script>
export default {
  name: 'ResponsiveBar',
  data() {
    return {
      name: undefined,
      windowSize: 0,
    };
  },
  mounted() {
    this.getBodyWidth();
    window.addEventListener('resize', this.getBodyWidth);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.getBodyWidth);
  },
  methods: {
    getBodyWidth() {
      console.log('width');
      this.windowSize = window.innerWidth;
    },
  },
};
</script>

<style></style>
