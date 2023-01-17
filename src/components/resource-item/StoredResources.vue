<template>
    <ul>
        <resource-item v v-for="res in resources" 
        :key="res.id" 
        :title="res.title"
        :description="res.description"
        :link="res.link"
        ></resource-item>
        <li></li>
    </ul>
</template>
<script>
import ResourceItem from './ResourceItem.vue';
export default {
    inject: ['resources'],
    components: {
        ResourceItem
    }
};
</script>
<style scoped>
ul {
    list-style: none;
    margin: 0;
    padding: 0;
    margin: auto;
    max-width: 40rem;
  }
</style>