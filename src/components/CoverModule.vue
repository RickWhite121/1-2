<template>
  <div class="Cover"></div>
</template>

<script>
export default {
  name: 'CoverModule',

  methods: {
    // clickToCloseList() {
    //   this.$emit('update');
    // },
  },
  components: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Cover {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-color: rgba(14, 13, 13, 0.507);
}
</style>
