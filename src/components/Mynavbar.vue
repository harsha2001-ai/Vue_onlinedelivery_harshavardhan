<!-- eslint-disable vue/multi-word-component-names -->
// eslint-disable-next-line vue/multi-word-component-names
<template>
        <ul>
         
  <li><a href="#"><h2>{{ header }}</h2></a></li>
  <li><a href="#"><sp>Start Ordering</sp></a></li>
  <li><a href="#"><span>Current Offers</span></a></li>
  <li class="underline"><a href="#"><span>{{ subheader }}</span></a></li>
  <li style="float:right"><a class="active" href="#"><i>Customer Name: {{ customerName }}</i></a></li>
</ul>

  </template>
  
  <script>
  export default {
    props: {
      header: {
        type: String,
        required: true,
      },
      subheader: {
        type: String,
        required: true,
      },
      customerName: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style >
  
  ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  overflow: hidden;
  background-color: #fa0404;
  display: flex;
  align-items: center;
}

li {
    flex:1;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover{
  background-color: black;
}

.active {
  background-color: #2baa04;
}

li a h2,
li a span,
li a p{
  padding :0;
  margin:0;
}

.underline{
  text-decoration: underline;
  color:white
}
  </style>
  
  
