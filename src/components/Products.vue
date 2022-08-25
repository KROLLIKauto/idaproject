<template>
  <div
    class="products-container"
  >
    <div
      class="product-card" 
      v-for="product in products"
    >
      <div class="product-image"><img :src=product.img /></div>
      <div class="product-title">{{product.title}}</div>
      <div class="product-description">
        {{product.description}}
      </div>
      <div class="product-price">{{product.price}} руб.</div>
    </div>
  </div>
</template>
<script>

export default {
  props: {
    products: {
      type: Array,
      requared: true,
    }
  }
  
}
</script>

<style scoped lang="scss">
.products-container {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-left: 16px;

  .product {
    &-card {
      width: 32%;
      display: flex;
      flex-direction: column;
      background: #FFFEFB;
      box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
      border-radius: 4px;
      height: 423px;
      overflow: hidden;
      margin-bottom: 2%;
      @media (max-width: 1200px) {
        width: 49%;
      }
    }
    
    &-image {
      width: 100%;
      height: 200px;
      margin-bottom: 16px;
      overflow: hidden;
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