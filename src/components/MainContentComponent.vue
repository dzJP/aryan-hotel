<template>
    <div class="main-content">
            <div class="image-gallery">
                <img v-for="(image, index) in images" :key="index" :src="image"
                    :class="{ 'image': true, 'active': index === activeIndex }" />
            </div>
            <HotelLocationInfoComponent class="hotel-info"/>
        </div>
</template>

<script>
import HotelLocationInfoComponent from '@/components/HotelLocationInfoComponent.vue';
export default {
    components: {
        HotelLocationInfoComponent
    },
    data() {
        return {
            images: [
                require('@/assets/odalar/odalar1.png'),
                require('@/assets/odalar/odalar2.png'),
                require('@/assets/odalar/odalar3.png'),
                require('@/assets/odalar/odalar4.png'),
                require('@/assets/odalar/odalar5.png'),
                require('@/assets/odalar/odalar6.png'),
                require('@/assets/odalar/odalar7.png'),
                require('@/assets/odalar/odalar8.png'),
                require('@/assets/odalar/odalar9.png'),
                require('@/assets/odalar/odalar10.png'),
                require('@/assets/odalar/odalar11.png'),
                require('@/assets/odalar/odalar12.png'),
                require('@/assets/odalar/odalar13.png'),
                require('@/assets/odalar/odalar14.png'),
                require('@/assets/odalar/odalar15.png'),
                require('@/assets/odalar/odalar16.png'),
                require('@/assets/odalar/odalar17.png'),
                require('@/assets/odalar/odalar18.png'),
                require('@/assets/odalar/odalar19.png'),
                require('@/assets/odalar/odalar20.png'),
                require('@/assets/odalar/odalar21.png'),
                require('@/assets/odalar/odalar22.png'),
                require('@/assets/odalar/odalar23.png'),
                require('@/assets/odalar/odalar24.png'),
                require('@/assets/odalar/odalar25.png'),
                require('@/assets/odalar/odalar26.png'),
                require('@/assets/odalar/odalar27.png'),
                require('@/assets/odalar/odalar28.png'),
                require('@/assets/odalar/odalar29.png'),
                require('@/assets/odalar/odalar30.png'),
                require('@/assets/odalar/odalar31.png'),
                require('@/assets/odalar/odalar32.png'),
                require('@/assets/odalar/odalar33.png')
            ],
            activeIndex: 0,
            fadingOut: false
        };
    },
    mounted() {
        setInterval(this.nextImage, 5000); // Change image every 5 seconds
    },
    methods: {
        nextImage() {
            this.fadingOut = true;
            setTimeout(() => {
                this.activeIndex = (this.activeIndex + 1) % this.images.length;
                this.fadingOut = false;
            }, 1000); // Wait for fade out transition to complete (1 second) before changing image
        }
    }
};
</script>

<style scoped>

.main-content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.image-gallery {
    width: 100%;
}

.image {
    position: absolute;
    top: 25%;
    left: 10%;
    width: 800px;
    opacity: 0;
    transition: opacity 2s ease;
    border-radius: 5%;
    box-sizing: border-box;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
}

.image.active {
    opacity: 1;
}

.image.active.fading-out {
    opacity: 0;
}

.hotel-info {
    margin-right: 10%;
}
</style>