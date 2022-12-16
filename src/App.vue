<template>
  <v-app>
    <div
      class="d-flex"
    >
      <SideBar />
      <HomeView :list = list />
  </div>  
</v-app>
</template>

<script>
import axios from "axios";
import SideBar from "./components/SideBar.vue";
import HomeView from "./views/HomeView.vue";

export default {
  
  data() {
    return {
      list: [],
      // the current page from which data is fetched 
      page: 1,
    };
  },

  components: {
    SideBar,
    HomeView
  },
  
  methods: {

    // initial data
    async getData() {
      let result = await axios.get(`https://pim.wforwoman.com/pim/pimresponse.php/?service=category&store=1&url_key=top-wear-kurtas&page=${this.page}&count=20&sort_by=&sort_dir=desc&filter=`)
    
    const value = this.list.concat(result.data.result.products)
    this.list = value
    
    },

    // to get next set of data when scrolled
    async getNextData() {
      let next = await axios.get(`https://pim.wforwoman.com/pim/pimresponse.php/?service=category&store=1&url_key=top-wear-kurtas&page=${this.page}&count=20&sort_by=&sort_dir=desc&filter=`)

      this.list.push(next.data.result.products)
    },
  //   getNextPage() {
  //     window.onscroll = () => {
  //       let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight == document.documentElement.offsetHeight;
  //       if (bottomOfWindow) {
  //         this.page++
  //         this.getData();
  //         console.log(this.page)
  //       }
  //   }
  // },

  // scroll
  handleScroll() {
    if(window.scrollY + window.innerHeight >= document.body.scrollHeight - 50) {
      this.page++
          this.getData();
      console.log('scrolled')
    }
  }

  
},
  mounted(){
    // this.getNextPage();
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeMount() {
    this.getData();
  }
};
</script>
