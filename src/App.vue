<template>
  <div class="main-container">
    <div class="title">Добавление товара</div>
    <div class="content">
      <AddForm />
      <Products />
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
