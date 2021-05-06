<template>
    <section class="albums">
        <div class="row" v-if="!loading">
            <div
                class="col"
                v-for="(album, index) in albumList.response"
                :key="index"
            >
                <Album :info="album" />
            </div>
        </div>
        <div v-else class="load">
            Loading...
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import Album from '@/components/Album.vue';

export default {
    name: 'Albumlist',
    components: {
        Album,
    },
    data() {
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            albumList: [],
            loading: true,
        };
    },
    created() {
        this.getAlbum();
    },
    methods: {
        getAlbum() {
            //API CALLS
            axios
                .get(this.apiURL)
                .then((res) => {
                    this.albumList = res.data;
                    this.loading = false;
                })
                .catch((err) => {
                    console.log('Error', err);
                });
        },
    },
};
</script>

<style scoped lang="scss">
.albums {
}

.row {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;

    .col {
        flex-basis: calc(100% / 8 - 20px);
        background: #2e3a46;
        margin: 10px;
        color: #fff;
    }
}
</style>
