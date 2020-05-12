<template>
  <section id="employee-list">
    <b-table
      class="w-50 mx-auto"
      striped
      hover
      :items="employees"
      :fields="fields"
    ></b-table>
    <nuxt-link :to="{ name: 'employee-application-add' }" class="my-btn"
      >Add Data</nuxt-link
    >
  </section>
</template>

<script>
export default {
  data() {
    return {
      fields: [
        { key: "sl_no", label: "SL NO" },
        { key: "name", label: "FULL NAME" },
        { key: "designation", label: "DESIGNATION" },
        { key: "joining_date", label: "JOINING DATE", filter: "hello" },
        { key: "salary", label: "SALARY" }
      ]
    };
  }
};
</script>

<style></style>
