<template>
    <b-container>
        <b-row>
            <b-col class="exchange-item" 
                v-for="(byMarketplace, index) in rateArr.byMarketplace" v-bind:key="index" >
                <table class="table">
                    <thead>
                        <tr>
                            <th class="col-xs-12 text-center" colspan="3">
                            {{ index }}
                            </th>
                        </tr>
                        <tr>
                            <th class="col-xs-4 text-center">Purchase</th>
                            <th class="col-xs-4"></th>
                            <th class="col-xs-4 text-center">Sale</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="item in byMarketplace" v-bind:key="item.marketplace">
                            <td>
                                <div class="price-style">{{ item.buyRate }}</div>
                            </td>
                            <td class="align-middle text-center"><b>{{ item.target }}</b></td>
                            <td><div class="price-style">{{ item.saleRate }}</div></td>
                        </tr>
                    </tbody>
                </table>
            </b-col>
        </b-row>
    </div>
  </b-container>
</template>
<script>
import axios from 'axios'

export default {
  name: 'ExchangeTable',
  data () {
    return {
      rateArr: []
    }
  },
  created () {
    axios.get(`src/resources/api.json`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.rateArr = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  }
}
</script>
<style>
.exchange-item>.table {
    font-size: 16px;
    margin: 5px;
    background: #E7D200;
    /* For browsers that do not support gradients */
    background: -webkit-linear-gradient(#E7D200, #ffff19);
    /* For Safari 5.1 to 6.0 */
    background: -o-linear-gradient(#E7D200, #ffff19);
    /* For Opera 11.1 to 12.0 */
    background: -moz-linear-gradient(#E7D200, #ffff19);
    /* For Firefox 3.6 to 15 */
    background: linear-gradient(#E7D200, #ffff19);
}

.exchange-item .price-style {
    font-family: 'Digital-7', arial;
    font-size: 24px;
    padding: 3px;
    background: #fff;
    margin: 3px;
}

.align-middle {
    vertical-align: middle!important;
}
</style>

