<template>
    <div class="end" style="margin-bottom: 15px">
        <table width="100%">
        <tr>
           <td>    
               <h3>Total Allowance: </h3>
           </td>
           <td style="text-align: right;">    
               <p>₹ {{total_amount}}</p>
           </td>
        </tr>
    </table>
    </div>
    <div :key="expense.id" v-for="expense in expenses">
        <Expense :expense="expense"/>
    </div>
    <div class="end" style="margin-top: 15px">
        <table width="100%">
        <tr>
           <td>    
               <h3>Total Expenses: </h3>
           </td>
           <td style="text-align: right;">    
               <p>₹ {{ subTotal(expenses) }}</p>
           </td>
        </tr>
        </table>
    </div>
    <div class="end">
        <table width="100%">
        <tr>
           <td>    
               <h3>Balance Remaining: </h3>
           </td>
           <td style="text-align: right;">    
               <p>₹ {{ remaining_balance() }}</p>
           </td>
        </tr>
    </table>
    </div>
</template>

<script>
import Expense from './Expense.vue'
export default {
    name: 'Expenses',
    data(){
        return{
            total_amount: 10000
        }
    },
    props: {
        expenses: Array,
    },
    components: {
        Expense
    },
    methods: {
    subTotal(expenses) {
      return expenses.reduce((acc, ele) => {
        return acc + parseInt(ele.amount);
      }, 0);
    },
    remaining_balance(){
        return this.total_amount - this.subTotal(this.expenses);
    }
  }
}
</script>
<style>

.end {
  background: #dddada;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.end h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>