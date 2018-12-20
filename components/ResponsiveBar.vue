<template>
  <div class="text-black text-2xl text-center tv:bg-teal hd:bg-red">{{ name }} - {{ windowSize }}</div>
</template>

<script>
export default {
  name: 'ResponsiveBar',
  data() {
    return {
      windowSize: 0,
    };
  },
  computed: {
    name() {
      if (this.windowSize >= 1920) {
        return 'hd';
      }
      if (this.windowSize >= 1440) {
        return 'xl';
      }
      if (this.windowSize >= 1024) {
        return 'lg';
      }
      if (this.windowSize >= 960) {
        return 'md';
      }
      if (this.windowSize >= 600) {
        return 'sm';
      }
      if (this.windowSize >= 360) {
        return 'xs';
      }
      return 'none';
    }
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
