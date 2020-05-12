<template>
  <section id="employee-add">
    <b-form @submit.prevent="addData" class="w-25 mx-auto">
      <b-form-group>
        <b-form-input
          v-model="inputs.name"
          type="text"
          required
          placeholder="Enter Full Name"
        ></b-form-input>
      </b-form-group>
      <b-form-group>
        <b-form-input
          v-model="inputs.designation"
          type="text"
          required
          placeholder="Enter Designation"
        ></b-form-input>
      </b-form-group>
      <b-form-group>
        <b-form-input
          v-model="inputs.joining_date"
          type="date"
          required
          placeholder="Enter Joining Date"
        ></b-form-input>
      </b-form-group>
      <b-form-group>
        <b-form-input
          v-model="inputs.salary"
          type="number"
          required
          placeholder="Enter Salary"
        ></b-form-input>
      </b-form-group>
      <b-button class="w-100" type="submit" variant="primary"
        >Add New Employee</b-button
      >
    </b-form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      date: new Date(),
      inputs: {
        name: null,
        designation: null,
        joining_date: null,
        salary: null
      },
      employees: []
    };
  },
  methods: {
    addData() {
      let slno = this.employees.length;
      let data = {
        sl_no: slno + 1,
        name: this.inputs.name,
        designation: this.inputs.designation,
        joining_date: this.inputs.joining_date,
        salary: this.inputs.salary
      };
      this.employees.push(data);
      this.inputs.name = null;
      this.inputs.designation = null;
      this.inputs.joining_date = null;
      this.inputs.salary = null;
    }
  }
};
</script>

<style></style>
