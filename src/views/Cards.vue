<template>
    <div class="cards">
         <ul>
      <li v-for="(card,index) in cards" :key="index">
        <a :href="card.url" target="_blank">{{ card.name }}</a>
      </li>
    </ul>
    </div>
</template>

<script>
export default {
    name:"Cards",
    props:["cards"]
}
</script>

<style>

</style>