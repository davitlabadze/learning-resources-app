<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Store Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resource</base-button>
    </base-card>
    <keep-alive>
        <component :is='selectedTab'></component>
    </keep-alive>
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
            resources: this.storeResources,
            addResource: this.addResource
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
        },
        addResource(title,description,url){
            const newResource = {
                id: new Date().toISOString(),
                title:title,
                description:description,
                link: url
            };
            this.storeResources.unshift(newResource);
            this.selectedTab = 'stored-resources'
        }
    }
}

</script>