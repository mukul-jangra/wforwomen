<template>
<v-container>
  <div>
    <v-row>
      <v-col
        cols="3"
        v-for="item in list"
      >
        <v-img
          :src="item.image"
        />
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
    }
  }
</script>
