<template>
  <div class="main-container">
    <div class="title">Добавление товара</div>
    <div class="content">
      <AddForm
        @create="createProducts"
      />
      <Products
        :products="products"
      />
    </div>
  </div>
</template>

<script>
import AddForm from '@/components/AddForm.vue'
import Products from '@/components/Products.vue'

export default {
  components: {
    AddForm,
    Products,
},
  data () {
    return {
      products: [{
        title: 'привет',
        description: 'описание какое то',
        img: 'https://vjoy.cc/wp-content/uploads/2020/10/dlya_dushi_35_13130628.jpg',
        price: 10000,
      }],
    }
  },
  methods: {
    createProducts(newProduct) {
      this.products.push(newProduct)
    }

  }

}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: rgba(255, 254, 251, 0.8);
}

.main-container {
  width: 90%;
  max-width: 1440px;
  margin: auto;
  margin-top: 31px;

  .title {
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 35px;
    color: #3F3F3F;
    margin-bottom: 16px;
  }
  
  .content {
    display: flex;
    width: 100%;
  }
}


</style>
