<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Store Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resource</base-button>
    </base-card>
    <component :is='selectedTab'></component>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResource from "./AddResource.vue";
export default {
    components:{
        StoredResources,
        AddResource
    },
    data(){
        return {
            selectedTab: 'stored-resources',
            storeResources: [
                {
                    id:'official-guid',
                    title: 'official Guide',
                    description: 'The official Vue.js documentation.',
                    link: 'https://vuejs.org/'
                },
                {
                    id:'google',
                    title: 'Google',
                    description: 'Learn to google...',
                    link: 'https://google.com/'
                }
            ]
        };
    },
    provide(){
        return {
            resources: this.storeResources
        }
    },
    computed: {
        storedResButtonMode(){
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        addResButtonMode(){
            return this.selectedTab === 'add-resource' ? null : 'flat';
        }
    },
    methods:{
        setSelectedTab(tab){
             this.selectedTab = tab
        }
    }
}

</script>