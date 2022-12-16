<template>
  <div >
    <h1>Filter</h1>
  <v-card
  v-for="item in filter"
  :key="item.id"
    width="300"
    max-width="344"
  >
    
   
   <v-card-actions>
    <v-btn
        color="orange lighten-2"
        text
      >
        {{item.title}}
      </v-btn>

      <v-spacer></v-spacer>
      <v-btn
        icon
        @click=expandCard(item.id);
      >
        <v-icon>{{ item.show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="item.show">
        <v-divider></v-divider>

        <v-card-text 
          v-for=" sub in item.options"
        >
          {{sub}}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</div>
</template>

<script>
export default {
  name: 'SideBar',

  data: () => ({
      
      filter: [
        {
          id: 1,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id: 2,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id: 3,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],show: false,
        },
        {
          id: 4,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id: 5,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:6,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:7,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:9,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:10,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:11,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },
        {
          id:12,
          title: 'Category',
          options: [
            "option 1","option 2","option 3"
          ],
          show: false,
        },

      ]
    }),

    methods: {
      expandCard(id) {
        console.log('hi')
        const index = this.filter.find((search) => search.id == id)

        if(index !== null){
          index.show = !index.show
        }
      }
    }
}
</script>