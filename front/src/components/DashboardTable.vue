<template>
  <div>
    <table class="table is-striped">
      <thead>
        <tr>
          <th>Date</th>
          <th>Kwh heure pleine</th>
          <th>Prix heure pleine</th>
          <th>Kwh heure creuse</th>
          <th>Prix heure creuse</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="entry in data" :key="entry.date">
          <td class="has-text-centered">{{entry.date}}</td>
          <td class="has-text-centered">{{entry.hPleines}}</td>
          <td class="has-text-centered"></td>
          <td class="has-text-centered">{{entry.hCreuses}}</td>
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

