<script setup>
// import { RouterLink, RouterView } from 'vue-router'
import HeaderMain from './components/HeaderMain.vue'
import Banner from './components/Banner.vue'
import OurServises from './components/OurServises.vue'

import HowWorking from './components/HowWorking.vue'
import Portfolio from './components/Portfolio.vue'
import ContactUs from './components/ContactUs.vue'
import FooterEnd from './components/FooterEnd.vue'
import OurCustomers from './components/OurCustomers.vue'
import Banner2 from './components/Banner2.vue'
</script>

<template>

    <HeaderMain></HeaderMain>
    <Banner />
    <OurServises></OurServises>




    <div id="workings">
        <HowWorking></HowWorking>
    </div>
    <Portfolio></Portfolio>
    <Banner2></Banner2>
    <OurCustomers></OurCustomers>

    <div id="contact">
        <ContactUs></ContactUs>
    </div>

    <FooterEnd></FooterEnd>
</template>

<style scoped></style>
