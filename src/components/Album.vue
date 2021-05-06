<template>
    <main>
        <div class="grid">
            <div class="album">
                <img :src="info.poster" alt="" />
                <h3>{{ info.title }}</h3>
                <h4>{{ info.author }}</h4>
                <h4>{{ info.year }}</h4>
                <h5>{{ info.genre }}</h5>
            </div>
        </div>
    </main>
</template>

<script>
export default {
    name: 'Album',
    props: ['info'],
};
</script>

<style scoped lang="scss">
.grid {
    /* display: flex; */
    .album {
        text-align: center;
        max-width: 1170px;
        margin: 0 auto;
    }

    img {
        width: 100px;
        padding: 10px;
    }

    h4 {
        color: #888;
    }
}
</style>
