<template>
    <div class="main-container py-12">

        <div class="md:flex ">
            <div class="md:w-1/3 space-y-10 pb-20 px-8 relative">

                <h1 class="text-4xl font-semibold">Контакты </h1>

                <div class="flex items-center gap-4 text-lg">
                    <TelIcon></TelIcon>
                    <span>{{ telnumber1 }}</span>
                </div>
                <div class="flex items-center gap-5 text-lg">
                    <LocationIcon></LocationIcon> {{ locationtitle }}
                </div>
                <div class="flex items-center gap-5 text-lg">
                    <PochtaIcon></PochtaIcon>{{ email }}
                </div>
            </div>


            <div class="md:w-2/3 ">
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d5401.435578290004!2d69.26179412519875!3d41.316824590416786!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38ae8b28ff2ba12d%3A0x4e5a532012c4ed3a!2z0J_QsNGA0Log0JDQvdGF0L7RgA!5e0!3m2!1sru!2s!4v1724678186022!5m2!1sru!2s"
                    width="100%" height="400" style="border:0;" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>

        </div>
    </div>
</template>

<script setup>
import TelIcon from './icons/TelIcon.vue'
import LocationIcon from './icons/LocationIcon.vue'
import PochtaIcon from './icons/PochtaIcon.vue'




// html data 
const telnumber1 = '+998 94 929 08 02'
const telnumber2 = '+998 94 929 00 00'
const locationtitle = 'qayerdir qayer yerni burchagida '
const email = 'beha@gmail.com'

// social link

</script>

<style scoped>
.icons-media>li {
    transition: all .3s ease;
}

.icons-media>li:hover {
    scale: 1.1;

}

.no-resize {
    resize: none;
}

:deep(.ant-form-item-required) {
    font-weight: 600;
    color: #2F2F51;
    font-size: 18px;

}

:deep(.ant-form-item-required::before) {
    display: none !important;
}
</style>
