<template>
    <div class="container-fluid px-0" style="max-width: 800px; font-family: 'Helvetica Neue',Arial,sans-serif; font-size: .95rem">
        <div class="mb-4 d-flex flex-column justify-content-center align-items-center" style="height: 200px">
            <div class="h3">Burnoe.com</div>
            <div class="d-flex">
                <div class="small border text-center" style="width: 70px">
                    <div>Сегодня</div>
                    <div>+10 +12<sup>0</sup></div>
                </div>
                <div class="small border text-center" style="width: 70px">
                    <div>Завтра</div>
                    <div>+15 +16<sup>0</sup></div>
                </div>
            </div>
        </div>

        <div class="mb-3  article-rounded-top" style="height: 1rem;">

        </div>

        <div class="mb-2 mb-md-4">
            <div class="hide-scroll-bar d-flex">
                <div class="ml-3 border" style="width: 150px; min-width: 150px" v-for="chosen in chosens" v-bind:key="chosen.id">
                    <div class="text-center">
                        <img src="https://via.placeholder.com/80x80" class="img-fluid rounded-circle" alt="" />
                    </div>
                    <div class="text-center" style="font-size: 0.8rem; height: 2.4rem;">
                        {{chosen.title}}
                    </div>
                </div>
            </div>
        </div>

        <div v-show="false" class="my-4 py-2">
            <div class="hide-scroll-bar d-flex">
                <div class="ml-3 border article-rounded-top" style="width: 161px; min-width: 161px" v-for="burnoe_new in burnoe_news" v-bind:key="burnoe_new.id">
                    <div class="">
                        <img src="https://via.placeholder.com/160x100" class="article-rounded-top" alt="" />
                    </div>
                    <div class="p-2" style="font-size: 0.8rem;">
                        {{burnoe_new.title}}
                    </div>
                </div>
            </div>
        </div>

        <div class="my-2 my-md-4">
            <div class="d-flex justify-content-between align-items-center">
                <div>
                    <BlockHeader class="d-none d-sm-block">Объявлении</BlockHeader>
                    <div class="ml-3 py-1" style="font-size: 0.85rem;" v-for="advert in articles" v-bind:key="advert.id">
                        {{advert.title}}
                    </div>
                </div>
                <div class="d-none d-sm-block pr-md-4" style="max-width: 14rem;">
                    <img src="https://via.placeholder.com/200x200" class="img-fluid" alt="" />
                </div>
            </div>
        </div>

        <div class="my-4 py-4 bg-dark">
            <BlockHeader class="text-white">Новости</BlockHeader>
            <div class="hide-scroll-bar d-flex">
                <div class="ml-3  mr-md-3 position-relative " style="width: 221px; min-width: 221px" v-for="burnoe_new in burnoe_news" v-bind:key="burnoe_new.id">
                    <div class="">
                        <img v-bind:src="burnoe_new.photo" class="img-fluid" alt="" />
                    </div>
                    <div class="position-absolute p-2 h-100 d-flex align-items-end" style="bottom: 0; background-color: rgba(0,0,0,0.45)">
                        <span class="text-white">{{burnoe_new.title}}</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="my-4">
            <BlockHeader>Статьи</BlockHeader>
            <div>
                <div class="px-3 pb-3 d-flex" v-for="article in burnoe_news" v-bind:key="article.id">
                    <div class="d-none d-sm-block" style="width: 131px; min-width: 131px">
                        <img src="https://via.placeholder.com/130x70" alt="" />
                    </div>
                    <div class="ml-3">
                        <div class="text-muted small">14:30</div>
                        <div>{{article.title}}</div>
                    </div>
                </div>
            </div>
        </div>

        <CardBlock class="my-4" title="Услуги" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="my-4" title="Еда" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="my-4" title="Развлечение" v-bind:categories="service_categories" v-bind:organizations="services" />

        <CardBlock class="my-4" v-bind:title="rent_title" v-bind:categories="rent_categories" v-bind:organizations="rent_organizations" />

        <JobsBlock class="my-4" v-bind:jobs="jobs" />

        <!--        todo NewsBlock -->
        <!--        todo ArticlesBlock -->

        <div class="mb-4 border" style="height: 180px">
            <span class="small">_version=0.01</span>
            <font-awesome-icon icon="user-secret" />
            <font-awesome-icon :icon="['fab', 'whatsapp']" />
        </div>
    </div>
