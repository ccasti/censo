<template>
  <div class="modal">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">{{ details.name }}</p>
        <button 
          class="delete"
          aria-label="close"
          @click="closeModal"></button>
      </header>
      <section class="modal-card-body has-text-justified">
        <iframe class="region" :src=details.src frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
      </section>
      <footer class="modal-card-foot"></footer>
    </div>
  </div>
</template>

<script>

export default {

  props: {
    details: { type: Object, required: true }
  },

  methods: {

    closeModal () {

      setTimeout(() => {
        this.$emit('clickCloseModal')    
      }, 300)
    }

  }

}

</script>

<style lang="scss" scoped>

  .modal-card {
    width: 60%;
  }

  .modal-card-title {
    font-size: 1.5rem;
    color: #3C76BA;
    font-weight: bold;
  }

  .modal-card-body {
    padding: 0;
  }

  .region {
    width: 100%;
    aspect-ratio: 10 / 7;
  }

  .modal-card-foot {
    padding: 3px;
  }

  .delete {
    background-color: #3C76BA;
    color: #fff;
    opacity: .9;
  }

  .delete:hover {
    background-color: #3C76BA;
    color: #fff;
    opacity: 1;
  }

  @media screen and (max-width: 768px) {

    .modal-card-title {
      font-size: 1.02rem;
    }

    .delete {
      opacity: 1;
    }

  }

</style>