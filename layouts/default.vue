<template>
  <div class="primary">
    <div class="primary__template template">
      <div class="template__header">
        <TheHeader />
      </div>
      <div class="template__content">
        <div class="template__container">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Default',
  components: {}
}
</script>

<style lang="scss" scoped>
.primary {
  height: 100vh;
  overflow-y: auto;
  width: 100%;
  &__template {
    height: 60px;
    display: grid;
    grid-template-rows: 60px 1fr auto;
  }
}
.template {
  font-family: "Roboto", sans-serif;
  min-height: 100vh;
  overflow: auto;
  &__content {
    display: flex;
    width: 100%;
    overflow-y: auto;
    color: black;
    background-color: white;
  }
  &__container {
    font-size: 14px;
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: center;
  }
  &__header {
    height: 80px;
    width: 100%;
  }
}
</style>
