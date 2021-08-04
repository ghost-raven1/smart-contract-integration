<template>
  <div class="main">
    <div class="card">
      <div class="card__left">
        <div class="balance">
          <span class="balance__title">Your balance</span>
          <span class="balance__value">100 BUSD</span>
          <input v-model="code" class="balance__input" type="text">
        </div>
      </div>
      <div class="card__right">
        <img alt="card-reader" src="/img/Card-Reader.svg">
      </div>
    </div>
    <div v-for="(wallet, i) in wallets" :key="i" class="wallets-panel">
      <div class="wallets-panel__item">
        <div>
          <img :alt="wallet.name" :src="wallet.imageUrl">
          <div>
            {{ wallet.name }}
          </div>
        </div>
      </div>
    </div>
    <div class="transfer-panel">
      1
    </div>
  </div>
</template>

<script>
export default {
  layout: 'default',
  data () {
    return {
      code: '',
      wallets: [
        {
          name: 'BUSD',
          imageUrl: ''
        },
        {
          name: 'BUSD',
          imageUrl: ''
        },
        {
          name: 'BUSD',
          imageUrl: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

.balance {
  display: flex;
  flex-direction: column;
  margin: 36px 0 30px 35px;
  &__title {
    font-weight: 400;
    font-size: 16px;
    color: #202020;
    margin-bottom: 8px;
  }
  &__value {
    font-weight: 700;
    font-size: 40px;
    color: #202020;
  }
  &__input {
    margin: 30px 0 0 0;
  }
}

.main {
  max-width: 1180px;
  width: 100%;
  height: 100%;
  justify-content: center;
}

.card {
  margin: 25px 0 25px 0;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  height: 180px;
  background: linear-gradient(253.94deg, #09F2C3 8.37%, #15DCE4 69.71%);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
  border-radius: 14px;
  &__left {}
  &__right {}
  &__right img {
    z-index: 1;
  }
}

.wallets-panel {
  width: 100%;
  height: 100px;
  display: flex;
  flex-direction: row;
  margin: 5px;
  &:first-child {
    margin: 5px 5px 5px 0;
  }
  &:last-child {
    margin: 5px 0 5px 5px;
  }
  &__item {
    width: 186px;
    height: 100px;
    background: #3C3C3C;
    border-radius: 14px;
  }
}

.transfer-panel {
  width: 100%;
  background: #3C3C3C;
  border-radius: 14px;
  height: 417px;
}
</style>
