<!-- eslint-disable vue/multi-word-component-names -->

<template>
  <div class="footer">
    <p>&copy; {{ playstore }}. <i>Rate us on Play Store.</i></p>
  </div>
</template>

<script>
export default {
  props: {
    playstore: {
      type: String,
      required: true,
    },
  },
};
</script>

<style >

.footer {
  background-color: #ff0000;
  color: #fff;
  padding: 10px;
  text-align: center;
  font-size: large;
}
</style>


