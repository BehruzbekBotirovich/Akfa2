<template>

    <div class="main-container mt-24">
        <img class="bg-img" src="../assets/images/bg4.webp" alt="">
    </div>
    <div class="banner  main-container">
        <div class="p-12 bg-white    md:w-4/6 -translate-y-32" id="akfa">
            <h1 class=" leading-8  mb-4">Производственная компания <span class="text-blue-800 font-extrabold">
                    AKFA </span> высокого качество обслуживания с 2000 года
            </h1>
            <p data-aos="fade-down" data-aos-duration="500" data-aos-delay="400">За это время мы завоевали доверие
                клиентов благодаря качественным изделиям и профессиональному подходу к
                работе. Мы специализируемся на производстве оконных конструкций высокого уровня, стремясь создать уют и
                комфорт в каждом доме. </p>
            <p data-aos="fade-down" data-aos-duration="500" data-aos-delay="400">Наша команда - это опытные специалисты,
                готовые реализовать любые проекты и удовлетворить потребности
                самых
                взыскательных заказчиков. Доверьте нам создание вашего идеального оконного решения!
            </p>
            <p class="hidden md:block" data-aos="fade-down" data-aos-duration="500" data-aos-delay="400">Мы гордимся
                своими технологическими возможностями и современным оборудованием,
                которые позволяют нам
                создавать продукцию высокого качества с соблюдением всех стандартов и требований. Наше производство
                основано
                на инновациях и постоянном совершенствовании процессов, чтобы предложить нашим клиентам самое лучшее в
                мире
                оконных конструкций. Мы стремимся к устойчивому развитию, сохраняя баланс между качеством,
                эффективностью и
                экологической ответственностью в каждом шаге производства.
            </p>
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
h1 {
    font-size: 36px;
    font-weight: 600;
    text-align: center;

    @media(max-width:610px) {
        font-size: 20px;
    }
}

p {
    line-height: 150%;
    font-size: 18px;
    color: #475569;
    margin-bottom: 10px;

    @media (max-width:610px) {
        font-size: 16px;
    }

}

.banner {
    display: flex;
    justify-content: center;


}

.bg-img {
    height: 400px;
    width: 100%;
    object-fit: cover;
}
</style>