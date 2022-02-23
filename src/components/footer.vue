<template>
  <v-footer :padless = "padless">
    <v-card dark flat tile width="100%" class="deep-purple accent-4 text-center flex"
    >
      <v-card-text>
        <v-btn v-for="(icon, i) in icons" :key="i" class="mx-4" icon>
          <v-icon size="24px">
            {{ icon.name }}
            </v-icon>
        </v-btn>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — 
        <strong> {{ copyright }} </strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
        copyright:'Cristine Marquez',
        icons: [
        {
            name:'mdi-facebook',
            url: 'https://www.facebook.com/#',
        },
        {
            name:'mdi-github',
            url: 'https://github.com/#',
        },
        {
            name:'mdi-linkedin',
            url: 'https://www.linkedin.com/in/#',
        },
        {
            name:'mdi-instagram',
            url: 'https://www.instagram.com/#',
            
        }
      ],
      padless: true,
    })
}
</script>


<style scoped>


</style>