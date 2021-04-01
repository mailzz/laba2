
<template>
  <v-app>
    <v-main>
      <slad/>
    </v-main>
  </v-app>
</template>

<script>
import slad from './components/slad';
export default {
  name: 'App',
  components: {
    slad,
  },
  data: () => ({
    //
  }),
};
</script>
