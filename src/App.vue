<script setup>
import 'bootstrap'
// import Header from '@/components/Header.vue'
// import Footer from '@/components/Footer.vue'
</script>

<template>
    <div id="main" class="mb-3">
        <Header />
        <div class="container main__container">
            <div class="row main__row">
                <router-view />
            </div>
            <Footer />
        </div>    
    </div>
</template>

<script>
export default {
    name: 'CICTCPC 2023 RANKING',
    watch: {
        $route: {
            immediate: true,
            handler (to, from) {
                document.title = (to.meta.title) ?  (to.meta.title + ' | DATFLIX') : 'DATFLIX'
            }
        }
    }
}

</script>

<style scoped>
.alert-warning {
    border-radius: 0%;
    border: 1px solid #b8b612;
    background-color: #000;
    color: white;
}
</style>
