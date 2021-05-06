<template>
    <div id="app">
        <!-- Header -->
        <Header />
        <!-- Main -->
        <Albumlist />
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Albumlist from '@/components/Albumlist.vue';

export default {
    name: 'App',
    components: {
        Header,
        Albumlist,
    },
};
</script>

<style lang="scss">
body {
    background: #1d2d3c;
    font-family: sans-serif;
}
</style>
