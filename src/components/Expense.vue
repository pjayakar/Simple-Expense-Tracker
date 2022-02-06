<template>
<div class="expense">
    <table width="100%">
        <tr>
           <td>    
               <h3>{{ expense.text }}</h3>
           </td>
           <td style="text-align: right;"> 
                <p>₹ {{ expense.amount }}</p>
           </td>
        </tr>
    </table>
</div>

</template>
<script>
export default {
    name: 'Expense',
    props: {
        expense: Object
    },
}
</script>

<style>
.fas {
    color: red;
}
.expense {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.expense h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>