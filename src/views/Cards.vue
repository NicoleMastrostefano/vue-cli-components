<template>
    <div class="cards">
        <ul>
            <!-- <li v-for="(card,index) in cards" :key="index">
                <a :href="card.url" target="_blank">{{ card.name }}</a>
            </li> -->
            <Card 
                v-for="(card,index) in cards" 
                :key="index"
                :name="card.name"
                :url="card.url"
            />
        </ul>
    </div>
</template>

<script>
import Card from "../components/Card.vue";

export default {
    name:"Cards",
    // props:[ "cards","className" ]
    props: {
        cards: {
            type: Array
        },
        className: {
            type: String
        } 
    },
    components: {
        Card
    }
}
</script>

<style>

</style>>