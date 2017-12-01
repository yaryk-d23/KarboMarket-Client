<template>
  <div id="app">
    <NavBar/>
    <br><br>
    <ExchangeTable/>
    <br><br>
    <OrderForm/>
  </div>
</template>

<script>
import NavBar from './components/nav-bar'
import ExchangeTable from './components/exchange-table'
import OrderForm from './components/order-form'
export default {

  name: 'app',
  components: {
    NavBar,
    ExchangeTable,
    OrderForm
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Noto+Sans');
@import url('http://allfont.ru/allfont.css?fonts=digital-7');
body {
    font-family: 'Noto Sans', sans-serif;
    font-weight: 300;
    background-color: #fff;
}

h1,
h2,
h3,
h4,
h5,
h6 {
    color: #465672;
}

p {
    line-height: 28px;
    margin: 25px;
    color: #465672;
}
</style>
