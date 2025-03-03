<template>
    <div class="block">
      Click Me
    </div>
  </template>
  
  <script>
  export default {
      props: ['delay'],
      data(){
        return {
            showBlock: false
        }
      },
      mounted(){
        console.log('Component Mounted')        
      }
  }
     
  </script>
  
  <style>
      .block{
          width: 400px;
          border-radius: 20px;
          background: rgb(7, 67, 107);
          color: white;
          text-align: center;
          padding: 100px 0;
          margin: 40px auto;
      }
  </style>