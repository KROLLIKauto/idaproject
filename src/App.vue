<template>
  <div class="main-container">
     <div class="header">
        <div class="title">Добавление товара</div>
        <select
          v-model="selectedOption"
          @change="changeOptions"
        >
          <option disabled value="">По умолчанию</option>
          <option value="price-min">По цене min</option>
          <option value="price-max">По цене max</option>
          <option value="title">По наименованию</option>
        </select>
     </div>
    <div class="content">
      <AddForm
        @create="createProducts"
      />
      <Products
        :products="products"
        @remove="removeProduct"
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
      products: JSON.parse(localStorage.getItem('products')) || [{
        description: '',
        img: 'https://st2.depositphotos.com/3364363/5972/i/600/depositphotos_59728757-stock-photo-waiting-for-a-new-day.jpg',
        title: 'Место у моря',
        id: new Date(),
        price: '25100',
        description: 'тихое место у самого моря'
      }],
      selectedOption: '',
    }
  },
  watch: {
    selectedOption(selectedOption) {
      this.products.sort((min, max) => {
        switch(selectedOption) {
          case 'price-min': return +min['price'] - +max['price']
          case 'price-max': return +max['price'] - +min['price']
          case 'title': return min['title']?.localeCompare(max['title'])
        }
      })
    }
  },
  methods: {
    createProducts(newProduct) {
      this.products.push(newProduct)
      localStorage.setItem('products', JSON.stringify(this.products))
    },
    removeProduct(product) {
      this.products = this.products.filter(elem => elem.id !== product.id)
      localStorage.setItem('products', JSON.stringify(this.products))
    },

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

  .header {
    display: flex;
    justify-content: space-between;

    select {
      width: 121.49px;
      height: 36px;
      background: #FFFEFB;
      box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
      border-radius: 4px;
    }

    .title {
      font-family: 'Source Sans Pro';
      font-style: normal;
      font-weight: 600;
      font-size: 28px;
      line-height: 35px;
      color: #3F3F3F;
      margin-bottom: 16px;
    }
  }
  
  .content {
    display: flex;
    width: 100%;
    @media (max-width: 800px) {
      flex-direction: column;
      width: 90%;
      margin: auto;
    }
  }
}


</style>
