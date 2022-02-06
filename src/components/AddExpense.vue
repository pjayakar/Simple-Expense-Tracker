<template>
  <form @submit="onSubmit" class="add-form">
      <table style="width:100%">
          <td style="width:50%; padding-right: 10px">
            <div class="form-control">
                <label>Expense</label>
                <input type="text" v-model="text" name="text" placeholder="Add Expense" />
            </div>
          </td>
          <td style="width:50% padding-left: 10px">
            <div class="form-control">
                <label>Amount</label>
                <input
                    v-model.number="amount" 
                    type="number"
                    placeholder="₹"
                />
            </div>
          </td>
      </table>
    <input type="submit" value="Add Expense" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: 'AddExpense',
  data() {
    return {
      text: '',
      amount: 0
    }
  },
  methods: {
    onSubmit(e) {
        e.preventDefault()

        if (!this.text) {
            alert('Please add an expense')
            return
        }

        const newExpense = {
            id: Math.floor(Math.random()*100000),
            text: this.text,
            amount: this.amount,
        }

        this.$emit('add-Expense', newExpense)
        this.text = ''
        this.amount = 0
    },
  },
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}

.form-control {
  margin: 20px 0;
}

.form-control label {
  display: block;
}

.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}

.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>