<template>
  <b-navbar toggleable="md" class="mb-md-5" variant="primary">
    <div class="container">
      <b-navbar-brand class="text-light font-weight-bold"
        >The-Wizard</b-navbar-brand
      >

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <li class="nav-item">
            <nuxt-link to="/" class="my-btn">Home</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link
              :to="{ name: 'employee-application-list' }"
              class="my-btn"
              >Employee Application</nuxt-link
            >
          </li>
          <li class="nav-item">
            <nuxt-link :to="{ name: 'pig-game' }" class="my-btn"
              >Pig Game</nuxt-link
            >
          </li>
        </b-navbar-nav>
      </b-collapse>
    </div>
  </b-navbar>
</template>

<script>
export default {};
</script>

<style></style>
