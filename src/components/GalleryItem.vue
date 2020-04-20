<template>
    <div v-bind:class="[isSelected ? checkedClass : '', itemClass]">
        <p>{{title}}</p>
        <img v-bind:src="'img/'+img">
        <button class="check" v-on:click="selectItem">
            <i class="far fa-check-circle"/>
        </button>
        <button class="uncheck" v-on:click="removeItem">
            <i class="far fa-times-circle"/>
        </button>
    </div>
</template>


<script>

export default {
    name: 'GalleryItem',
    props: {
        id: Number,
        title: String,
        img: String,
        isSelected: Boolean,
    },

    data() {
        return {
            checkedClass: 'checked',
            itemClass: 'item',
        };
    },
    methods: {
        selectItem() {
            if (!this.selected) {
                this.$emit('increase');
                this.selected = true;
            }
        },
        removeItem() {
            if (this.selected) {
                this.$emit('decrease');
                this.selected = false;
            }
        },
    },
};
</script>

<style lang="scss" scoped>

.item {
    margin: 2% 2% 2% 2%;
    position: relative;
    overflow: hidden;
    filter: brightness(70%);
}

@media (min-width: 1200px) {
  .item {
    width: 20%;
    }
}

@media (min-width: 576px) and (max-width: 1200px) {
  .item {
    width: 25%;
    }
}

@media (max-width: 576px){
  .item {
    width: 75%;
    }
}

.item::after {
    display: block;
    content: '';
    /* 16:9 aspect ratio */
    padding-bottom: 56.25%;
}

.item img{
   position: absolute;
   top: 0;
   left: 0;
   bottom: 0;
   right: 0;
   text-align: center;
   width: 100%;
   object-fit: fill;
}

.item p {
    position: inherit;
    color: white;
    z-index: 1;
    background-color: gray;
    margin-top: -1px;
}

.item:hover {
    filter: brightness(100%);
}

.checked {
    filter: brightness(100%);
}

.check {
    z-index: 1;
    position: absolute;
    color: white;
    font-size: 32px;
    left: 0;
    bottom: 2px;
    background-color: transparent;
    border: none;
}

.uncheck {
    z-index: 1;
    position: absolute;
    color: white;
    font-size: 32px;
    right: 0;
    bottom: 2px;
    background-color: transparent;
    border: none;
}

</style>
