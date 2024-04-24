<template>
  <div >
    <Mynavbar :header="headerNav" :subheader="orderinfo" :customerName="Name" />

    <OrdersDetails  :data="prevOrders" />

    <Playstore :playstore="Rating" />

    <div v-if="loading">Data Loading.Please Wait</div>
    <div v-if="error">{{ errortofetchdata }}</div>
  </div>
</template>

<script>
import Mynavbar from './components/Mynavbar.vue';
import OrdersDetails  from './components/OrdersDetails.vue';
import Playstore from './components/Playstore.vue';


export default {
  name: 'App',
  components: {
    Mynavbar,
    OrdersDetails,
    Playstore,
  },
  data() {
    return {
      headerNav: 'Zomato',
      orderinfo: 'Previous Orders Info',
      Name: 'Sri Harsha Vardhan Yendru',
      prevOrders: [],
      Rating: 'Zomato',
      loading: true,
      error: null,
    };
  },
  methods: {
    async fetchorders() {
      try {
        const response = await fetch('https://fetch-previous-order-details.onrender.com/api');
        if (!response.ok) {
          throw new Error('Network response not ok');
        }

        const data = await response.json();
        this.prevOrders =data;
      } catch (error) {
        console.error('Error fetching details of the order:', error.message);
        this.error = 'Error.Please try again later.';
        return [];
      } finally {
        this.loading = false;
      }
    },
  },
  async created() {
    await this.fetchorders();

    
  },
};
</script>

<style>
body {
  font-family: 'Montserrat', sans-serif;
  margin: 0;
  padding: 0;
}

#app div {
  margin-top: 10px;
  font-weight: bold;
  color: black;
}



</style>
