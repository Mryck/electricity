<template>
  <transition name="modal-fade">
    <div class="modal is-active" role="dialog">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title has-text-centered">
            <slot name="title"></slot>
          </p>
          <slot name="header-button"></slot>
        </header>
        <section class="modal-card-body">
          <slot name="body"></slot>
          <slot name="body-infos"></slot>
        </section>
        <footer class="modal-card-foot">
          <slot name="footer-button"></slot>
        </footer>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "modal",

};
</script>

<style>
.modal-fade-enter,
.modal-fade-leave-active {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.5s ease;
}
</style>
