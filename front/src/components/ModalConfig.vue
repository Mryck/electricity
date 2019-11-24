<template>
  <div>
    <modal>
      <p slot="title">{{ title }}</p>
      <button class="delete" slot="header-button" @click="close" aria-label="close"></button>
      <br />
      <table slot="body-infos" class="table is-striped">
        <tbody>
          <tr>
            <th>Peak price :</th>
            <td>
              <input v-model="bodyInfo.peakPrice" placeholder="Value" />
            </td>
          </tr>
          <tr>
            <th>Off-Peak price :</th>
            <td>
              <input v-model="bodyInfo.offPeakPrice" placeholder="Value" />
            </td>
          </tr>
          <tr>
            <th>Other taxes (%) :</th>
            <td>
              <input v-model="bodyInfo.taxes" placeholder="Value" />
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
        peakPrice: "",
        offPeakPrice: "",
        taxes: 0
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
    this.title = "Configuration";
  }
};
</script>