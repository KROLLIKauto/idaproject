<template>
  <div class="auth-container">
    <form @submit.prevent>
      <div class="form-input-container">
        <div class="form-input-title">Наименование товара</div>
        <input
          v-model="newProduct.title"
          placeholder="Введите наименование товара"
          required
        />
      </div>
      <div class="form-input-container">
        <div class="form-input-title">Описание товара</div>
        <textarea
          v-model="newProduct.description"
          placeholder="Введите описание товара"
        >
        </textarea>
      </div>
      <div class="form-input-container">
        <div class="form-input-title">Ссылка на изображение товара</div>
        <input
          v-model="newProduct.img"
          placeholder="Введите ссылку"
          required
        />
      </div>
      <div class="form-input-container">
        <div class="form-input-title">Цена товара</div>
        <input
          :value="newProduct.price"
          @input="addSpaceMask"
          placeholder="Введите цену"
          required
        />
      </div>
      <button
        class="form-button"
        :disabled="isDisabled"        
        @click="createProducts"
      >
        Добавить товар
      </button>
    </form>
  </div>
</template>
<script>
export default {
  data () {
    return {
      newProduct: {
        title: '',
        description: '',
        img: '',
        price: '',
      }
    }
  },
  computed: {
    isDisabled() {
      if (
        this.newProduct.title.length === 0
        || this.newProduct.img.length === 0
        || this.newProduct.price.length === 0
      ) return true

      return false
    },
  },
  methods: {
    createProducts() {
      this.newProduct.id = new Date()
      this.newProduct.price = this.newProduct.price.split(' ').join('')
      this.$emit('create', this.newProduct)
      this.newProduct = {
        title: '',
        description: '',
        img: '',
        price: '',
      }
    },

    addSpaceMask(e) {
      this.newProduct.price = this.getValidPrice(e)
    },

    getValidPrice(e) {
      const value = e.target.value.split(' ').join('')
      if (isNaN(+value)) {
        this.newProduct.price = ''
        return
      }

      let arrWithArrays = []
      let arrValue = value.split('')
      while (arrValue.length) arrWithArrays.push(arrValue.splice(-3, 3), ' ')
      let result = arrWithArrays.reverse().flat().join('')
      result.slice(0, 1) === ' ' && result.slice(0, 1)

      return result
    }
  }
}

</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@500&display=swap');

.auth-container {
  min-width: 332px;
  height: 440px;
  left: 32px;
  top: 83px;
  background: #FFFEFB;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;

  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;

    .form-input {
      &-container {
        display: flex;
        flex-direction: column;
        width: 90%;
        margin-bottom: 16px;
        
        input, textarea {
          background: #FFFEFB;
          box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
          border-radius: 4px;
          height: 36px;
          outline: none;
          border: none;
          font-family: 'Source Sans Pro';
          font-weight: 400;
          font-size: 12px;
          line-height: 15px;
          color: #3F3F3F;
          padding: 4px;
        }

        textarea {
          min-height: 108px;
          resize: none;
        }

      }

      &-title {
        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 400;
        font-size: 10px;
        line-height: 13px;
        letter-spacing: -0.02em;
        color: #49485E;
        margin-bottom: 4px;
      }
    }
      
    .form-button {
      background: #7BAE73;
      box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      width: 90%;
      height: 36px;
      color: #FFFFFF;
      border: none;
      font-family: 'Inter';
      font-style: normal;
      font-weight: 600;
      font-size: 12px;
      line-height: 15px;

      &:hover {
        cursor: pointer;
        border: 1px solid rgb(62, 99, 62);
      }

      &:disabled {
        background-color: #a9a9a9;
        cursor: auto;
        border: none;
      }
    }
  }
}
</style>