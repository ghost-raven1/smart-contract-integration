<template>
  <div class="header">
    <div class="header__container">
      <div class="header__logo">
        <div class="logo">
          Cr
        </div>
      </div>
      <div>
        <button class="btn__connect">
          Connect wallet
        </button>
        <div class="header__color-mode-picker">
          <!--      <mode-toggle />-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>

.header {
  position: fixed;
  top: 0;
  left: 0;
  height: 67px;
  width: 100%;
  display: flex;
  background: #3C3C3C;
  box-shadow: 1px 1px 2px 0 #8d8d8d;
  z-index: 1;
  justify-content: center;
  &__logo {
    align-items: center;
    align-self: flex-start;
    display: flex;
    height: 50px;
    width: 320px;
    filter: brightness(1);
    padding: 4px;
    flex-direction: row;
    margin: -5px 0px 5px 0;
  }
  &__container {
    padding: 10px;
    width: 1180px;
    display: flex;
    align-items: center;
    height: 60px;
    justify-content: space-between;
  }
  &__color-mode-picker {
    margin: 10px 1rem 10px 0;
    padding: 0 20px 0 0;
    justify-content: center;
    display: flex;
    flex-direction: row;
    align-items: center;
  }
}
.logo {
  color: white;
  background: darkgray;
  border-radius: 6px;
  padding: 5px 10px;
  font-family: "Roboto", sans-serif;
  font-size: 32px;
  font-weight: 700;
  align-items: center;
  transition: all .15s linear 0s;
  text-shadow: 0 2px 2px -1px #8d8d8d;
  cursor: pointer;
}
</style>
