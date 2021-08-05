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
    <div class="wallets">
      <div v-for="(wallet, i) in wallets" :key="i" class="wallet">
        <div class="wallet__info">
          <div class="wallet__currency">
            <img :alt="wallet.name" :src="wallet.imageUrl">
            <div class="wallet__name">
              {{ wallet.name }}
            </div>
          </div>
          <div class="wallet__balance">
            {{ wallet.balance }} {{ wallet.name }}
          </div>
        </div>
      </div>
    </div>
    <div class="transfer">
      <div class="transfer__title">
        Transfer
      </div>
      <div class="transfer__inputs">
        <div class="amount">
          <label class="amount__label" for="amount">
            Amount
          </label>
          <input id="amount" type="number" class="amount__input" placeholder="Amount">
        </div>
        <div class="address">
          <label class="address__label" for="address">
            Address (Recipient)
          </label>
          <input id="address" type="number" class="address__input" placeholder="Address">
        </div>
        <div class="btns">
          <button class="btn__allowance">
            Get allowance
          </button>
          <button class="btn__approve">
            Approve
          </button>
          <button class="btn__transfer">
            Transfer
          </button>
        </div>
      </div>
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
          name: 'DND',
          imageUrl: '~/assets/img/empty-token.webp',
          balance: '100'
        },
        {
          name: 'USDT',
          imageUrl: '~/assets/img/empty-token.webp',
          balance: '100'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

.wallets {
  height: 100px;
  display: flex;
  flex-direction: row;
  margin: 5px;
}

.wallet {
  width: 186px;
  height: 100px;
  background: #3C3C3C;
  border-radius: 14px;
  margin: 10px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
  &:first-child {
    margin: 5px 10px 5px 0;
  }
  &:last-child {
    margin: 5px 0 5px 10px;
  }
  &__info {
    margin: 20px 20px 10px 20px;
  }
  &__name {
    font-size: 18px;
    font-family: Montserrat, sans-serif;
    font-weight: 600;
    color: #fff;
  }
  &__balance {
    font-family: Montserrat, sans-serif;
    font-size: 16px;
    font-weight: 400;
    text-align: right;
    color: #8F8F8F;
  }
  &__currency {
    display: flex;
    flex-direction: row;
    margin-bottom: 14px;
  }
}

.transfer {
  margin: 40px 0 0 0;
  width: 100%;
  background: #3C3C3C;
  border-radius: 14px;
  height: 417px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
  &__title {
    margin: 0 30px 0 30px;
    padding: 30px 0 30px 0;
    font-family: Montserrat, sans-serif;
    font-weight: 600;
    font-size: 23px;
    color: #fff;
  }
  &__inputs {
    margin: 0 30px 0 30px;
  }
}

.btns {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  gap: 10px;
}

.address {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
  &__label {
    font-family: Montserrat, sans-serif;
    font-weight: 400;
    font-size: 16px;
    color: #C7C7C7;
    margin-bottom: 10px;
  }
  &__input {
    height: 72px;
    border-radius: 14px;
    color: #585858;
    border: none;
    background: #585858;
    &::placeholder {
      font-weight: 400;
      font-size: 18px;
      font-family: Montserrat, sans-serif;
      color: #8F8F8F;
      padding: 0 0 0 20px;
    }
  }
}

.amount {
  @extend .address;
  &__label {
    @extend .address__label;
  }
  &__input {
    @extend .address__input;
  }
}

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
    margin: 10px 0 0 0;
    height: 42px;
    background: #FFFFFF;
    border-radius: 35px;
    width: 100%;
    border: none;
    padding: 0 20px 0 20px;
    font-family: Montserrat, sans-serif;
    font-size: 16px;
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
  &__left {
    max-width: 500px;
    width: 100%;
  }
  &__right img {
    z-index: 1;
  }
}
</style>
