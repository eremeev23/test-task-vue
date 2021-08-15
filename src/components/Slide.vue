<template>
    <div class="slide">
        <img :class="'img'" :src="require('./img/' + item_data.img)" alt="">
    </div>
</template>

<script>
export default {
    name: 'slide',
    props: {
        item_data: {
            type: Object,
            default: () => {}
        },
        gallery_data: {
            type: Array,
            default: () => []
        },
    },
    data(){
        return {
        windowWidth: null,
        }
    },
    created() {
        window.addEventListener('resize', this.checkScreen);
        this.checkScreen();
    },
    methods: {
        checkScreen(){
            const img = document.querySelectorAll('.img');
            const slide = document.querySelectorAll('.slide');
            this.windowWidth = document.documentElement.clientWidth;
            img.forEach((item) => item.style.width = `${this.windowWidth}px`);
            slide.forEach((item) => item.style.height = img.style.height + 'px');
            return;
        }
    },
    mounted() {
        window.addEventListener('resize', this.checkScreen);
        this.checkScreen();
    }
}
</script>

<style scoped>
.img {
    max-width: 1110px;
}
</style>