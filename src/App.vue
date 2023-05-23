<script>
import Cards from './components/Cards.vue';
import axios from 'axios';

export default {
    components: {
        Cards,
    },

    data() {
        return {
            CardJSON: [],
        }
    },

    computed: {
        getCardAPI(){
            // axios.post('https://db.ygoprodeck.com/api/v7/randomcard.php')
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
                .then(response => this.CardJSON = response.data.data);
        },
    }
}

</script>

<template>
    <header>
        <h1>YU-GI-OH API</h1>
    </header>
    <div id="divCard">
        <Cards v-for="card in CardJSON"
        :id="card.id"
        :name="card.name"
        :type="card.type"
        :img="card.card_images[0].image_url"
        />
    </div>
    
</template>    
    

<style lang="scss">
    body {
        margin: 0;
    }
    #divCard {
        padding: 2em;
        display: flex;
        flex-wrap: wrap;
        background-color: orange;
        gap: .3em;
    }
</style>
