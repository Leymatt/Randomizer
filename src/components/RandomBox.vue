<template>
  <div class="random">
    <div class="random__wrapper">
      <h1 class="random__title">🧠 Рандомайзер 🧠</h1>
      <div class="random__result">
        <p class="random__result-text">Полученное число: {{result}}</p>
      </div>
      <div class="random__inputs">
        <div class="random__inputs-wrapper">
          <p class="random__inputs-text">Минимум</p>
          <label for="min" />
          <input type="number" id="min" class="random__inputs-input" v-model="min">
        </div>
        <div class="random__inputs-wrapper">
          <p class="random__inputs-text">Максимум</p>
          <label for="max" />
          <input type="number" id="max" class="random__inputs-input" v-model="max">
        </div>
      </div>
      <button class="random__answer" @click="answer">Получить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  data () {
    return {
      min: '',
      max: '',
      result: ''
    }
  },

  methods: {
    answer () {
      const min = Math.ceil(this.min)
      const max = Math.ceil(this.max)
      if ( min >= max ) {
        this.result = 'min >= max'
      } else {
        this.result = Math.floor(Math.random() * (max - min + 1)) + min;
      }
    }
  }
}
</script>

<style scoped lang="scss">
$grey-color: #3e3e3e;

  .random {
    display: flex;
    background-color: #2c3e50;
    width: 100vw;
    height: 100vh;

    .random__wrapper {
      background-color: white;
      border-radius: 10px;
      margin: 0 auto;
      align-self: center;
      width: 500px;
      height: 500px;
      box-shadow: 0 4px 5px 2px #0f191d;

      .random__title {
        color: $grey-color;
        margin: 35px 0 0;
        border-bottom: 2px solid #ff6e87;
        padding-bottom: 35px;
      }

      .random__result {
        margin-top: 35px;

        .random__result-text {
          font-size: 26px;
        }
      }

      .random__inputs {
        margin-top: 30px;

        .random__inputs-wrapper {
          display: flex;
          justify-content: center;

          &:nth-child(2) {
            margin-top: 40px;

            .random__inputs-text {
              margin-right: 26px;
            }
          }

          .random__inputs-text {
            font-size: 21px;
            margin-right: 30px;
          }

          .random__inputs-input {
            border-bottom: 1px solid $grey-color;
            font-size: 21px;
          }
        }
      }

      .random__answer {
        width: 320px;
        height: 55px;
        border-radius: 10px;
        margin-top: 65px;
        background-color: #ff6e87;
        color: white;
        text-transform: uppercase;
        font-weight: 600;
        font-size: 21px;
      }
    }
  }
</style>
