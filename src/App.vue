<template>
  <div>
    <v-app id="inspire">
  <app-navbar></app-navbar>
  <app-form></app-form>
  <app-footer></app-footer>
  </v-app>
  </div>
</template>

<script>
import footerVue from './components/footer.vue'
import formVue from './components/form.vue'
import navbarVue from './components/navbar.vue'

export default {
  name: 'App',
  components: {
    'app-navbar': navbarVue,
    'app-form': formVue,
    'app-footer': footerVue
  },
}
</script>