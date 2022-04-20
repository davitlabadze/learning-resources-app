<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')">Store Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')">Add Resource</base-button>
    </base-card>
    <component :is='selectedTab'></component>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import Addresource from "./Addresource.vue";
export default {
    component:{
        StoredResources,
        Addresource
    },
    data(){
        return {
            selectedTab: 'stored-resources'
        };
    },
    methods:{
        setSelectedTab(tab){
             this.selectedTab = tab
        }
    }
}

</script>