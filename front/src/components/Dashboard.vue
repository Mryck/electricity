<template>
  <div>
    <section class="hero is-info">
      <div class="hero-head">
        <nav class="navbar">
          <div class="container">
            <div id="navbarMenuHeroA" class="navbar-menu">
              <div class="navbar-start">
                <span class="navbar-item">
                  <h1 class="title">Electricity dashboard</h1>
                </span>
              </div>
              <div class="navbar-end">
                <span class="navbar-item">
                  <a class="button is-info is-inverted" @click="addData">Add data</a>
                </span>
                <span class="navbar-item">
                  <a class="button is-info is-inverted" @click="config">Config</a>
                </span>
              </div>
            </div>
          </div>
        </nav>
      </div>
    </section>
    <br />
    <div class="container">
      <dashboard-table :data="rawData"></dashboard-table>
      <dashboard-chart :data="chartData"></dashboard-chart>
    </div>
  </div>
</template>

<script>
import DashboardChart from "./DashboardChart.vue";
import DashboardTable from "./DashboardTable.vue";

export default {
  components: {
    DashboardChart,
    DashboardTable
  },
  data() {
    return {
      chartData: Object,
      rawData: [
        { date: "1-10-19", offPeak: 15000, peak: 31000 },
        { date: "1-11-19", offPeak: 16000, peak: 32000 },
        { date: "1-12-19", offPeak: 17000, peak: 33000 }
      ]
    };
  },
  methods: {
    addData() {},
    config() {}
  },
  created() {
    let xAxis = [];
    let peak = [];
    let offPeak = [];

    this.rawData.forEach(element => {
      xAxis.push(element.date);
      peak.push(element.peak);
      offPeak.push(element.offPeak);
    });

    this.chartData = {
      labels: xAxis,
      datasets: [
        {
          label: "Peak",
          backgroundColor: "#4e65d8",
          data: peak
        },
        {
          label: "Off-Peak",
          backgroundColor: "#4ed862",
          data: offPeak
        }
      ]
    };
  },
  mounted() {
    // TODO: Loads data from axios
  }
};
</script>

