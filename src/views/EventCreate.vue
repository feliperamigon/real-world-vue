<template>
    <div>
        <h1>Create an Event, {{ user.name }}</h1>
        <p>This event was created by {{ user.id }}</p>
        <p>There are {{ catLength }} categories</p>
        <ul>
            <li v-for="category in categories" :key="category">{{ category }}</li>
        </ul>
    </div>
</template>

<script>
    import { mapState } from 'vuex';

    export default {
        computed: {
            catLength() {
                return this.$store.getters.catLength;
            },
            ...mapState(['categories', 'user'])
        }
    }
</script>

<style scoped>

</style>