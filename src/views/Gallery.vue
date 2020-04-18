<template>
    <div class="gallery">
        <h1>Gallery</h1>

        <h2>There are {{ resultCount }} items</h2>

        
        
    </div>

</template>

<script>
import json from '../../public/json/item-list.json';
import GalleryItem from '../components/GalleryItem.vue';

export default {
    name: 'Gallery',
    data() {
        return {
            myJson: json,
        };
    },
    components: {
        GalleryItem,
    },
    computed: {
        resultCount() {
            if (this.myJson.length > 0 && this.myJson.length != null)
                return this.myJson.length;
            else
                return 0;
        },
        console: () => console,
    },
    methods: {
        dataLog() {
            console.log(this.$data);
        },
    },
};
</script>

<style lang="scss" scoped>

</style>
