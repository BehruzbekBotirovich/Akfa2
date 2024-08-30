<template>

    <header class="fixed top-0 left-0 z-20 bg-white w-full shadow">
        <div class="flex gap-10 py-1 main-container md:justify-center justify-between items-center  ">
            <!-- Desktop Menu -->
            <a-menu mode="horizontal" class="items-center hidden lg:block" style="width: 520px;">
                <!-- Menu items go here -->
                <a-menu-item key="5">
                    <a @click.prevent="scrollTo('main')" href="#">Главная</a>
                </a-menu-item>
                <a-menu-item key="1">
                    <a @click.prevent="scrollTo('servise')" href="#">Услуги</a>
                </a-menu-item>
                <a-menu-item key="2">
                    <a @click.prevent="scrollTo('akfa')" href="#">О компании</a>
                </a-menu-item>

                <a-menu-item key="3">
                    <a @click.prevent="scrollTo('contact')" href="#">Контакты</a>
                </a-menu-item>
                <a-menu-item key="4">
                    <a @click.prevent="scrollTo('portfolio')" href="#">Портфолио</a>
                </a-menu-item>
            </a-menu>
            <div class="md:hidden">
                <img src="../assets/images/logo.png" alt="" loading="lazy" width="36">
            </div>
            <!-- Burger Icon for Mobile -->
            <div class="lg:hidden">
                <a-button type="ghost" @click="showMobileMenu = !showMobileMenu" class="flex items-center text-xl">
                    <MenuUnfoldOutlined :class="showMobileMenu ? 'rotating' : 'inactive-class'" />
                </a-button>
            </div>


        </div>

        <!-- Mobile Menu -->
        <Transition name="slide-fade">
            <a-menu v-if="showMobileMenu" mode="vertical"
                class="lg:hidden fixed top-0 left-0 w-3/4 z-10 h-screen bg-white shadow-lg">
                <!-- Menu items go here -->

                <a-menu-item :class="{ active: activeSection === 'about-us' }" key="1">
                    <a @click.prevent="scrollTo('about-us')" href="#">Услуги</a>
                </a-menu-item>
                <a-menu-item :class="{ active: activeSection === 'product' }" key="2">
                    <a @click.prevent="scrollTo('product')" href="#">Продукция</a>
                </a-menu-item>
                <a-menu-item :class="{ active: activeSection === 'workings' }" key="3">
                    <a @click.prevent="scrollTo('workings')" href="#">О компании</a>
                </a-menu-item>
                <a-menu-item :class="{ active: activeSection === 'faq' }" key="4">
                    <a @click.prevent="scrollTo('faq')" href="#">Вопрос-ответ</a>
                </a-menu-item>
                <a-menu-item :class="{ active: activeSection === 'contact' }" key="5">
                    <a @click.prevent="scrollTo('contact')" href="#">Контакты</a>
                </a-menu-item>

            </a-menu>
        </Transition>

        <a-modal v-model:open="open" title="Вызвать замерщика на дом" @ok="handleOk" :footer="false">
            <ZamerWindow></ZamerWindow>
        </a-modal>
    </header>
    <nav class="md:flex justify-between py-4 main-container mt-14">
        <div class="md:flex gap-4n">
            <div class="hidden md:block"><img src="../assets/images/logo.png" width="60" height="60"></div>
            <div>
                <h3 class="text-xl font-bold "> Название компании</h3>
                <p>​​​​​​​Изготовление и установка окон в Москве </p>
            </div>
        </div>


        <div class="flex items-center gap-4 ">
            <div class="rounded-full p-2 bg-slate-300 w-fit"><svg width="24px" height="24px" viewBox="0 0 24 24"
                    fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M14 2C14 2 16.2 2.2 19 5C21.8 7.8 22 10 22 10" stroke="#1C274C" stroke-width="1.5"
                        stroke-linecap="round" />
                    <path
                        d="M14.207 5.53564C14.207 5.53564 15.197 5.81849 16.6819 7.30341C18.1668 8.78834 18.4497 9.77829 18.4497 9.77829"
                        stroke="#1C274C" stroke-width="1.5" stroke-linecap="round" />
                    <path
                        d="M10.0376 5.31617L10.6866 6.4791C11.2723 7.52858 11.0372 8.90532 10.1147 9.8278C10.1147 9.8278 10.1147 9.8278 10.1147 9.8278C10.1146 9.82792 8.99588 10.9468 11.0245 12.9755C13.0525 15.0035 14.1714 13.8861 14.1722 13.8853C14.1722 13.8853 14.1722 13.8853 14.1722 13.8853C15.0947 12.9628 16.4714 12.7277 17.5209 13.3134L18.6838 13.9624C20.2686 14.8468 20.4557 17.0692 19.0628 18.4622C18.2258 19.2992 17.2004 19.9505 16.0669 19.9934C14.1588 20.0658 10.9183 19.5829 7.6677 16.3323C4.41713 13.0817 3.93421 9.84122 4.00655 7.93309C4.04952 6.7996 4.7008 5.77423 5.53781 4.93723C6.93076 3.54428 9.15317 3.73144 10.0376 5.31617Z"
                        stroke="#1C274C" stroke-width="1.5" stroke-linecap="round" />
                </svg></div>
            <span class="font-extrabold md:text-xl "> +998 99 999 99 99</span>
            <a-button type="primary" size="large" class="hidden md:block" @click="showModal"> Заказать звонок</a-button>
        </div>
    </nav>



</template>
<script setup>
import ZamerIcon from './icons/ZamerIcon.vue'
import ZamerWindow from './windows/ZamerWindow.vue'
import { ref, onMounted, onUnmounted } from 'vue';
import { MenuUnfoldOutlined, MenuFoldOutlined } from '@ant-design/icons-vue';
const activeSection = ref('');
const showMobileMenu = ref(false); // State to show/hide mobile menu

// moldalka ant vue
const open = ref(false);
const showModal = () => {
    open.value = true;
};
const handleOk = e => {
    console.log(e);
    open.value = false;
};

// menu boyicha navigatsiya scroll boyicha
const scrollTo = (elementId) => {
    const element = document.getElementById(elementId);
    showMobileMenu.value = false;
    if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
        activeSection.value = elementId;
    }
};

const handleScroll = () => {
    const sections = ['about-us', 'product', 'workings', 'faq', 'contact'];
    const scrollPosition = window.scrollY + window.innerHeight / 2;

    for (const section of sections) {
        const element = document.getElementById(section);
        if (element) {
            const { offsetTop, offsetHeight } = element;
            if (scrollPosition >= offsetTop && scrollPosition < offsetTop + offsetHeight) {
                activeSection.value = section;
                break;
            }
        }
    }
};

onMounted(() => {
    window.addEventListener('scroll', handleScroll);
    handleScroll(); // To set the active section on initial load
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
});
</script>
<style scoped>
.activeItem>span>a {
    color: blue;
    padding-bottom: 13px;
    border-bottom: 2px solid blue;
    transition: all 0.2s easy;
}


:deep(.ant-menu-horizontal) {
    border-bottom: none;
}

:deep(.ant-menu-item-selected) {
    color: black !important;

}

:deep(.ant-menu-item-selected::after) {
    display: none;
}

/* Transition for Mobile Menu */
.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: transform 0.3s ease, opacity 0.3s ease;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    transform: translateX(-100%);
    opacity: 0;
}

.v-enter-active,
.v-leave-active {
    transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}

.rotating {
    transform: rotate(180deg);
}
</style>
