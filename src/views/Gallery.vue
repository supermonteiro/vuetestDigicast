<template>
    <div style="text-align: center; height: 100%">
        <h1>Gallery</h1>

        <h2>There are {{ resultCount }} items ({{selectedItems}} selected)</h2>

        <div class="gallery">
            <gallery-item
            v-for="data in myJson.items"
            v-bind:key="data.id"
            v-bind:id="data.id"
            v-bind:title="data.title"
            v-bind:img="data.img"
            v-bind:isSelected="data.isSelected"
            @increase="increaseSelected"
            @decrease="decreaseSelected"
            />
        </div>
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
            selectedItems: 0,
        };
    },
    components: {
        GalleryItem,
    },
    computed: {
        resultCount() {
            return Object.keys(this.myJson.items).length;
        },
    },
    methods: {
        increaseSelected() {
            this.selectedItems = this.selectedItems + 1;
        },
        decreaseSelected() {
            this.selectedItems = this.selectedItems - 1;
        },
    },
};
</script>

<style lang="scss" scoped>
    .gallery {
        background-color: #514e8e;
        display: inline-flex;
        flex-wrap: wrap;
        width: 50%;
        list-style: none;
        flex-wrap: wrap;
        position: relative;
        text-align: center;
    }
    
</style>
