<template>
  <div class="products-container">
    <div class="product-card">
      <div class="product-image"><img src="http://bipbap.ru/wp-content/uploads/2017/04/0_7c779_5df17311_orig.jpg" /></div>
      <div class="product-title">Наименование товара</div>
      <div class="product-description">
        Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк
      </div>
      <div class="product-price">10 000 руб.</div>
    </div>
    <div class="product-card">
      <div class="product-image"><img src="http://bipbap.ru/wp-content/uploads/2017/04/0_7c779_5df17311_orig.jpg" /></div>
      <div class="product-title">Наименование товара</div>
      <div class="product-description">
        Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк
      </div>
      <div class="product-price">10 000 руб.</div>
    </div>
    <div class="product-card">
      <div class="product-image"><img src="http://bipbap.ru/wp-content/uploads/2017/04/0_7c779_5df17311_orig.jpg" /></div>
      <div class="product-title">Наименование товара</div>
      <div class="product-description">
        Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк
      </div>
      <div class="product-price">10 000 руб.</div>
    </div>
  </div>
</template>
<script>
export default {
  
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