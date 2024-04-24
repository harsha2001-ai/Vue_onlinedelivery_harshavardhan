
<template>
    <div class="orders">
    <div v-for="item in data" :key="item.id" class="order_item">
    <h3> Restaurant Name:<br>{{ item.Name }} <hr></h3>
    <p>Delivery Rating: {{ item.DeliveryRating }} star</p>
    <p>Payment Type: {{ item.MethodOfPayment }} (Cash/Card/Rewards)</p>
    <p>Number of Items: {{ item.NumberOfItems }} (Item/Items)</p>
    <p>Total Amount: {{ item.OrderAmount }} </p>
    <p>Ordered Date: {{ new Date(item.OrderDate).toLocaleDateString() }} (DD/MM/YYYY)</p>
    <p> Ordered Dish: {{ item.RestaurantDish }} (Dish/Dishes)</p>
    </div>
  </div>
    </template>
    
    <script>
    export default {
        
        name: 'OrdersDetails' ,
    props: {
    data: Array,
    },
    };
    </script>
    
    <style>
    .orders {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));

      grid-gap: 30px;

      background-color: rgb(255, 47, 0);
      padding: 20px 20px 35px 20px;
    }
    .orders h3{
         text-align: center;

         color: brown
    }


    .orders p{
      color:rgb(255, 255, 255);
    }
    
    .order_item {
      background-color:rgb(91, 159, 76);
      padding-bottom: 10px;
      padding: 20px;
      
    }
    </style>