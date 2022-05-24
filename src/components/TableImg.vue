<template>
  <td class="res__td res__td--img">
    <img
      class="res__img res__img--small"
      src="${item.PicURL}"
      width="400"
      height="267"
    />
    <img
      class="res__img res__img--large"
      src="${item.PicURL}"
      width="400"
      height="267"
    />
  </td>
</template>

<script>
export default {
  name: 'TableImg',

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
.res__td--img {
  position: relative;
}

.res__img {
  vertical-align: middle;
}

.res__img--small {
  width: 80px;
  height: auto;
}

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
