<template>
    <div id="home">
        <HeaderComponent />
    </div>
    <MainContentComponent />
    <AboutComponent />
    <ContactComponent />
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import MainContentComponent from '@/components/MainContentComponent.vue';
import AboutComponent from '@/components/AboutComponent.vue';
import ContactComponent from '@/components/ContactComponent.vue';

export default {
    components: {
        HeaderComponent,
        MainContentComponent,
        AboutComponent,
        ContactComponent
    }
}
</script>