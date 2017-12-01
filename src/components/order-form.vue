<template>
    <b-container>
        <b-row>
            <div class="order-form">
                <b-form inline @submit="onSubmit" @reset="onReset">
                    <label class="mr-sm-2" for="inlineFormCustomSelectPref">Enter your data:</label>
                    <b-form-select id="Type"
                            :options="types"
                            required placeholder="Type"
                            v-model="form.type">
                    </b-form-select>
                    <b-form-select id="Currency"
                            :options="currency"
                            required
                            v-model="form.currency">
                    </b-form-select>
                    <b-form-input id="Amount"
                        type="number"
                        v-model="form.amount"
                        required
                        placeholder="Amount">
                    </b-form-input>
                    <b-button type="submit" variant="primary">Send</b-button>
                </b-form>
            </div>
        </b-row>
    </b-container>
</template>
<script>
import axios from 'axios'

export default {
  name: 'OrderForm',
  data () {
    return {
        form: {
        type: '',
        currency: '',
        amount: 0
    },
    types: [{
            text: 'Sell',
            value: 'sell'
        },{
            text:'Buy',
            value: 'buy'
        }
    ],
    currency: [{
            text: 'BTC',
            value: 'btc'
        },{
            text:'UAH',
            value: 'uah'
        },{
            text: 'RUR',
            value: 'rur'
        },{
            text:'USD',
            value: 'usd'
        }
    ]
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
      let params = '/'+this.form.type+'?currency='+this.form.currency+'&amount='+this.form.amount;
      window.open(`http://krb.rublin.org:8089/api/v1/order`+params,'_blank');
      /*axios.get(`http://krb.rublin.org:8089/api/v1/order`+params)
      .then(response => {
      // JSON responses are automatically parsed.
        console.log(response);
      })
      .catch(e => {
        this.errors.push(e)
      })*/
    },
    onReset (evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.type = ''
      this.form.type = ''
      this.form.currency = 0
    }
  }
}
</script>
<style>
    .order-form {
        margin: 0 auto;
    }
</style>
