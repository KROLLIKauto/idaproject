<template>
  <div
    class="products-container"
  >
    <div
      class="product-card" 
      v-for="product in products"
      :key="product.id"
    >
      <div
        class="product-icon-remove"
        @click="$emit('remove', product)"
      >
        <img src="@/images/delete.png" />
      </div>
      <div class="product-image"><img :src=product.img /></div>
      <div class="product-title">{{product.title}}</div>
      <div class="product-description">
        {{product.description}}
      </div>
      <div class="product-price">{{getValidPrice(product.price)}} руб.</div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    products: {
      type: Array,
      requared: true,
    },
  },
  methods: {
    getValidPrice(product) {
      const value = product.split(' ').join('')
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
  },
  
}
</script>

<style scoped lang="scss">
.products-container {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  margin-left: 16px;
  @media (max-width: 800px) {
    justify-content: center;
    margin-top: 5%;
  }

  .product {
    &-card {
      width: 32%;
      display: flex;
      flex-direction: column;
      background: #FFFEFB;
      box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
      border-radius: 4px;
      height: 423px;
      margin-bottom: 2%;
      margin-right: 2%;
      position: relative;
      cursor: pointer;
      @media (min-width: 1200px) {
        &:nth-child(3n) {
          margin-right: 0;
        }
      }
      @media (max-width: 1200px) {
        width: 49%;
        &:nth-child(2n) {
          margin-right: 0;
        }
      }
      @media (max-width: 1000px) {
        width: 80%;
          margin-right: 0;
      }

      &:hover .product-icon-remove {
        display: flex;
      }
    }

    &-icon-remove {
      position: absolute;
      top: -15px;
      right: -15px;
      background: #FF8484;
      box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      width: 32px;
      height: 32px;
      display: none;
      justify-content: center;
      align-items: center;
      cursor: pointer;
    }
    
    &-image {
      width: 100%;
      height: 200px;
      margin-bottom: 16px;
      overflow: hidden;
      border-radius: 4px 4px 0 0;
      & img {
        width: 100%;
      }
    }

    &-title {
      margin-bottom: 16px;
      font-family: 'Source Sans Pro';
      font-style: normal;
      font-weight: 600;
      font-size: 20px;
      line-height: 25px;
      color: #3F3F3F;
      margin-left: 16px;
    }

    &-description {
      font-family: 'Source Sans Pro';
      font-style: normal;
      font-weight: 400;
      font-size: 16px;
      line-height: 20px;
      color: #3F3F3F;
      margin: 0 16px 16px 16px;
      overflow: auto;
    }

    &-price {
      font-family: 'Source Sans Pro';
      font-style: normal;
      font-weight: 600;
      font-size: 24px;
      line-height: 30px;
      color: #3F3F3F;
      margin: 0 16px 16px 16px;
    }
  }
}
</style>