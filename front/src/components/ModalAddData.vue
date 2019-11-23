<template>
  <div>
    <modal>
      <p slot="title">{{ title }}</p>
      <button class="delete" slot="header-button" @click="close" aria-label="close"></button>
      <br />
      <table slot="body-infos" class="table is-striped">
        <tbody>
          <tr>
            <th>Date :</th>
            <td>
              <input v-model="bodyInfo.date" placeholder="Value" />
            </td>
          </tr>
          <tr>
            <th>Peak value :</th>
            <td>
              <input v-model="bodyInfo.peak" placeholder="Value" />
            </td>
          </tr>
          <tr>
            <th>Off-Peak value :</th>
            <td>
              <input v-model="bodyInfo.offPeak" placeholder="Value" />
            </td>
          </tr>
        </tbody>
      </table>
      <button class="button" slot="footer-button" @click="close">Cancel</button>
    </modal>
  </div>
</template>

<script>
import Modal from "./Modal.vue";

export default {
  components: {
    Modal
  },
  data() {
    return {
      isModalVisible: false,
      title: "",
      bodyInfo: {
        title: "",
        date: "",
        peak: 0,
        offPeak: 0
      }
    };
  },
  methods: {
    close() {
      this.$emit("close");
    }
  },
  mounted() {
    // TODO: Loads Config from axios
    this.title = "Add data";
    this.bodyInfo.title = "New values";
    this.bodyInfo.date = new Date().toLocaleDateString();
  }
};
</script>