<template>
    <div>
        <AppHeader/>
        <h1>About dadjokes</h1>
        <p>This is an app that displays corny and jokes</p>
    </div>
</template>

<script>
    import AppHeader from '../components/AppHeader';
    export default {
        head(){
            return {
                title: "about the app",
                meta: [
                    {
                        hid: 'description',
                        name: 'description',
                        content: "You can learn more about daddy jokes"
                    }
                ]
            }
        },
        component:{
            AppHeader
        }
    }
</script>

<style lang="scss" scoped>

</style>