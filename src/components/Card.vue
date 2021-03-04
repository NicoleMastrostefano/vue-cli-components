<template>
    <li>
        <a href="url" target="_blank">{{ name }}</a>
    </li>
</template>

<script>
export default {
    name:"Card",
    // props:["name", "url"]
    props: {
        name:{
            type: String,
            required:true
        },
        url: {
            type: String,
            required:true
        }
    }
}
</script>

<style>
    
</style>