</template>

<script>
    // @ is an alias to /src
    // import HelloWorld from '@/components/HelloWorld.vue'
    import BlockHeader from '@/components/BlockHeader.vue'
    import CardBlock from '@/components/CardBlock.vue'
    import JobsBlock from '@/components/JobsBlock.vue'

    export default {
        name: 'home',
        data: function() {
            return {
                chosens: [
                    {
                        id: 1,
                        title: 'Кафе "Три самурая"'
                    },
                    {
                        id: 2,
                        title: 'Прокат столы и стулья'
                    },
                    {
                        id: 3,
                        title: 'Кафе "Мирас"'
                    },
                    {
                        id: 4,
                        title: 'Русская Баня и Массаж'
                    },
                    {
                        id: 5,
                        title: 'Парикмахерская и Маникюр'
                    }
                ],
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
                ],
                jobs: [
                    {
                        id: 1,
                        title: 'Учитель физики',
                        description: 'Школа №29, от 55000 тг'
                    },
                    {
                        id: 2,
                        title: 'Кальянщик с опытом',
                        description: 'Ночной клуб Мистер, график с 20:00 до 02:00 ночи'
                    },
                    {
                        id: 3,
                        title: 'Оператор (девушка)',
                        description: 'Компьютерный клуб, опыт работы от года'
                    },
                    {
                        id: 4,
                        title: 'Наборщик текста',
                        description: 'Можно работать из дома, оплата сдельная'
                    },
                    {
                        id: 5,
                        title: 'Учитель физики',
                        description: 'Школа №29, временная работа'
                    },
                    {
                        id: 6,
                        title: 'Кальянщик с опытом',
                        description: 'Ночной клуб Мистер, с 20:00 до 02:00 ночи'
                    },
                    {
                        id: 7,
                        title: 'Оператор (девушка)',
                        description: 'Компьютерный клуб, опыт работы год и больше'
                    },
                ],
                burnoe_news: [
                    {
                        id: 1,
                        title: 'Почему закрыли барахолку в Алматы',
                        photo: 'https://via.placeholder.com/220x150/F0D165'
                    },
                    {
                        id: 2,
                        title: 'Врачи Алматы спасли жизнь роженице, умиравшей из-за разрыва печени',
                        photo: 'https://via.placeholder.com/220x150/F0D165'
                    },
                    {
                        id: 3,
                        title: 'Комнаты в студенческих общежитиях сдают в аренду в Алматы',
                        photo: 'https://via.placeholder.com/220x150/F0D165'
                    },
                    {
                        id: 4,
                        title: 'В Семее задержали серийного автовора, им оказался подросток',
                        photo: 'https://via.placeholder.com/220x150/F0D165'
                    },
                    {
                        id: 5,
                        title: 'Самолет посадили в Шымкенте, чтобы высадить дебоширов',
                        photo: 'https://via.placeholder.com/220x150/F0D165'
                    }
                ],
                articles: [
                    {
                        id: 1,
                        title: 'Почему закрыли барахолку в Алматы'
                    },
                    {
                        id: 2,
                        title: 'Врачи Алматы спасли жизнь роженице, умиравшей из-за разрыва печени'
                    },
                    {
                        id: 3,
                        title: 'Комнаты в студенческих общежитиях сдают в аренду в Алматы'
                    },
                    {
                        id: 4,
                        title: 'В Семее задержали серийного автовора, им оказался подросток'
                    },
                    {
                        id: 5,
                        title: 'Самолет посадили в Шымкенте, чтобы высадить дебоширов'
                    }
                ]
            }
        },
        components: {
            BlockHeader,
            CardBlock,
            JobsBlock
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
    .article-rounded-top {
        border-top-left-radius: 1.2rem;
        border-top-right-radius: 1.2rem;
        border: #999999 1px solid;
        border-bottom: 0;
    }
</style>
