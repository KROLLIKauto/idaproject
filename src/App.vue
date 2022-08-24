<template>
  <div class="main-container">
    <div class="title">Добавление товара</div>
    <div class="content">
      <div class="auth-container">
        <form>
          <div class="form-input-container">
            <div class="form-input-title">Наименование товара</div>
            <input placeholder="Введите наименование товара" />
          </div>
          <div class="form-input-container">
            <div class="form-input-title">Описание товара</div>
            <textarea placeholder="Введите описание товара"></textarea>
          </div>
          <div class="form-input-container">
            <div class="form-input-title">Ссылка на изображение товара</div>
            <input placeholder="Введите ссылку" />
          </div>
          <div class="form-input-container">
            <div class="form-input-title">Цена товара</div>
            <input placeholder="Введите цену" />
          </div>
          <button class="form-button">Добавить товар</button>
        </form>
      </div>
      <div class="products-container">
        <div class="product-card">
          <div class="product-image"><img src="http://bipbap.ru/wp-content/uploads/2017/04/0_7c779_5df17311_orig.jpg" /></div>
          <div class="product-title">Наименование товара</div>
          <div class="product-description">
            Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк
          </div>
          <div class="product-price">10 000 руб.</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
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

    //auth
    .auth-container {
      width: 332px;
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
              font-weight: 400;
              font-size: 12px;
              line-height: 15px;
              color: #B4B4B4;
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
        }
      }
    }

    //products
    .products-container {
      display: flex;
      width: 60%;
      flex-wrap: wrap;
      justify-content: space-between;
      margin-left: 16px;

      .product {
        &-card {
          width: 332px;
          display: flex;
          flex-direction: column;
          background: #FFFEFB;
          box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
          border-radius: 4px;
          height: 423px;
          overflow: hidden;
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
  }
}


</style>
