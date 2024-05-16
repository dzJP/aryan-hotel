<template>
    <div class="main-content">
        <div class="content-wrapper">
            <div class="image-gallery" v-if="images.length > 0">
                <img :src="currentImage" :key="currentIndex" class="image" @click="toggleSize"
                    :class="{ enlarged: enlarged }" />
                <div v-if="enlarged" class="navigation-buttons">
                    <button class="nav-button left" @click="prevImage">&#10094;</button>
                    <button class="nav-button right" @click="nextImage">&#10095;</button>
                </div>
            </div>
            <HotelLocationInfoComponent />
        </div>
    </div>
</template>

<script>
import HotelLocationInfoComponent from './HotelLocationInfoComponent.vue';

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
            currentIndex: 0,
            intervalId: null,
            enlarged: false // Track if image is enlarged or not
        };
    },
    computed: {
        currentImage() {
            return this.images[this.currentIndex];
        }
    },
    mounted() {
        if (this.images.length > 1) {
            this.startSlideshow();
        }
    },
    beforeUnmount() {
        clearInterval(this.intervalId);
    },
    methods: {
        startSlideshow() {
            this.intervalId = setInterval(() => {
                if (!this.enlarged) {
                    this.currentIndex = (this.currentIndex + 1) % this.images.length;
                }
            }, 5000);
        },
        toggleSize() {
            this.enlarged = !this.enlarged;
            if (this.enlarged) {
                clearInterval(this.intervalId);
            } else {
                this.startSlideshow();
            }
        },
        nextImage() {
            this.currentIndex = (this.currentIndex + 1) % this.images.length;
        },
        prevImage() {
            this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
        }
    }
};
</script>

<style>
.main-content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.content-wrapper {
    display: flex;
    gap: 10em;
    height: 50vh;
}

.image-gallery {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    height: auto;
}

.image {
    width: 800px;
    height: auto;
    cursor: pointer;
    border-radius: 10%;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
    box-sizing: border-box;
    transition: transform 0.3s ease;
}


.enlarged {
    justify-content: center;
    width: 100%;
    height: auto;
    border: none;
}
.nav-button {
    background: transparent;
    border: none;
    font-size: 24px;
    cursor: pointer;
    color: black;
    position: absolute;
}

.nav-button.left {
    left: 10px;
}

.nav-button.right {
    right: 10px;
}
</style>
