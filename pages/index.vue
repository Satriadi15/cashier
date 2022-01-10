<template>
  <v-row >
    <v-col cols="8"> 
     <products></products>
    </v-col>
     <v-col cols="4"> 
     ORDERS
    </v-col>
  </v-row>
</template>

<script>
import Products from '~/components/Products.vue'
export default {
  components: { Products },
  name: 'IndexPage',
}
</script>
