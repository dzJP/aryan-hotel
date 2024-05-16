<template>
    <div class="container">
        <h2 class="hotel-title">
            <span>{{ hotel.name }}</span>
        </h2>
        <div class="hotel-location">
            <h3>{{ hotel.address }}</h3>
            <p>Distance from your location: {{ distance }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            hotel: {
                name: 'Aryan Butik Otel',
                address: 'Şar, 221 Karaman Sk. no:22, 47100 Artuklu/Mardin, Turkey',
                location: { lat: 37.31425, lng: 40.73504 } // Hotel's latitude and longitude
            },
            userLocation: null,
            distance: null
        };
    },
    mounted() {
        this.getUserLocation();
    },
    methods: {
        getUserLocation() {
            if ('geolocation' in navigator) {
                navigator.geolocation.getCurrentPosition(
                    position => {
                        this.userLocation = {
                            lat: position.coords.latitude,
                            lng: position.coords.longitude
                        };
                        this.calculateDistance();
                    },
                    error => {
                        console.error('Error getting user location:', error);
                    }
                );
            } else {
                console.error('Geolocation is not supported by this browser.');
            }
        },
        calculateDistance() {
            const { lat: lat1, lng: lon1 } = this.userLocation;
            const { lat: lat2, lng: lon2 } = this.hotel.location;
            const R = 6371; // Radius of the earth in km
            const dLat = this.deg2rad(lat2 - lat1);
            const dLon = this.deg2rad(lon2 - lon1);
            const a =
                Math.sin(dLat / 2) * Math.sin(dLat / 2) +
                Math.cos(this.deg2rad(lat1)) *
                Math.cos(this.deg2rad(lat2)) *
                Math.sin(dLon / 2) *
                Math.sin(dLon / 2);
            const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
            const distance = R * c; // Distance in km
            this.distance = distance.toFixed(2) + ' km';
        },
        deg2rad(deg) {
            return deg * (Math.PI / 180);
        }
    }
};
</script>
<style>

.hotel-title {
    text-align: center;
    font-size: 3em;
    letter-spacing: 5px;
}

h3 {
    font-size: 1.3em;
    margin-bottom: 5%;
}

p {
    font-size: 1.5em;
}

.container {
    display: inline-flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    max-height: 400px;
    max-width: 80%;
    padding: 2rem 0.2rem 3rem;
    margin-top: 5%;
    background-color: var(--testcolor);
    border-radius: 2rem;
    border: .2rem solid #868686;
    font-family: 'Futura', sans-serif;

}

.hotel-location {
    text-align: center;
    padding: 20px;
}
</style>
