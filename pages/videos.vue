<template>
    <div>
        <h1>videos</h1>
        <div v-for="video in videos" :key="video.id">
            {{video.name}}
        </div>
        <nuxt-child />
    </div>
</template>

<script>
    export default {
        data() {
            return {
                videos: [
                    {
                        id:1,
                        name: "sakib tutorial"
                    },
                    {
                        id:2,
                        name: "rayhan tutorial"
                    }
                ]
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>