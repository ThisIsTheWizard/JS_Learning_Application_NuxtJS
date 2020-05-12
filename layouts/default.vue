<template>
  <div id="wizard">
    <navbar />
    <nuxt />
  </div>
</template>

<script>
import navbar from "~/components/navbar";
export default {
  components: { navbar }
};
</script>

<style>
#wizard {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
.my-flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
.my-btn {
  padding: 8px 16px;
  margin: 10px 5px;
  font-weight: 600;
  border-radius: 20px;
  border: 1px solid #fff;
  text-transform: capitalize;
  color: rgba(255, 255, 255, 0.9);
  background-color: rgba(0, 0, 0, 0.4);
  background-clip: padding-box;
  -webkit-transition: all 1s ease-in-out;
  -moz-transition: all 1s ease-in-out;
  transition: all 1s ease-in-out;
}
.my-btn:hover,
.my-btn:focus,
.my-btn.nuxt-link-exact-active {
  outline: 0;
  text-decoration: none;
  color: rgba(255, 255, 255, 1);
  box-shadow: inset 300px 0 0 0 #007bff;
}
.my-btn.big:hover,
.my-btn.big:focus {
  box-shadow: inset 600px 0 0 0 #007bff;
}
.h-100vh {
  height: 100vh;
}
</style>
