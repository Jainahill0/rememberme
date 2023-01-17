<template>
    <base-card>
       <base-button @click="setSelectedTab('stored-resourses')">Stored Resources</base-button>
       <base-button @click="setSelectedTab('add-resourse')">Add Resource</base-button>

    </base-card>
    <component :is="selectedTab"></component>
</template>
<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
    components: {
        StoredResources,
        AddResource
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [ 
                {
                    id: 'official-guide', 
                    title: 'Official Guide',
                    description: 'The official Vue.js Documentation.',
                    link: ''
             }, 
                {
                    id: 'google', 
                    title: 'Google',
                    description: 'Learn to google....',
                    link: ''
            },

            ],
        };
    },
    provide() {
        return {
            resources: this.storedResource
        };
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        }
    }
}

</script>