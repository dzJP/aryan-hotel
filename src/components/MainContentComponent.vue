<template>
    <div class="main-content">
        <div class="image-gallery" v-if="images.length > 0">
            <img :src="currentImage" :key="currentIndex" class="image" @click="toggleSize"
                :class="{ enlarged: enlarged }" />
            <div v-if="enlarged" class="navigation-buttons">
                <button class="nav-button left" @click="prevImage">&#10094;</button>
                <button class="nav-button right" @click="nextImage">&#10095;</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            images: [
                require('@/assets/genel/genel1.png'),
                require('@/assets/genel/genel2.png'),
                // Add URLs of your images here
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

.image-gallery {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 100%;
}

.image {
    width: 40%;
    height: auto;
    cursor: pointer;
    border-radius: 10%;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
    transition: transform 0.3s ease;
    margin-left: 5%;
}

.image:not(.enlarged):hover {
    border: 2px solid var(--blue-heaven);
    transform: scale(1.05);
}

.enlarged {
    justify-content: center;
    width: 80%;
    height: auto;
    position: relative;
    left: 5%;
    top: -6%;
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
