<template>
  <main class="main">
    <table class="res">
      <thead class="res__hd">
        <tr class="res__title">
          <th class="res__th">編號</th>
          <th class="res__th">行政區</th>
          <th class="res__th">圖片</th>
          <th class="res__th">名稱</th>
          <th class="res__th">介紹</th>
        </tr>
      </thead>
      <tbody class="res__content" id="ResContent">
        <tr
          v-for="(item, i) in parentData"
          :key="item.ID"
          :class="['res__row', `${i % 2 === 0 ? '' : ' res__row--stripe'}"
        >
          <td class="res__td res__td--textCenter res__td--order">
            ${curPage * showAmount + i + 1}
          </td>
          <td class="res__td">${item.City}</td>
          <td class="res__td res__td--img">
            <img
              class="res__img res__img--small"
              src="${item.PicURL}"
              width="400"
              height="267"
            />
          </td>
          <td class="res__td res__td--fixed">
            ${item.Url === '' ? `${item.Name}` : `<a
              class="res__link"
              target="_blank"
              href="${item.Url}"
              >${item.Name}</a
            >`}
          </td>
          <td class="res__td">${textLimit(item.FoodFeature)}</td>
        </tr>
      </tbody>
    </table>
  </main>
</template>

<script>
export default {
  name: 'TableComponent',
  props: {
    parentData: {
      type: Array,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  width: 93%;
  padding-bottom: 30px;
}

.res {
  width: 100%;
}

.res__title {
  background: linear-gradient(#f6f8f8, #eaebeb);
  border-bottom: 2px solid #cbcbcb;
}

.res__th {
  padding: 10px;
  font-size: 15px;
  border: 1px solid #cbcbcb;
  color: #8a8787;
  font-weight: 600;
  white-space: nowrap;
}

.res__row {
  height: 75px;
}

.res__row--stripe {
  background-color: #f9f9f9;
}

.res__row:hover {
  background-color: #eef2f7;
}

.res__td {
  position: relative;
  padding: 5px 10px;
  height: 70px;
  font-size: 15px;
  border: 1px solid #dfdddd;
  vertical-align: middle;
  box-sizing: border-box;
}

.res__link {
  color: #3494c4;
}

.res__link:visited {
  color: #247baa;
}

.res__td--order {
  font-size: 13px;
  color: #a4a4a7;
}

.res__td--img {
  position: relative;
}

.res__td--fixed {
  width: 175px;
}

.res__td--textCenter {
  text-align: center;
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
