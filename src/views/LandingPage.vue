<template>
    <HeaderComponent />
    <MainContentComponent />
    <ContactComponent />
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import MainContentComponent from '@/components/MainContentComponent.vue';
import ContactComponent from '@/components/ContactComponent.vue';

export default {
    components: {
        HeaderComponent,
        MainContentComponent,
        ContactComponent
    }
}
</script>