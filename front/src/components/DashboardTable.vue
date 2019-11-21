<template>
  <div>
    <table class="table is-striped">
      <thead>
        <tr>
          <th>Date</th>
          <th>Peake Kwh</th>
          <th>Peake Price</th>
          <th>Off-Peake Kwh</th>
          <th>Off-Peake Price</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="entry in data" :key="entry.date">
          <td class="has-text-centered">{{entry.date}}</td>
          <td class="has-text-centered">{{entry.peak}}</td>
          <td class="has-text-centered"></td>
          <td class="has-text-centered">{{entry.offPeak}}</td>
          <td class="has-text-centered"></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    data: Array
  },
  data() {
    return {};
  }
};
</script>

