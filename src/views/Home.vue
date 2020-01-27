<template>
    <div class="container-fluid px-0" style="max-width: 800px; font-family: 'Helvetica Neue',Arial,sans-serif; font-size: .95rem">
        <div class="mb-4 border" style="height: 180px"></div>
        <CardBlock class="mb-4" title="Услуги" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="mb-4" title="Еда" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="mb-4" title="Развлечение" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="mb-4" v-bind:title="rent_title" v-bind:categories="rent_categories" v-bind:organizations="rent_organizations" />

        <div class="mb-4 border" style="height: 180px"></div>
    </div>
</template>

<script>
    // @ is an alias to /src
    // import HelloWorld from '@/components/HelloWorld.vue'
    import CardBlock from '@/components/CardBlock.vue'

    export default {
        name: 'home',
        data: function() {
            return {
                service_categories: [
                    {
                        id: 1,
                        name: 'Такси'
                    },
                    {
                        id: 2,
                        name: 'Еда'
                    },
                    {
                        id: 3,
                        name: 'Ремонт'
                    },
                    {
                        id: 4,
                        name: 'Развлечение'
                    },
                    {
                        id: 5,
                        name: 'Спорт'
                    },
                    {
                        id: 6,
                        name: 'Для авто'
                    },
                    {
                        id: 7,
                        name: 'Отдых'
                    }
                ],
                services: [
                    {
                        id: 1,
                        title: 'Кафе Интерстеллар',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Выгодные цены, хорошие удобство. График работы: круглосуточно. Вежливые | офицанты. Разнообразный меню. Деликатесы.',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 2,
                        title: 'Ресторан Три Звезды',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Посетите наш ресторан в любое время. Наш адрес г. Тараз, улица Мечнокова, 35 (Напротив Налогового)',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 3,
                        title: 'Пивной Бар Белая Медведица',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Круглосуточно работаем. Адрес: перекресток ул. Абая и Конаева. ',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 4,
                        title: 'Евро Столовое',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Комплексный обет от 550 тг. Акция: Купи чай один раз, а дальше бесплатно. Работаем с 9:00 до 22:00',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 5,
                        title: 'Кафе Компот',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Разнобразный меню и разные напитки. Только самые вкусные. Наш адрес мкр. Жансая торговый дом DavMIR',
                        footer: '8-747-112-63-03'
                    }
                ],
                rent_title: 'Посуточная аренда',
                rent_categories: [
                    {
                        id: 1,
                        name: 'Квартира'
                    },
                    {
                        id: 4,
                        name: 'Комната'
                    },
                    {
                        id: 2,
                        name: 'Хостел'
                    },
                    {
                        id: 3,
                        name: 'Коттедж'
                    },
                    {
                        id: 5,
                        name: 'Дом'
                    }
                ],
                rent_organizations: [
                    {
                        id: 1,
                        title: 'Ночовка',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Посуточная аренда комнаты 3000 тг/ночь, 30% скидка если арендуете на неделю',
                        footer: '@instagram.com/myaccount_official'
                    },
                    {
                        id: 2,
                        title: 'Хостел Даулет',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Койка места 5000 тг/сутка. Обед и ужин с нас. Поставим коммандировочные, есть ИП.',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 3,
                        title: 'Хостел Даулет',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Койка места 5000 тг/сутка. Обед и ужин с нас. Поставим коммандировочные, есть ИП.',
                        footer: '8-747-112-63-03'
                    },
                    {
                        id: 4,
                        title: 'Хостел Даулет',
                        img: 'https://via.placeholder.com/200x100',
                        text: 'Койка места 5000 тг/сутка. Обед и ужин с нас. Поставим коммандировочные, есть ИП.',
                        footer: '8-747-112-63-03'
                    }
                ]
            }
        },
        components: {
            CardBlock
        }
    }
</script>

<style>
    .hide-scroll-bar {
        overflow-x: scroll;
        scrollbar-width: none; /* Firefox */
        -ms-overflow-style: none;  /* Internet Explorer 10+ */
    }
    .hide-scroll-bar::-webkit-scrollbar { /* WebKit */
        width: 0;
        height: 0;
    }
</style>
