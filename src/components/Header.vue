<template>
    <header>
        <div id="app">
        <img 
            :class="center" 
            v-bind:src="picture" 
            v-bind:alt="`${firstName}`"
        /> 
        </div>
    </header>
    <h1 style="text-align: justify" >{{firstName}}'s Expense Tracker</h1>

</template>

<script>
import image from "C:/Users/pjaya/expense-tracker/src/images/panda.jpg"
    import Button from './Button.vue'
    export default{
        name: 'Header',
        props:{
            title: String,
            firstName: String,
        },
        components: {
            Button
        },
        data(){
            return{
                firstName: 'Pinaki',
                picture: image
            }
        }
    }
</script>
<style scoped>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}
.centered{
    position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
 img {
    height: 100px;
    width: 100px;
    border-radius: 50%;
    border: 3px #333 solid;
    margin-bottom: 1rem;
  }
    #app {
    margin: auto;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
    header {
        left: 50%;
        right: 50%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>