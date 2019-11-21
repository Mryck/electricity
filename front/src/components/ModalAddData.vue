<template>
  <div>
    <modal>
      <p slot="title">{{ title }}</p>
      <button class="delete" slot="header-button" @click="close" aria-label="close"></button>
      <p class="content" slot="body">{{ bodyInfo.details }}</p>
      <br />
      <table slot="body-infos" class="table is-striped">
        <tbody>
          <tr>
            <th>Entry One</th>
            <td>{{ bodyInfo.details }}</td>
          </tr>
          <tr>
            <th>Entry Two</th>
            <td>{{ bodyInfo.details }}</td>
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
        details: ""
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
  }
};
</script>