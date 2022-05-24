<template>
  <img class="res__img--large" />
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
.res__img--large {
  position: absolute;
  left: 110%;
  top: 10px;
  z-index: 1;
  width: 300px;
  height: auto;
  padding: 10px;
  background-color: #fff;
  box-shadow: 0px 0px 4px 1px rgb(180, 178, 178);
  box-sizing: border-box;
}
</style>
