<template>
    <ul>
        <learning-resource 
        v-for="res in storeResources" 
        :key="res.id" 
        :title="res.title" 
        :description="res.description"
        :link="res.link"
        ></learning-resource>
    </ul>
</template>

<script>
    import LearningResource from './components/learning-resources/LearningResource.vue'
export default {

    components: {
        LearningResource
    },
    data(){
        return {
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
        }
    }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>