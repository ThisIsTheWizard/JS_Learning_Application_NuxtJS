<template>
  <section id="home-page">
    <div class="w-50 mx-auto">
      <h1 class="text-center">
        Home Page
      </h1>
      <b-form-select v-model="selected" :options="options"></b-form-select>
      <h1>{{ selected }}</h1>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      selected: "",
      options: [
        {
          value: "3",
          text: "bkash Personal BDT",
        },
        {
          value: "9",
          text: "Payoneer USD",
        },
        {
          value: "4",
          text: "bkash Agent BDT",
        },
        {
          value: "5",
          text: "Rocket Personal BDT",
        },
        {
          value: "6",
          text: "Rocket Agent BDT",
        },
        {
          value: "7",
          text: "Nagad Personal BDT",
        },
        {
          value: "8",
          text: "Nagad Agent BDT",
        },
        {
          value: "10",
          text: "Neteller USD",
        },
        {
          value: "11",
          text: "Skrill USD",
        },
        {
          value: "12",
          text: "PayPal USD",
        },
        {
          value: "13",
          text: "Chinese Yuan",
        },
      ],
    };
  },
};
</script>

<style></style>
