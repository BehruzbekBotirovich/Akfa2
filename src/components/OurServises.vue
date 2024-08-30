<template>
    <div class="main-container py-14 ">

        <h1 class="text-4xl font-bold  text-center mb-4 md:mb-12">Наши услуги </h1>

        <div class="servises-container space-y-6 " id="servise">

            <div v-for="(servise, index)  of Servises" :key="index" class="servise-wrapper">
                <div class="servise-img" :data-aos="(index + 1) % 2 == 0 ? 'fade-right' : 'fade-left'"
                    data-aos-duration="500" data-aos-delay="200">
                    <img :src="servise.img" alt="">
                </div>
                <div class="servise-title space-y-2 md:space-y-6"
                    :data-aos="(index + 1) % 2 == 1 ? 'fade-right' : 'fade-left'" data-aos-duration="500"
                    data-aos-delay="200">
                    <h1 class=" md:text-2xl font-bold">{{ servise.title }} </h1>
                    <p>{{ servise.text }} </p>
                    <a-button type="primary" class="font-bold "  @click="showModal"> Заказать</a-button>
                </div>
            </div>

        </div>
        <a-modal v-model:open="open" title="Вызвать замерщика на дом" :footer="false" @ok="handleOk">
            <ZamerWindow></ZamerWindow>
        </a-modal>
    </div>


</template>


<script setup>
import ZamerWindow from './windows/ZamerWindow.vue';
import { ref } from 'vue';
const open = ref(false);
const showModal = () => {
    open.value = true;
};
const handleOk = e => {
    console.log(e);
    open.value = false;
};


import img1 from '../assets/images/ours1.webp'
import img2 from '../assets/images/ours2.webp'
import img3 from '../assets/images/ours3.webp'
import img4 from '../assets/images/ours4.webp'

const Servises = [
    {
        img: img1,
        title: 'Изготовление и установка ПВХ окон',
        text: 'Наполнение сайта в соответствии с требованиями поисковых систем. Необходима для успешного продвижения в ТОП-10.',
    },
    {
        img: img2,
        title: 'Остекление балконов и лоджий',
        text: 'Для комфортного использования балкона мы предлагаем наиболее качественные системы остекления',
    },
    {
        img: img3,
        title: 'Входные и офисные двери',
        text: 'Применяются конструкции с привлекательным внешним видом, устойчивые к интенсивным функциональным нагрузкам.',
    },
    {
        img: img4,
        title: 'Жалюзи',
        text: 'Для пластиковых окон предлагаются тканевые и ламельные кассетные системы, позволяющие разместить жалюзи непосредственно у стекла',
    },



]
</script>


<style scoped>
.servises-container>.servise-wrapper:nth-child(odd) {
    .servise-title {
        order: 1;
    }

    .servise-img {
        order: 2;
    }
}

.servise-wrapper {
    gap: 30px;
    display: flex;
    align-items: center;

    @media (max-width:610px) {
        gap: 10px;
    }
}

.servise-title {
    width: 50%;
}

.servise-img {
    width: 50%;

    img {
        width: 100%;
        aspect-ratio: 6/3;
        object-fit: cover;
        border-radius: 10px;
    }

    @media (max-width:620px) {
        img {
            aspect-ratio: 1/1;
        }
    }

}
</style>