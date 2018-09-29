<template>
    <div class="Search">
        <input type="text" class="Search__input" v-model="query" @keyup.13="search()">
        <button class="Search__button" @click="search()">Найти</button>
        <div v-if="loading" class="Search__loading">Загрузка</div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                query: ''
            }
        },
        computed: {
            loading () {
                return this.$store.getters.loading
            }
        },
        methods: {
            search() {
                this.$store.dispatch('search', this.query)
            }
        }
    }
</script>