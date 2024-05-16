<template>
    <div class="main-content">
        <div class="image-gallery">
            <img v-for="(image, index) in images" :key="index" :src="image"
                :class="{ 'image': true, 'active': index === activeIndex }" @click="openModal(index)" />
        </div>
        <HotelLocationInfoComponent class="hotel-info" />
        <div class="modal" v-if="modalOpen" @click="toggleModal">
            <span class="close" @click="closeModal">&times;</span>
            <img :src="images[activeIndex]" class="modal-content">
            <span class="prev" @click.stop="prevImage">&#10094;</span>
            <span class="next" @click.stop="nextImage">&#10095;</span>
        </div>
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
            fadingOut: false,
            modalOpen: false,
            intervalId: null
        };
    },
    mounted() {
        this.startSlideshow();
    },
    methods: {
        startSlideshow() {
            this.intervalId = setInterval(this.nextImage, 5000);
        },
        stopSlideshow() {
            clearInterval(this.intervalId);
        },
        openModal(index) {
            this.activeIndex = index;
            this.modalOpen = true;
            this.stopSlideshow();
        },
        closeModal() {
            this.modalOpen = false;
            this.startSlideshow();
        },
        toggleModal() {
            this.modalOpen = !this.modalOpen;
            if (!this.modalOpen) {
                this.startSlideshow();
            }
        },
        nextImage() {
            if (!this.modalOpen) {
                this.fadingOut = true;
                setTimeout(() => {
                    this.activeIndex = (this.activeIndex + 1) % this.images.length;
                    this.fadingOut = false;
                }, 1000);
            } else {
                this.activeIndex = (this.activeIndex + 1) % this.images.length;
            }
        },
        prevImage() {
            if (!this.modalOpen) {
                this.fadingOut = true;
                setTimeout(() => {
                    this.activeIndex = (this.activeIndex - 1 + this.images.length) % this.images.length;
                    this.fadingOut = false;
                }, 1000);
            } else {
                this.activeIndex = (this.activeIndex - 1 + this.images.length) % this.images.length;
            }
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
    cursor: pointer;
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

.modal {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
}

.modal-content {
    margin: auto;
    display: block;
    width: 80%;
    max-width: 800px;
    max-height: 80%;
    cursor: pointer;
}

.close {
    color: #fff;
    font-size: 2em;
    position: absolute;
    top: 20px;
    right: 30px;
    cursor: pointer;
}

.prev,
.next {
    color: #fff;
    font-size: 3em;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
}

.prev {
    left: 20px;
}

.next {
    right: 20px;
}
</style>