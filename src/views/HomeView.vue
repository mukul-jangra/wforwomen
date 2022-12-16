<template>
<v-container>
  <div>
    <v-row>
      <v-col
        cols="3"
        v-for="item in list"
      >
      <template>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      :src="item.image"></v-img>
    <v-card-subtitle>
      {{item.name}}
    </v-card-subtitle>
    <v-card-title>
      {{item.price}}
    </v-card-title> 
      
  </v-card>
</template>
      </v-col>
    </v-row>
  </div>
</v-container>
</template>

<script>


  export default {
    name: 'HomeView',

    props: {
      // data from the parent
      list: Array
    },
    data() {
      return {
      }
    },
    methods: {
      
    },
    mounted() {
      this.setSize();
    }
  }
</script>
