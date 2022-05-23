<template>
  <div id="app">
    <header class="hd">
      <h1 class="hd__title">農村地方美食小吃特色料理</h1>
    </header>
    <div class="container">
      <TableComponent :parent-data="paginationData[curPage]" />
    </div>
  </div>
</template>

<script>
import TableComponent from './components/TableComponent.vue';

export default {
  name: 'App',
  data() {
    return {
      jsonData: [],
      paginationData: [],
      curPage: 0,
      showAmount: 10,
    };
  },

  async created() {
    this.jsonData = await this.fetchData();
    this.dataPagination();
  },

  methods: {
    async fetchData() {
      const dataUrl =
        'https://data.coa.gov.tw/Service/OpenData/ODwsv/ODwsvTravelFood.aspx';
      try {
        const res = await this.$http.get(dataUrl);
        return res.data;
      } catch (e) {
        console.log(e.message);
      }
    },

    dataPagination(arr = []) {
      this.jsonData.forEach((item, i) => {
        arr.push(item);
        if ((i + 1) % this.showAmount === 0) {
          this.paginationData.push(arr.splice(0));
        } else if (i + 1 === this.jsonData.length) {
          this.paginationData.push(arr);
        }
      });
    },
  },

  components: {
    TableComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.mx-auto {
  margin-right: auto;
  margin-left: auto;
}

.container {
  width: 900px;
  box-sizing: border-box;
}

.grid {
  display: flex;
}

.hd {
  padding-top: 20px;
  padding-bottom: 20px;
}
/* --- Modules --- */

.hd__title {
  font-size: 30px;
  font-weight: 600;
  text-align: center;
}
</style>
