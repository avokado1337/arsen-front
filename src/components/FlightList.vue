<script>
export default {
    data() {
        return {
            flights: []
        }
    }
}
</script>

<template>
    <div class="wrapper">
        <div class="container">
            <div class="header">

            </div>
            <div class="flight" v-for="flight in flights" :key="id">
            </div>
        </div>
    </div>
</template>

<style>
</style>