<template>
  <div class="btnList">
    <button
      v-for="(item, i) in parentData.dataLength"
      :key="i"
      :class="[
        'btnList__btn',
        { 'btnList__btn--active': i === parentData.pageIndex },
      ]"
      type="button"
      :data-page="item"
      @click="clickToSwitchCurPage(`${i}`)"
    >
      {{ item }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'BtnModule',
  props: {
    parentData: {
      type: Object,
    },
  },
  methods: {
    clickToSwitchCurPage(num) {
      this.$emit('update', parseInt(num, 10));
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btnList {
  padding: 0px 20px;
}

.btnList__btn {
  display: block;
  padding: 10px;
  font-size: 15px;
  color: #978795;
  text-decoration: none;
  border: none;
  background-color: transparent;
  cursor: pointer;
}

.btnList__btn--active {
  position: relative;
  font-weight: 700;
  color: #666666;
}

.btnList__btn--active::after {
  position: absolute;
  top: 0px;
  left: 30px;
  content: '|';
  font-size: 22px;
  font-weight: 900;
  color: #0075b0;
  vertical-align: top;
}
</style>
