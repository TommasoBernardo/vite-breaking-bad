<template>
    <header>
        <nav class="navbar  my-nav-color">
            <div class="container">
                <a class="navbar-brand" href="#">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg/1200px-Yu-Gi-Oh%21_%28Logo%29.jpg"
                        alt="" class="img-fluid"> Yu-Gi-Oh Api</a>
            </div>

            <TypeSelect  @search ="getCards"/>
        </nav>
    </header>
</template>
<script>
import { store } from '../store.js';
import TypeSelect from './TypeSelect.vue';
import SelectStyle from './SelectStyle.vue'
import axios from 'axios';
export default {
    components:{
        TypeSelect,
        SelectStyle,
    },
    name: 'AppHeader',
    data() {
        return {
            store,
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?",
        }
    },
    methods: {
    getCards(archetypeInput = 'chaos') {
      axios.get(this.apiUrl, {
        params: {
          num: 12,
          offset: 0,
          archetype: archetypeInput,
          type: 'Effect Monster'
        }
      })
        .then((response) => {
          this.store.cardsList = (response.data.data);
        })
        .catch(function (error) {
          // handle error
          console.error(error);
        })
    },
    getResponse() {
      console.log('Connessione riuscita')
    }
  },
  created() {
    this.getCards();
  }
}
</script>
<style lang="scss" scoped>
header {
    height: 80px;
    background-color: #FFFFFF;

    a {
        font-size: 3rem;
    }

    img {
        height: 60px;
    }
}

.my-nav-color{
    background-color: orange;
}
</style>