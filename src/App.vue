<template>
    <the-header title="RemmberMe"></the-header>
    <stored-resources :resources="storeResources"></stored-resources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue'
   import StoredResources from './components/learning-resources/StoredResources.vue'
export default {

    components: {
        StoredResources,
        TheHeader
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