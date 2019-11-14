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
      <!-- TODO: Add component for the table -->
      <!-- TODO: Add component for the chart -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

